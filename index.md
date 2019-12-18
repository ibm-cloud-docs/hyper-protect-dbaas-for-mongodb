---

copyright:
  years: 2019
lastupdated: "2019-12-20"

keywords: Hyper Protect DBaaS, mongo database, data security, cloud database

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
{:external: target="_blank" .external}

# Getting started with {{site.data.keyword.cloud_notm}} {{site.data.keyword.ihsdbaas_mongodb_full}}
{: #gettingstarted}

{{site.data.keyword.cloud}} {{site.data.keyword.ihsdbaas_mongodb_full}} is an {{site.data.keyword.cloud_notm}} service that provides {{site.data.keyword.mongodb}} databases on demand. It offers a flexible and scalable platform that allows you to quickly and easily provision and manage your database of choice.
{: shortdesc}

This {{site.data.keyword.cloud_notm}} offering provides {{site.data.keyword.mongodb}} database clusters. Each database cluster has one primary node and two secondary nodes (replicas that back up the primary).

With {{site.data.keyword.cloud_notm}} {{site.data.keyword.ihsdbaas_mongodb_full}}, you can create database clusters in the {{site.data.keyword.cloud_notm}}, view information about your nodes, databases, and users, monitor databases, and view service logs.

## Supported version
{: #mongodb_supported_version}

{{site.data.keyword.ihsdbaas_mongodb_full}} currently supports {{site.data.keyword.mongodb}} EE 3.6. It provides a secure, up-to-date version of the {{site.data.keyword.mongodb}} Enterprise database. We upgrade database maintenance versions `major.minor.maintenance` when appropriate.

## Prerequisite
{: #prerequisite}

Before you start, make sure you are using the [required browser software](/docs/overview?topic=overview-prereqs-platform) for {{site.data.keyword.cloud_notm}}.

For Safari, ensure that the **Prevent cross-site tracking** and **Block all cookies** options under **Safari > Preferences > Privacy** are not selected.

If you encounter problems using one of the required browsers, disable your browser plug-ins.

## Step 1: Creating a service instance
{: #creating-a-database-cluster-introduction}

When you create a service instance, you create a database cluster (replica set) with one primary and two secondary nodes as replicas, as shown in the following diagram.

![A {{site.data.keyword.ihsdbaas_full}} service instance](images/cluster-node-db.svg "A {{site.data.keyword.ihsdbaas_full}} service instance"){: caption="Figure 1. A {{site.data.keyword.ihsdbaas_full}} service instance" caption-side="bottom"}

If you haven't created a service instance yet, you can create one through [the web user interface](/docs/services/hyper-protect-dbaas-for-mongodb?topic=hyper-protect-dbaas-for-mongodb-dbaas_webui_service), [the CLI plug-in with the {{site.data.keyword.cloud_notm}} CLI](/docs/services/hyper-protect-dbaas-for-mongodb?topic=hyper-protect-dbaas-for-mongodb-install-dbaas-cli-plugin), or [the {{site.data.keyword.ihsdbaas_full}} RESTful APIs](https://{DomainName}/apidocs/hyperp-dbaas){: external}.

Free plans are available. They are designed for evaluation purposes and are not suitable for production usage. If you create free-plan instances, note that they will be automatically deleted 30 days after creation.

##  Step 2: Managing the database cluster
{: #managing-database-cluster-introduction}

Each {{site.data.keyword.ihsdbaas_mongodb_full}} cluster contains a DBaaS Manager, which manages and intelligently schedules your requests based on the available resources.

In a database cluster, you can:
- View information about nodes
- View information about databases
- View information about users
- Monitor databases
- View service logs

You can send the requests to the DBaaS Manager through one of the following interfaces:

- The [web user interface](/docs/services/hyper-protect-dbaas-for-mongodb?topic=hyper-protect-dbaas-for-mongodb-dbaas_webui_service)
- The [CLI plug-in with the {{site.data.keyword.cloud_notm}} CLI tool](/docs/services/hyper-protect-dbaas-for-mongodb?topic=hyper-protect-dbaas-for-mongodb-install-dbaas-cli-plugin)
- The [{{site.data.keyword.ihsdbaas_full}} RESTful APIs](https://{DomainName}/apidocs/hyperp-dbaas){: external}

To manage your nodes, databases and users, use your database client.

## Step 3: Connecting to databases
{: #accessing-database-introduction}

You can use the mongo shell, your favorite {{site.data.keyword.mongodb}} driver, or tools like {{site.data.keyword.mongodb}} Compass to connect to your databases. {{site.data.keyword.ihsdbaas_mongodb_full}} allows only SSL-secured client connections.

### Before you begin
{: #accessing-database-introduction-byb}

The tool you use needs to be compatible with MongoDB EE 3.6 that is supported by {{site.data.keyword.ihsdbaas_mongodb_full}}.

To enable verification of the server certificate during database connection, download a certificate authority (CA) file from the **Overview** page of the service dashboard, and copy it to the appropriate directory.

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

  The user name for the database admin as specified in the service creating screen.

- *password*

  The password for the database admin as specified in the service creating screen.

- *CAFile*

  The path of the `cert.pem` file you downloaded from the service dashboard.

#### Using MongoDB Compass or other tools
{: #accessing-database-introduction-connect-mongodb-compass}

For other tools, such as [{{site.data.keyword.mongodb}} Compass](https://docs.mongodb.com/compass/master/install/){: external}, {{site.data.keyword.ihsdbaas_mongodb_full}} supports *SSL server certificate validation* to connect to the host. If needed, use the CA file from the service dashboard.

For example, to use MongoDB Compass to connect to your databases, complete the following steps:

1. Copy the cluster URL from the **Overview** page in the {{site.data.keyword.ihsdbaas_mongodb_full}} service dashboard.
2. Open MongoDB Compass, which will use the URL from the clipboard to auto-populate the fields in the connection dialog.
3. In the **Authentication** drop-down list, select **Username / Password** and enter your user name and password.
4. Select **Server Validation** in the **SSL** field. Upload the certificate authority file you downloaded from the service dashboard, and click **CONNECT**.

## Step 4 (Conditional): Migrating from {{site.data.keyword.mongodb}} databases
{: #migrating-from-mongodb}

To migrate from {{site.data.keyword.mongodb}} databases to {{site.data.keyword.ihsdbaas_mongodb_full}}, follow the [migration instructions](/docs/services/hyper-protect-dbaas-for-mongodb?topic=hyper-protect-dbaas-for-mongodb-migration_mongodb).
