---

copyright:
  years: 2019
lastupdated: "2019-12-20"

keywords: migrate, restore

subcollection: hyper-protect-dbaas-for-mongodb

---

{:external: target="_blank" .external}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:tip: .tip}
{:note: .note}

# Migrating {{site.data.keyword.mongodb}} databases to {{site.data.keyword.cloud_notm}} {{site.data.keyword.ihsdbaas_mongodb_full}}
{: #migration_mongodb}

If you are using {{site.data.keyword.mongodb}} databases and want to migrate to {{site.data.keyword.cloud}} {{site.data.keyword.ihsdbaas_mongodb_full}}, read this topic for details. It does not matter where your {{site.data.keyword.mongodb}} databases are hosted, as long as the platform provides {{site.data.keyword.mongodb}} database services.
{: shortdesc}

## Before you begin
{: #migration_mongodb_before_begin}

To use the {{site.data.keyword.mongodb}} commands to complete the migration, you need to download and install {{site.data.keyword.mongodb}} of the version compatible with {{site.data.keyword.mongodb}} EE 3.6 that is supported by {{site.data.keyword.ihsdbaas_mongodb_full}}. For more information, see [{{site.data.keyword.mongodb}} Release Notes](https://docs.mongodb.com/manual/release-notes/){: external}.

## Step 1: Create a dump file for restoring the original databases
{: #step1_create_dump_file}

Use the following `mongodump` command to create a dump file that contains the databases you want to restore.

```
mongodump --host "<cluster_name>/<host_name_1>:<port_1>,<host_name_2>:<port_2>,<host_name_3>:<port_3>" --ssl --username <user_name> --authenticationDatabase <authentication_database_name> --db <database_name> --sslCAFile <cert_file> --out <dump_path>
```
{: pre}

The following table explains the parameters that are used in the command.

|Parameter|Description|Example|
|---------|-----------|-------|
|*cluster_name*|The MongoDB replica set name.|MongoDB-001|
|*host_name_i*|The name of the host server that hosts the node. One primary node and two secondary nodes are available in each cluster.|dbaas29.hyperprotectdbaas.cloud.ibm.com, dbaas31.hyperprotectdbaas.cloud.ibm.com, dbaas30.hyperprotectdbaas.cloud.ibm.com|
|*port_i*|The port to connect to the corresponding host. You can find the port numbers on the **Overview** page.|28205, 28016, 28175|
|*user_name*|The username to authenticate to the original databases. The user needs to have READ privilege on the database you want to migrate.|my_user|
|*authentication_database_name*|The authentication database for the specified user. If you don't specify an authentication database, `mongodump` assumes it to be the database that you set in `--db` option. If the `--db` option is also not specified, `mongodump` assumes it to be the admin database.|admin|
|*database_name*|The database you want to migrate. If you don't specify the database, `mongodump` dumps all the databases that belong to the user.|my_database|
|*cert_file*|The certificate authority (CA) file in the `.pem` format that you downloaded from the **Overview page** in the service dashboard. Specify it with a relative or absolute path.|./cert.pem|
|*dump_path*|The path specifies the directory where `mongodump` will write a [BSON](https://docs.mongodb.com/manual/reference/program/mongodump/index.html#cmdoption-mongodump-out){: external} file for the dumped database. You will find the BSON file in a subdirectory with the name of *database_name*. You can use relative or absolute paths.|my_dump_path|
{: caption="Table 1. Parameters that are needed to create a dump file"}

For more information about `mongodump` utility, see [{{site.data.keyword.mongodb}} documentation](https://docs.mongodb.com/manual/reference/program/mongodump/){: external}.

You can get most of the information from the cluster URI. The format of the URI is `mongodb://<host_name_1>:<port_1>,<host_name_2>:<port_2>,<host_name_3>:<port_3>/admin?replicaSet=<replica_set_name>`. You can match the parameters to the corresponding ones in the previous `mongodump` command.
{: tip}

## Step 2: Create a new {{site.data.keyword.ihsdbaas_mongodb_full}} service instance
{: #step2_creat_new_service_instance}

Before you restore the data, you need to create a new {{site.data.keyword.ihsdbaas_mongodb_full}} service instance as the target database cluster. You can use one of the following ways to create a new instance:
- [The web user interface](/docs/services/hyper-protect-dbaas-for-mongodb?topic=hyper-protect-dbaas-for-mongodb-dbaas_webui_service#dbaas_webui_create_service)
- [The CLI plug-in with the {{site.data.keyword.cloud_notm}} CLI](/docs/services/hyper-protect-dbaas-for-mongodb?topic=hyper-protect-dbaas-for-mongodb-dbaas_cli_create_service)
- [The {{site.data.keyword.ihsdbaas_full}} RESTful APIs](https://{DomainName}/apidocs/hyperp-dbaas){: external}

When you create the new service instance, you need to set the cluster name, the administrator name, and password. They are not necessarily to be the same as the ones in the original instance. It doesn't affect the migration. After the migration is completed, the databases are assigned to the new administrator/authentication database.

## Step 3: Restore the data from the dump file to the new service instance
{: #step3_restore_data}

Use the `mongorestore` command to restore the data from the dump file that is created in [Step 1](#step1_create_dump_file).

```
mongorestore --host "<cluster_name>/<host_name1>:<port1>,<host_name2>:<port2>,<host_name3>:<port3>" --ssl --username <user_name> --authenticationDatabase <authentication_database_name> --db <database_name> --sslCAFile <cert_file> <dump_file_path>
```
{: pre}

The following table explains the parameters that are used in the command.

|Parameter|Description|Example|
|---------|-----------|-------|
|*cluster_name*|The {{site.data.keyword.mongodb}} cluster name that you set when you create the service instance. You can find the **Cluster name** on the **Overview** page in the service dashboard. The name is the value after `replicaSet=`.||MongoDB-002|
|*host_name_i*|The name of the host server that hosts the targeting node. One primary node and two secondary nodes are available in each cluster. You can find the hostnames on the **Overview** page in the service dashboard.|dbaas29.hyperprotectdbaas.cloud.ibm.com, dbaas31.hyperprotectdbaas.cloud.ibm.com, dbaas30.hyperprotectdbaas.cloud.ibm.com|
|*port_i*|The port to connect the corresponding host. You can find the port numbers on the **Overview** page in the service dashboard.|28128, 28248, 28043|
|*user_name*|The username to authenticate to the target database. The user does not have to be the same as the user that creates the dump file.|new_user|
|*authentication_database_name*|The authentication database for the specified user. If you don't specify an authentication database, `mongodump` assumes it to be the database that you set in `--db` option. If the `--db` option is also not specified, `mongodump` assumes it to be the admin database.|admin|
|*database_name*|The target database that you want to migrate the data into. If the database does not exist, `mongorestore` creates it automatically. If you don't specify the database, `mongorestore` creates a database based on the original database.|my_database|
|*cert_file*|The certificate authority (CA) file in the `.pem` format that you downloadeded from the **Overview page** in the service dashboard. Specify it with a relative or absolute path.|./cert.pem|
|*dump_file_path*|The path of the folder containing dump files you created in [Step 1](#step1_create_dump_file), that is, *dump_path/database_name*. You can use relative or absolute paths.|my_dump_path/my_database|
{: caption="Table 2. Parameters that are needed to restore the data from a dump file"}

Use your database client to create new database users.
{: tip}

For {{site.data.keyword.mongodb}}, the migration merges the original data into the target cluster rather than overwriting the existing data if any. You can refer to the [detailed explanation](https://docs.mongodb.com/manual/reference/program/mongorestore/#insert-only){: external} of this feature in the {{site.data.keyword.mongodb}} website. You can also see [{{site.data.keyword.mongodb}} documentation](https://docs.mongodb.com/manual/reference/program/mongorestore/){: external} for more information about the `mongorestore` utility.

## What's next
{: #whats_next_migration_mongodb}

After the migration, you can connect to the new database cluster to check whether the data is migrated successfully.
