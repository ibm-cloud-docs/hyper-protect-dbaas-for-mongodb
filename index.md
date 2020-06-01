---

copyright:
  years: 2019, 2020
lastupdated: "2020-05-28"

keywords: hyper protect dbaas, hyper protect dbaas for mongodb, mongodb, cloud database, data security, secure database, encrypted database

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
{:help: data-hd-content-type='help'}
{:support: data-reuse='support'}

# Getting started with {{site.data.keyword.cloud_notm}} {{site.data.keyword.ihsdbaas_mongodb_full}}
{: #gettingstarted}

{{site.data.keyword.cloud}} {{site.data.keyword.ihsdbaas_full}} provides tamper-proof, enterprise cloud database environments with high availability for workloads with sensitive data. It offers a flexible platform that allows you to easily provision and manage your database of choice, without data security concerns.
{: shortdesc}

For more information about the industry-leading data security level of {{site.data.keyword.ihsdbaas_mongodb_full}}, see [Securing your data in {{site.data.keyword.ihsdbaas_mongodb_full}}](/docs/hyper-protect-dbaas-for-mongodb?topic=hyper-protect-dbaas-for-mongodb-data-security).

{{site.data.keyword.ihsdbaas_mongodb_full}} provides {{site.data.keyword.mongodb}} database clusters in the {{site.data.keyword.cloud_notm}}. Each {{site.data.keyword.ihsdbaas_full}} database cluster has one primary node and two secondary nodes (replicas that back up the primary). For more information about high data availability, see [High availability and disaster recovery](/docs/hyper-protect-dbaas-for-mongodb?topic=hyper-protect-dbaas-for-mongodb-high-availability-disaster-recovery).

With {{site.data.keyword.cloud_notm}} {{site.data.keyword.ihsdbaas_mongodb_full}}, you can create database clusters, view information about your nodes, databases, and users, monitor databases, and view service logs.

Watch the following video to find how to get started with {{site.data.keyword.cloud_notm}} {{site.data.keyword.ihsdbaas_mongodb_full}}:

<iframe width="737" height="415" src="https://www.youtube.com/embed/YzQdszTI4Zg" title="Getting started with Hyper Protect DBaaS" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## Supported version
{: #mongodb_supported_version}

{{site.data.keyword.ihsdbaas_mongodb_full}} currently supports {{site.data.keyword.mongodb}} EE 3.6. It provides a secure, up-to-date version of the {{site.data.keyword.mongodb}} Enterprise database. We upgrade database maintenance versions `major.minor.maintenance` when appropriate.

## Prerequisite
{: #prerequisite}

Before you start, make sure you're using the [required browser software](/docs/overview?topic=overview-prereqs-platform) for {{site.data.keyword.cloud_notm}}.

For Safari, ensure that the **Prevent cross-site tracking** and **Block all cookies** options under **Safari > Preferences > Privacy** are not selected.

If you encounter problems when you use one of the required browsers, disable your browser plug-ins.

## Step 1. Create a service instance
{: #creating-a-database-cluster-introduction}
{: help} 
{: support}

When you create a service instance, you create a cloud database cluster (replica set) with one primary and two secondary nodes as replicas, as shown in the following diagram. 

![A {{site.data.keyword.ihsdbaas_full}} service instance](images/cluster-node-db.svg "A {{site.data.keyword.ihsdbaas_full}} service instance with high availability"){: caption="Figure 1. A {{site.data.keyword.ihsdbaas_full}} service instance with high availability" caption-side="bottom"}

If you haven't created a service instance yet, you can create one through [the web user interface](/docs/hyper-protect-dbaas-for-mongodb?topic=hyper-protect-dbaas-for-mongodb-dbaas_webui_service), [the CLI](/docs/hyper-protect-dbaas-for-mongodb?topic=hyper-protect-dbaas-for-mongodb-dbaas_cli_create_service), or [the {{site.data.keyword.ihsdbaas_full}} RESTful APIs](/apidocs/hyperp-dbaas/hyperp-dbaas-v2){: external}.

Free plans are available. They are designed for evaluation purposes and are not suitable for production usage. If you create free-plan instances, note that they will be automatically deleted 30 days after creation.

You can select a root key that you create in {{site.data.keyword.hscrypto}} or {{site.data.keyword.keymanagementserviceshort}} only when you create the DBaaS instance. Otherwise, a randomly generated key will be used by default.
{: note}

##  Step 2. Manage the database cluster
{: #managing-database-cluster-introduction}
{: help} 
{: support}

Each {{site.data.keyword.ihsdbaas_mongodb_full}} cluster contains a DBaaS Manager, which manages and intelligently schedules your requests based on the available resources.

In a database cluster, you can:
- View information about databases
- View information about users
- View information about nodes
- View service logs
- Monitor databases

You can send the requests to the DBaaS Manager through one of the following interfaces:

- [The web user interface](/docs/hyper-protect-dbaas-for-mongodb?topic=hyper-protect-dbaas-for-mongodb-dbaas_webui_service)
- [The CLI plug-in with the {{site.data.keyword.cloud_notm}} CLI tool](/docs/hyper-protect-dbaas-for-mongodb?topic=hyper-protect-dbaas-for-mongodb-install-dbaas-cli-plugin)
- [The {{site.data.keyword.ihsdbaas_full}} RESTful APIs](/apidocs/hyperp-dbaas/hyperp-dbaas-v2){: external}

To manage your databases and database users, use your database client.

## Step 3. Connect to databases
{: #accessing-database-introduction}

You can use the mongo shell, your favorite {{site.data.keyword.mongodb}} driver, or tools like {{site.data.keyword.mongodb}} Compass to connect to your databases. {{site.data.keyword.ihsdbaas_mongodb_full}} allows only [SSL](#x2038004){: term}-secured client connections. 

### Before you begin
{: #accessing-database-introduction-byb}

The tool that you use needs to be compatible with MongoDB EE 3.6 that is supported by {{site.data.keyword.ihsdbaas_mongodb_full}}.

To enable verification of the server certificate during database connection, download a [certificate authority (CA)](#x2016383){: term} file from the **Overview** page of the service dashboard, and copy it to the appropriate directory.

#### Using mongo shell
{: #accessing-database-introduction-connect-mongoshell}

[Download the mongo shell](https://www.mongodb.com/download-center/enterprise){: external} as part of the MongoDB Server or as a standalone package. To check whether the version is compatible with MongoDB EE 3.6 supported by {{site.data.keyword.ihsdbaas_mongodb_full}}, see [{{site.data.keyword.mongodb}} Release Notes](https://docs.mongodb.com/manual/release-notes/){: external}.

To use the mongo shell to connect to your databases, run the following command. You can copy the commmand from the service dashboard. For more information about the mongo shell, see [mongo](https://docs.mongodb.com/manual/reference/program/mongo/index.html){: external}.

```
# mongo 'mongodb://<host_name_1>:<port_1>,\
<host_name_2>:<port_2>,\
<host_name_3>:<port_3>/admin?replicaSet=<cluster_name>' \
--ssl --username <user_name> --password <password> --sslCAFile <CAFile>
```
{: codeblock}

**Command options**

- *host_name_i*

  The name of the host server that hosts the node.

- *port_i*

  The port to connect to the corresponding host.

- *cluster_name*

  The {{site.data.keyword.mongodb}} cluster name that you set when you create the service instance.

- *user_name*

  The user name for the database admin as specified in the service creation page.

- *password*

  The password for the database admin as specified in the service creation page.

- *CAFile*

  The path of the `cert.pem` file you downloaded from the service dashboard.

#### Using MongoDB Compass or other tools
{: #accessing-database-introduction-connect-mongodb-compass}

For other tools, such as [{{site.data.keyword.mongodb}} Compass](https://docs.mongodb.com/compass/master/install/){: external}, {{site.data.keyword.ihsdbaas_mongodb_full}} supports *SSL server certificate validation* to connect to the host. If needed, use the CA file from the service dashboard.

For example, to use MongoDB Compass to connect to your databases, complete the following steps:

1. Copy the cluster URL from the **Overview** page in the {{site.data.keyword.ihsdbaas_mongodb_full}} service dashboard.
2. Open MongoDB Compass, which uses the URL from the clipboard to auto-populate the fields in the connection dialog.
3. In the **Authentication** drop-down list, select **Username / Password** and enter your user name and password.
4. Select **Server Validation** in the **SSL** field. Upload the certificate authority file you downloaded from the service dashboard, and click **CONNECT**.

## Step 4 (Conditional). Migrate from {{site.data.keyword.mongodb}} databases
{: #migrating-from-mongodb}

To migrate from {{site.data.keyword.mongodb}} databases to {{site.data.keyword.ihsdbaas_mongodb_full}}, follow the [migration instructions](/docs/hyper-protect-dbaas-for-mongodb?topic=hyper-protect-dbaas-for-mongodb-migration_mongodb).
