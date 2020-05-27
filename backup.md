---

copyright:
  years: 2019, 2020
lastupdated: "2020-04-15"

keywords: backup, disaster recovery, restore

subcollection: hyper-protect-dbaas-for-mongodb

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:important: .important}
{:screen: .screen}
{:codeblock: .codeblock}
{:tip: .tip}
{:pre: .pre}
{:note: .note}
{:term: .term}
{:external: target="_blank" .external}

# Backing up and restoring your databases by using {{site.data.keyword.cos_full_notm}}
{: #backup_mongodb_databases}

The {{site.data.keyword.cloud}} {{site.data.keyword.ihsdbaas_mongodb_full}} service automatically triggers a backup of your complete database once every 24 hours. These encrypted backups are available for the last seven days and redundantly available on local storage in all availability zones of the supported regions.
{: shortdesc}

If you want to increase your disaster recovery capabilities by making cross-region backups, you can use [{{site.data.keyword.cos_full_notm}} service](https://cloud.ibm.com/catalog/services/cloud-object-storage){: external} to store your data in a different region by referring to the following steps.

## Before you begin
{: #backup_mongodb_before_begin}

To use the {{site.data.keyword.mongodb}} commands to complete the backup, you need to download and install {{site.data.keyword.mongodb}} of the version compatible with {{site.data.keyword.mongodb}} EE 3.6 that is supported by {{site.data.keyword.ihsdbaas_mongodb_full}}. For more information, see [{{site.data.keyword.mongodb}} Release Notes](https://docs.mongodb.com/manual/release-notes/){: external}.

## Step 1. Create a dump file for backing up the original databases
{: #step1_create_dump_file_backup_mongodb}

Use the following `mongodump` command to create a dump file that contains the databases that you want to back up.

```
mongodump --host "<cluster_name>/<host_name_1>:<port_1>,<host_name_2>:<port_2>,<host_name_3>:<port_3>" --ssl --username <user_name> --authenticationDatabase <authentication_database_name> --db <database_name> --sslCAFile <cert_file> --out <dump_file>
```
{: pre}

The following table explains the parameters that are used in the command.

|Parameter|Description|Example|
|---------|-----------|-------|
|*cluster_name*|The {{site.data.keyword.mongodb}} cluster name that you set when you create the service instance. You can find the **Cluster name** on the **Overview** page in the service dashboard.|MongoDB-001|
|*host_name_i*|The name of the host server that hosts the node. One primary node and two secondary nodes are available in each cluster. You can find the hostnames on the **Overview** page.|dbaas29.hyperprotectdbaas.cloud.ibm.com, dbaas31.hyperprotectdbaas.cloud.ibm.com, dbaas30.hyperprotectdbaas.cloud.ibm.com|
|*port_i*|The port to connect to the corresponding host. You can find the port numbers on the **Overview** page.|28205, 28016, 28175|
|*user_name*|The username to authenticate to the original databases. The user needs to have READ privilege on the database you want to migrate.|my_user|
|*authentication_database_name*|The authentication database for the specified user. If you don't specify an authentication database, `mongodump` assumes it to be the database that you set in `--db` option. If the `--db` option is also not specified, `mongodump` assumes it to be the admin database.|admin|
|*database_name*|The database that you want to back up. If you don't specify the database, `mongodump` dumps all the databases that belong to the user.|my_database|
|*cert_file*|The [certificate authority (CA)](#x2016383){: term} file in the `.pem` format that you downloaded from the **Overview page**. Specify it with a relative or absolute path.|./cert.pem|
|*dump_file*|The `.dump` file to store the original data. You can use relative or absolute paths to specify the file.|./mongo.dump|
{: caption="Table 1. Parameters that are needed to create a dump file"}

For more information about `mongodump` utility, see [{{site.data.keyword.mongodb}} documentation](https://docs.mongodb.com/manual/reference/program/mongodump/){: external}.

You can get most of the information from the cluster URL on the **Overview** page in the service dashboard. The format of the URL is `mongodb://<host_name_1>:<port_1>,<host_name_2>:<port_2>,<host_name_3>:<port_3>/admin?replicaSet=<cluster_name>`. You can match the parameters to the corresponding ones in the previous `mongodump` command.
{: tip}

## Step 2. Create a {{site.data.keyword.cos_full_notm}} instance to upload the dump file
{: #step2_create_object_storage_backup_mongodb}

Complete the following steps to back up your data in a Cloud {{site.data.keyword.cos_short}} instance in a different region:

1. [Create a {{site.data.keyword.cos_short}} instance](/docs/cloud-object-storage?topic=cloud-object-storage-provision).
2. [Create a bucket](/docs/cloud-object-storage?topic=cloud-object-storage-endpoints#endpoints-region) in a different region.
3. [Create a service credential](/docs/cloud-object-storage?topic=cloud-object-storage-service-credentials) and save the `access_key_id` and `secret_access_key` for later use.
4. Install a S3 client.
5. Use the S3 client and the access keys to connect to the Cloud {{site.data.keyword.cos_short}} endpoint of the bucket that you create earlier. For detailed instructions on configuring the `.s3cfg` file, see [Use IBM Cloud Object Storage to serve static website content](https://www.ibm.com/cloud/blog/static-websites-cloud-object-storage-cos){: external}.
6. Use the S3 client to [upload the {{site.data.keyword.mongodb}} backup file](/docs/cloud-object-storage?topic=cloud-object-storage-upload) that you create in [Step 1](#step1_create_dump_file_backup_mongodb) to the bucket.

For more information about {{site.data.keyword.cos_full_notm}}, see [the {{site.data.keyword.cos_full_notm}} documentation](/docs/cloud-object-storage?topic=cloud-object-storage-getting-started).

If you want to restore the data from the Cloud {{site.data.keyword.cos_short}} instance to a {{site.data.keyword.ihsdbaas_mongodb_full}} instance, complete the following Step 3.

## Step 3. Restore the data from the Cloud {{site.data.keyword.cos_short}} instance to a {{site.data.keyword.ihsdbaas_mongodb_full}} instance
{: #step3_restore_data_from_cos_mongodb}

You need to download the backup file from the Cloud {{site.data.keyword.cos_short}} bucket to your local machine first, then use the `mongorestore` command to restore the data.

```
mongorestore --host "<cluster_name>/<host_name_1>:<port_1>,<host_name_2>:<port_2>,<host_name_3>:<port_3>" --ssl --username <user_name> --authenticationDatabase <authentication_database_name> --db <database_name> --sslCAFile <cert_file> <dump_file>
```
{: pre}

The following table explains the parameters that are used in the command.

|Parameter|Description|Example|
|---------|-----------|-------|
|*cluster_name*|The target {{site.data.keyword.mongodb}} cluster name that you set when you create the service instance. You can find the **Cluster name** on the **Overview** page in the service dashboard.|MongoDB-002|
|*host_name_i*|The name of the host server that hosts the target node. One primary node and two secondary nodes are available in each cluster. You can find the hostnames on the **Overview** page.|dbaas29.hyperprotectdbaas.cloud.ibm.com, dbaas31.hyperprotectdbaas.cloud.ibm.com, dbaas30.hyperprotectdbaas.cloud.ibm.com|
|*port_i*|The port to connect to the corresponding host. You can find the port numbers on the **Overview** page.|28128, 28248, 28043|
|*user_name*|The username to authenticate to the target database. The user doesn't have to be the same as the user that creates the dump file.|new_user|
|*authentication_database_name*|The authentication database for the specified user. If you don't specify an authentication database, `mongodump` assumes it to be the database that you set in `--db` option. If the `--db` option is also not specified, `mongodump` assumes it to be the admin database.|admin|
|*database_name*|The target database that you want to restore the data into. If the database doesn't exist, `mongorestore` creates it automatically. If you don't specify the database, `mongorestore` creates a database based on the original database.|my_database|
|*cert_file*|The certificate authority (CA) file in the `.pem` format that you downloaded from the **Overview page**. Specify it with a relative or absolute path.|./cert.pem|
|*dump_file*|The `.dump` file that you download from your Cloud {{site.data.keyword.cos_short}} bucket. You can use relative or absolute paths to specify the file.|./mongo.dump|
{: caption="Table 2. Parameters that are needed to restore the data from a dump file"}

For {{site.data.keyword.mongodb}}, the migration merges the original data into the target cluster rather than overwriting the existing data if any. You can refer to the [detailed explanation](https://docs.mongodb.com/manual/reference/program/mongorestore/#insert-only){: external} of this feature in the {{site.data.keyword.mongodb}} website. You can also see [{{site.data.keyword.mongodb}} documentation](https://docs.mongodb.com/manual/reference/program/mongorestore/){: external} for more information about the `mongorestore` utility.

## What's next
{: #whats_next_backup_mongodb}

After [Step 3](#step3_restore_data_from_cos_mongodb), you can connect to the database cluster to check whether the data is restored successfully.
