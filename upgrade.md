---

copyright:
  years: 2020, 2021
lastupdated: "2021-04-21"

keywords: upgrade mongodb, mongodb version

subcollection: hyper-protect-dbaas-for-mongodb

---

{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}
{:android: data-hd-operatingsystem="android"}
{:api: .ph data-hd-interface='api'}
{:apikey: data-credential-placeholder='apikey'}
{:app_key: data-hd-keyref="app_key"}
{:app_name: data-hd-keyref="app_name"}
{:app_secret: data-hd-keyref="app_secret"}
{:app_url: data-hd-keyref="app_url"}
{:authenticated-content: .authenticated-content}
{:beta: .beta}
{:c#: data-hd-programlang="c#"}
{:cli: .ph data-hd-interface='cli'}
{:codeblock: .codeblock}
{:curl: .ph data-hd-programlang='curl'}
{:deprecated: .deprecated}
{:dotnet-standard: .ph data-hd-programlang='dotnet-standard'}
{:download: .download}
{:external: target="_blank" .external}
{:faq: data-hd-content-type='faq'}
{:fuzzybunny: .ph data-hd-programlang='fuzzybunny'}
{:generic: data-hd-operatingsystem="generic"}
{:generic: data-hd-programlang="generic"}
{:gif: data-image-type='gif'}
{:go: .ph data-hd-programlang='go'}
{:help: data-hd-content-type='help'}
{:hide-dashboard: .hide-dashboard}
{:hide-in-docs: .hide-in-docs}
{:important: .important}
{:ios: data-hd-operatingsystem="ios"}
{:java: .ph data-hd-programlang='java'}
{:java: data-hd-programlang="java"}
{:javascript: .ph data-hd-programlang='javascript'}
{:javascript: data-hd-programlang="javascript"}
{:new_window: target="_blank"}
{:note .note}
{:note: .note}
{:objectc data-hd-programlang="objectc"}
{:org_name: data-hd-keyref="org_name"}
{:php: data-hd-programlang="php"}
{:pre: .pre}
{:preview: .preview}
{:python: .ph data-hd-programlang='python'}
{:python: data-hd-programlang="python"}
{:route: data-hd-keyref="route"}
{:row-headers: .row-headers}
{:ruby: .ph data-hd-programlang='ruby'}
{:ruby: data-hd-programlang="ruby"}
{:runtime: architecture="runtime"}
{:runtimeIcon: .runtimeIcon}
{:runtimeIconList: .runtimeIconList}
{:runtimeLink: .runtimeLink}
{:runtimeTitle: .runtimeTitle}
{:screen: .screen}
{:script: data-hd-video='script'}
{:service: architecture="service"}
{:service_instance_name: data-hd-keyref="service_instance_name"}
{:service_name: data-hd-keyref="service_name"}
{:shortdesc: .shortdesc}
{:space_name: data-hd-keyref="space_name"}
{:step: data-tutorial-type='step'}
{:subsection: outputclass="subsection"}
{:support: data-reuse='support'}
{:swift: .ph data-hd-programlang='swift'}
{:swift: data-hd-programlang="swift"}
{:table: .aria-labeledby="caption"}
{:term: .term}
{:tip: .tip}
{:tooling-url: data-tooling-url-placeholder='tooling-url'}
{:troubleshoot: data-hd-content-type='troubleshoot'}
{:tsCauses: .tsCauses}
{:tsResolve: .tsResolve}
{:tsSymptoms: .tsSymptoms}
{:tutorial: data-hd-content-type='tutorial'}
{:ui: .ph data-hd-interface='ui'}
{:unity: .ph data-hd-programlang='unity'}
{:url: data-credential-placeholder='url'}
{:user_ID: data-hd-keyref="user_ID"}
{:vbnet: .ph data-hd-programlang='vb.net'}
{:video: .video}


# Upgrading to a new major version
{: #upgrade-version}

You can upgrade your existing {{site.data.keyword.ihsdbaas_mongodb_full}} service instance running {{site.data.keyword.mongodb}} 3.6 to version 4.4. To upgrade from {{site.data.keyword.mongodb}} 3.6 to 4.4, you need to create a new service instance running {{site.data.keyword.mongodb}} 4.4, and manually restore a backup of your data into the new service instance.
{: shortdesc}

## Before you begin
{: #before-begin}

To use the `mongodump` and `mongorestore` commands to complete the upgrade, you need to download and install the [{{site.data.keyword.mongodb}} Database Tools](https://www.mongodb.com/try/download/database-tools){: external}.

Starting with {{site.data.keyword.mongodb}} 4.4, the {{site.data.keyword.mongodb}} Database Tools are released separately from the {{site.data.keyword.mongodb}} Server and use their own versioning. Before you download the tools, refer to the [`mongodump` documentation](https://docs.mongodb.com/database-tools/mongodump/#compatibility){: external} and the [`mongorestore` documentation](https://docs.mongodb.com/database-tools/mongorestore/#compatibility){: external} to ensure that they're compatible with {{site.data.keyword.mongodb}} 3.6 and {{site.data.keyword.mongodb}} 4.4.
{: note}

## Step 1. Create a dump file for backing up the original databases
{: #step1-create-dump-file}

Use the following `mongodump` command to create a dump file that contains the databases that you want to back up.

```
mongodump --host "<cluster_name>/<host_name_1>:<port_1>,<host_name_2>:<port_2>,<host_name_3>:<port_3>" --ssl --username <user_name> --authenticationDatabase <authentication_database_name> --db <database_name> --sslCAFile <cert_file> --out <dump_file>
```
{: pre}

The following table explains the parameters that are used in the command.

|Parameter|Description|Example|
|---------|-----------|-------|
|*cluster_name*|The {{site.data.keyword.mongodb}} cluster name that you set when you create the service instance. You can find the **Cluster name** on the **Overview** page on the service dashboard.|MongoDB-001|
|*host_name_i*|The name of the host server that hosts the node. One primary node and two secondary nodes are available in each cluster. You can find the hostnames on the **Overview** page.|dbaas29.hyperprotectdbaas.cloud.ibm.com, dbaas31.hyperprotectdbaas.cloud.ibm.com, dbaas30.hyperprotectdbaas.cloud.ibm.com|
|*port_i*|The port to connect to the corresponding host. You can find the port numbers on the **Overview** page.|28205, 28016, 28175|
|*user_name*|The username to authenticate to the original databases. The user needs to have READ privilege on the database you want to migrate.|my_user|
|*authentication_database_name*|The authentication database for the specified user. If you don't specify an authentication database, `mongodump` assumes it to be the database that you set in `--db` option. If the `--db` option is also not specified, `mongodump` assumes it to be the admin database.|admin|
|*database_name*|The database that you want to back up. If you don't specify the database, `mongodump` dumps all the databases that belong to the user.|my_database|
|*cert_file*|The [certificate authority (CA)](#x2016383){: term} file in the `.pem` format that you downloaded from the **Overview** page. Specify it with a relative or absolute path.|./cert.pem|
|*dump_file*|The `.dump` file to store the original data. You can use relative or absolute paths to specify the file.|./mongo.dump|
{: caption="Table 1. Parameters that are needed to create a dump file"}

For more information about the `mongodump` utility, see the [mongodump documentation](https://docs.mongodb.com/database-tools/mongodump/){: external}.

You can get most of the information from the cluster URL on the Manage page on the service dashboard. The format of the URL is `mongodb://<host_name_1>:<port_1>,<host_name_2>:<port_2>,<host_name_3>:<port_3>/admin?replicaSet=<cluster_name>`. You can match the parameters to the corresponding ones in the previous `mongodump` command.
{: tip}

## Step 2. Create a new service instance with suitable resource allocation values
{: #step2-create-new-instance}

[Create a new {{site.data.keyword.ihsdbaas_mongodb_full}} service instance](/docs/hyper-protect-dbaas-for-mongodb?topic=hyper-protect-dbaas-for-mongodb-create-service), which runs {{site.data.keyword.mongodb}} 4.4 by default. Make sure the disk size that you select is enough to restore the database backup.

## Step 3. Restore the data to the new service instance
{: #step3-restore-data}

Use the `mongorestore` command to restore the data to the new {{site.data.keyword.ihsdbaas_mongodb_full}} service instance.

```
mongorestore --host "<cluster_name>/<host_name_1>:<port_1>,<host_name_2>:<port_2>,<host_name_3>:<port_3>" --ssl --username <user_name> --authenticationDatabase <authentication_database_name> --db <database_name> --sslCAFile <cert_file> <dump_file>
```

The following table explains the parameters that are used in the command.

|Parameter|Description|Example|
|---------|-----------|-------|
|*cluster_name*|The target {{site.data.keyword.mongodb}} cluster name that you set when you create the service instance. You can find the **Cluster name** on the **Overview** page on the service dashboard.|MongoDB-002|
|*host_name_i*|The name of the host server that hosts the target node. One primary node and two secondary nodes are available in each cluster. You can find the hostnames on the **Overview** page.|dbaas29.hyperprotectdbaas.cloud.ibm.com, dbaas31.hyperprotectdbaas.cloud.ibm.com, dbaas30.hyperprotectdbaas.cloud.ibm.com|
|*port_i*|The port to connect to the corresponding host. You can find the port numbers on the **Overview** page.|28128, 28248, 28043|
|*user_name*|The username to authenticate to the target database. The user doesn't have to be the same as the user that creates the dump file.|new_user|
|*authentication_database_name*|The authentication database for the specified user. If you don't specify an authentication database, `mongodump` assumes it to be the database that you set in `--db` option. If the `--db` option is also not specified, `mongodump` assumes it to be the admin database.|admin|
|*database_name*|The target database that you want to restore the data into. If the database doesn't exist, `mongorestore` creates it automatically. If you don't specify the database, `mongorestore` creates a database based on the original database.|my_database|
|*cert_file*|The certificate authority (CA) file in the `.pem` format that you downloaded from the **Overview** page. Specify it with a relative or absolute path.|./cert.pem|
|*dump_file*|The `.dump` file that you download from your Cloud {{site.data.keyword.cos_short}} bucket. You can use relative or absolute paths to specify the file.|./mongo.dump|
{: caption="Table 2. Parameters that are needed to restore the data from a dump file"}

For {{site.data.keyword.mongodb}}, the migration merges the original data into the target cluster rather than overwrites the existing data if any. You can refer to the [detailed explanation](https://docs.mongodb.com/database-tools/mongorestore/#insert-only){: external} of this feature in the {{site.data.keyword.mongodb}} website. For more information about the `mongorestore` utility, see the [{{site.data.keyword.mongodb}} documentation](https://docs.mongodb.com/database-tools/mongorestore/){: external}.

## What's next
{: #whats-next}

After [Step 3](#step3-restore-data), you can connect to the database cluster to check whether the data is restored successfully.

Make sure your data is restored in step 3 before you delete your {{site.data.keyword.mongodb}} 3.6 service instance.
{: important}
