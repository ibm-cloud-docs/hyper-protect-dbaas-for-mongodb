---

copyright:
  years: 2019, 2021
lastupdated: "2021-05-12"

keywords: hyper protect dbaas, hyper protect dbaas for mongodb, mongodb, cloud database, data security, secure database, encrypted database

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


# Getting started with {{site.data.keyword.cloud_notm}} {{site.data.keyword.ihsdbaas_mongodb_full}}
{: #gettingstarted}

{{site.data.keyword.cloud}} {{site.data.keyword.ihsdbaas_full}} provides tamper-proof, enterprise cloud database environments with high availability for workloads with sensitive data. It offers a flexible platform where you can easily provision and manage your database of choice ({{site.data.keyword.mongodb}} and [{{site.data.keyword.postgresql}}](/docs/hyper-protect-dbaas-for-postgresql?topic=hyper-protect-dbaas-for-postgresql-gettingstarted)), without data security concerns.
{: shortdesc}

For more information about the industry-leading data security level of {{site.data.keyword.ihsdbaas_mongodb_full}}, see [Securing your data in {{site.data.keyword.ihsdbaas_mongodb_full}}](/docs/hyper-protect-dbaas-for-mongodb?topic=hyper-protect-dbaas-for-mongodb-data-security).

{{site.data.keyword.ihsdbaas_mongodb_full}} provides {{site.data.keyword.mongodb}} database clusters in the {{site.data.keyword.cloud_notm}}. Each {{site.data.keyword.ihsdbaas_full}} database cluster has one primary node and two secondary nodes (replicas that back up the primary). For more information about high data availability, see [High availability and disaster recovery](/docs/hyper-protect-dbaas-for-mongodb?topic=hyper-protect-dbaas-for-mongodb-high-availability-disaster-recovery).

With {{site.data.keyword.cloud_notm}} {{site.data.keyword.ihsdbaas_mongodb_full}}, you can create database clusters, scale your resources, view information about your nodes, databases, and users, monitor databases, and view service logs.

Watch the following video to find out how to get started with {{site.data.keyword.cloud_notm}} {{site.data.keyword.ihsdbaas_full}}:

![Getting started with {{site.data.keyword.ihsdbaas_full}}](https://www.kaltura.com/p/1773841/sp/177384100/embedIframeJs/uiconf_id/27941801/partner_id/1773841?iframeembed=true&entry_id=0_2wa8vkxt){: video output="iframe" data-script="#video-transcript-gettingstarted" id="mediacenterplayer" frameborder="0" width="560" height="315" allowfullscreen webkitallowfullscreen mozAllowFullScreen}

## Video transcript
{: #video-transcript-gettingstarted}
{: notoc}

Hi, welcome to this getting started video for IBM Cloud™ Hyper Protect DBaaS, an offering that allows you to easily provision and manage highly secure, high volume databases for your sensitive data without sacrificing performance.

Every Hyper Protect DBaaS service instance contains a highly available three-node cluster with multi-zone region support. Built on LinuxONE technology, Hyper Protect DBaaS encrypts both data at rest and data in flight. It offers complete data confidentiality; not even the cloud admin has access to your data. It also supports many industry certifications, GDPR, for example, and client regulatory compliance activities. And as you will see in the rest of this video, you can easily provision and monitor secure MongoDB or PostgreSQL databases without specialized database skills.

In the following demo, you will learn how to create a Hyper protect DBaaS service instance, connect to your databases, and navigate the service dashboard.

Before you start, you need to have an IBM Cloud account and log in. Go to the IBM Cloud service Catalog and find Hyper Protect DBaaS. You can choose between MongoDB and PostgreSQL. In this video, we’ll use MongoDB as an example.

On the service provisioning page, select a region and a pricing plan. With the flexible plan, you can select your initial resource allocation values.

You can also try out the service with the free plan. The service name is auto-generated. Select a resource group to organize your resources, which can't be changed after you create the instance. Tags are optional. Name the cluster and the admin. Enter and confirm your password. You can choose to use your own KMS instance with a root key for more secure encryption. You also have the option of using private service endpoints to enhance control and security over your data.

You can find the service instance you just created on the Resource list page. It takes a few minutes for the provisioning to complete. Select your service instance to open the service dashboard.

Click Getting started to read the getting started documentation. If you need more information and detailed instructions, select View docs in Actions to go to the full documentation.

To connect to the databases, you can run the mongo shell command or use MongoDB Compass. In this video, we'll use MongoDB Compass. In the service dashboard, download the certificate authority file, and copy the cluster URL.

Open MongoDB Compass. Paste your connection string. Click Fill in connection fields individually. In the Authentication dropdown list, choose Username / Password, enter your admin name and password. In the More options tab, for SSL, select Server Validation. Upload the certificate authority file you just downloaded, and click Connect. Now you have connected to your databases.

Let’s go back to the service dashboard.

If you are using the flexible pricing plan, you can see the Resources label. On the resources page, you can manually adjust the amount of resources to suit your workload and the size of your data. If you are using the old fixed pricing plan (Small, Medium, or Large), go to the Plan page first to convert you fixed pricing plan to the flexible plan and reload the dashboard to see the Resources page and scale your resources. Free service instances can't be converted or scaled.

On the Manage page, you can see the overall information of your service instance.

Select Databases and Users to view the information about your databases and users.

Select Nodes to view the information of your primary and secondary nodes, and download audit and mongod logs.

Select Observability to go to monitoring and logging. To use monitoring or logging, first you need to agree to sending your metrics or logs to the monitoring or logging service. The steps to add monitoring and logging are similar. Here we’ll use logging as an example. Click Add logging. If you don't have a Log Analysis service instance, you'll be directed to the service creation page to create one. Select the same region as your service instance. After you add the Log Analysis service instance, click Launch logging to be directed to the Log Analysis dashboard to view the logs.

Similarly, you can add the IBM Cloud Monitoring service to monitor your CPU, memory and disk usage.

Now you have a general idea about the service. Go to the [Hyper Protect DBaaS homepage](https://www.ibm.com/cloud/hyper-protect-dbaas){: external} to learn more and get started for free.

## Supported version
{: #mongodb_supported_version}

{{site.data.keyword.ihsdbaas_mongodb_full}} currently supports {{site.data.keyword.mongodb}} EE 4.4. It provides a secure, up-to-date version of the {{site.data.keyword.mongodb}} Enterprise database. We upgrade database maintenance versions `major.minor.maintenance` when appropriate.

## Prerequisites
{: #prerequisite}

1. To use the UI, make sure you're using the [required browser software](/docs/overview?topic=overview-prereqs-platform) for {{site.data.keyword.cloud_notm}}.

  For Safari, ensure that the **Prevent cross-site tracking** and **Block all cookies** options under **Safari > Preferences > Privacy** are not selected.

  If you encounter problems when you use one of the required browsers, disable your browser plug-ins.

2. You can create a 30-day free plan service instance with three types of accounts: [Pay-As-You-Go, Subscription](/docs/account?topic=account-accounts), or [trial accounts](/docs/account?topic=account-accountfaqs#freetrial) (trial accounts are available for faculty and students at accredited academic institutions).

  To check your account type, go to the [Account settings](https://cloud.ibm.com/account/settings){: external} page.

  If you have a Lite account, you need to [upgrade your account to a Pay-As-You-Go or Subscription account](/docs/account?topic=account-upgrading-account), or [convert it to a trial account](/docs/account?topic=account-accountfaqs#convertacct).

## Step 1. Create a service instance
{: #creating-a-database-cluster-introduction}
{: help} 
{: support}

When you create a service instance, you create a cloud database cluster (replica set) with one primary and two secondary nodes as replicas, as shown in the following diagram. 

![A {{site.data.keyword.ihsdbaas_full}} service instance](images/cluster-node-db.svg "A {{site.data.keyword.ihsdbaas_full}} service instance with high availability"){: caption="Figure 1. A {{site.data.keyword.ihsdbaas_full}} service instance with high availability" caption-side="bottom"}

You can create a service instance through the UI, CLI, and API. For more information and detailed instructions, see [Creating a service instance](/docs/hyper-protect-dbaas-for-mongodb?topic=hyper-protect-dbaas-for-mongodb-create-service).

Free plans are available. They are designed for evaluation purposes and are not suitable for production usage. Free-plan service instances will be automatically deleted 30 days after creation.
{: note}

## Step 2. Connect to databases
{: #accessing-database-introduction}

You can use the mongo shell, your favorite {{site.data.keyword.mongodb}} driver, or tools like {{site.data.keyword.mongodb}} Compass to connect to your databases. {{site.data.keyword.ihsdbaas_mongodb_full}} allows only [SSL](#x2038004){: term}-secured client connections. 

### Before you begin
{: #accessing-database-introduction-byb}

The tool that you use needs to be compatible with {{site.data.keyword.mongodb}} EE 4.4 that is supported by {{site.data.keyword.ihsdbaas_mongodb_full}}.

To enable verification of the server certificate during database connection, download the [certificate authority (CA)](#x2016383){: term} file from the **Overview** page of the service dashboard, and copy it to the appropriate directory.

The CA file that you download from the dashboard contains root and intermediate certificates, which are both required for certificate validation.
{: note}

#### Using mongo shell
{: #accessing-database-introduction-connect-mongoshell}

[Download the mongo shell](https://www.mongodb.com/download-center/enterprise){: external} as part of the {{site.data.keyword.mongodb}} Server or as a stand-alone package. To check whether the version is compatible with {{site.data.keyword.mongodb}} EE 4.4 supported by {{site.data.keyword.ihsdbaas_mongodb_full}}, see [{{site.data.keyword.mongodb}} Release Notes](https://docs.mongodb.com/manual/release-notes/){: external}.

To use the mongo shell to connect to your databases, run the following command. You can copy the command from the service dashboard. For more information about the mongo shell, see the [mongo shell documentation](https://docs.mongodb.com/manual/mongo/){: external}.

```
# mongo 'mongodb://<host_name_1>:<port_1>,\
<host_name_2>:<port_2>,\
<host_name_3>:<port_3>/admin?replicaSet=<cluster_name>' \
--tls --username <user_name> --password <password> --tlsCAFile <CAFile>
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

  The path of the `cert.pem` file that you downloaded from the service dashboard.

#### Using {{site.data.keyword.mongodb}} Compass or other tools
{: #accessing-database-introduction-connect-mongodb-compass}

For other tools, such as [{{site.data.keyword.mongodb}} Compass](https://docs.mongodb.com/compass/master/install/){: external}, {{site.data.keyword.ihsdbaas_mongodb_full}} supports *SSL server certificate validation* to connect to the host.

For example, to use {{site.data.keyword.mongodb}} Compass to connect to your databases, complete the following steps:

1. Copy the cluster URL from the **Overview** page on the {{site.data.keyword.ihsdbaas_mongodb_full}} service dashboard.
2. Open {{site.data.keyword.mongodb}} Compass. On the **New Connection** page, paste the cluster URL.
3. Click **Fill in connection fields individually**.
4. For **Authentication**, select **Username / Password**. Enter your user name and password.
5. Click the **More Options** tab. In the **SSL** field, select **Server Validation** . Upload the certificate authority file that you downloaded from the service dashboard, and click **CONNECT**.

Don't skip step 5, otherwise the connection will fail.
{: important}

##  Step 3. Manage the database cluster
{: #managing-database-cluster-introduction}
{: help} 
{: support}

Each {{site.data.keyword.ihsdbaas_mongodb_full}} cluster contains a DBaaS Manager, which manages and intelligently schedules your requests based on the available resources.

In a database cluster, you can:
- Scale your resources
- View information about databases, users, and nodes
- View service logs
- Monitor databases
- ...

You can send the requests to the DBaaS Manager through the UI, CLI, and API. For detailed instructions, see [Managing your service instance](/docs/hyper-protect-dbaas-for-mongodb?topic=hyper-protect-dbaas-for-mongodb-manage-service).

To create or delete your databases and database users, use your database client.

## Step 4 (Optional). Migrate from {{site.data.keyword.mongodb}} databases
{: #migrating-from-mongodb}

To migrate from {{site.data.keyword.mongodb}} databases to {{site.data.keyword.ihsdbaas_mongodb_full}}, follow the [migration instructions](/docs/hyper-protect-dbaas-for-mongodb?topic=hyper-protect-dbaas-for-mongodb-migration_mongodb).
