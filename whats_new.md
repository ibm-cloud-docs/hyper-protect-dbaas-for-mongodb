---

copyright:
  years: 2019
lastupdated: "2019-12-20"

keywords: release note, new

subcollection: hyper-protect-dbaas-for-mongodb

---

{:external: target="_blank" .external}
{:shortdesc: .shortdesc}

# What's new
{: #what-new}

Stay up to date with the new features that are available for {{site.data.keyword.cloud}} {{site.data.keyword.ihsdbaas_mongodb_full}}.
{: shortdesc}

## 18 December 2019
{: #Dec-2019} 

### Added: Role-based authorization with {{site.data.keyword.cloud_notm}} Identity and Access Management
{: #added-iam-integration}

You can assign access to other users or services to use your service instance with {{site.data.keyword.cloud_notm}} Identity and Access Management (IAM).

### Added: Creating a service instance with your own encryption key
{: #added-byok}

You can create a {{site.data.keyword.ihsdbaas_mongodb_full}} service instance with your own encryption key, using {{site.data.keyword.keymanagementservicelong_notm}} or {{site.data.keyword.cloud_notm}} {{site.data.keyword.hscrypto}}.

### Changed: Dashboard
{: #changed-dashboard}

The major changes to the dashboard are navigation and renaming of terms. The new service dashboard uses side navigation. The terms **instance** and **replica** are replaced by **node**.

### Changed: Manage databases and database users with only database clients
{: #changed-manage}

To enhance security, use your database client to manage databases and database users. The **Databases**, **Users**, and **Nodes** pages in the dashboard are read-only.

### Changed: Python components for using CLI
{: #change-cli-python}

Python 3 (instead of Python 2) components are required to access a complete set of DBaaS commands when you use the {{site.data.keyword.cloud_notm}} CLI.

## 23 September 2019
{: #Sep23-2019} 

### Added: Sending logs to {{site.data.keyword.la_full_notm}}
{: #added-logging}

You can view logs of your {{site.data.keyword.ihsdbaas_mongodb_full}} instance in a configured {{site.data.keyword.loganalysisshort_notm}} instance.

### Added: {{site.data.keyword.ihsdbaas_mongodb_full}} expands into Sydney region
{: #Sydney-region}

You can create {{site.data.keyword.ihsdbaas_mongodb_full}} resources in the Sydney region. To receive logs and events of your {{site.data.keyword.ihsdbaas_mongodb_full}} instance in Sydney, use {{site.data.keyword.cloud_notm}} {{site.data.keyword.loganalysisshort_notm}} and {{site.data.keyword.at_short}} instances in Dallas for now.

### Changed: Frankfurt support for {{site.data.keyword.cloudaccesstrailshort}}
{: #at-frankfurt}

You can use your {{site.data.keyword.cloudaccesstrailshort}} instance in Frankfurt to view events of your {{site.data.keyword.ihsdbaas_mongodb_full}} instance in Frankfurt.

## 13 September 2019
{: #Sep13-2019} 

### Added: Free plans are available
{: #free-plans}

You can try out free plans for {{site.data.keyword.ihsdbaas_mongodb_full}}. Free plans are designed for evaluation purposes and are not suitable for production usage. If you create free-plan instances, note that they will be automatically deleted 30 days after creation.

## 28 August 2019
{: #Aug-2019}

### Added: {{site.data.keyword.ihsdbaas_mongodb_full}} expands into Frankfurt region
{: #frankfurt-region}

You can create {{site.data.keyword.ihsdbaas_mongodb_full}} resources in the Frankfurt region.

## 21 June 2019
{: #June-2019}

### {{site.data.keyword.ihsdbaas_mongodb_full}} is generally available
{: #ga-201906}

{{site.data.keyword.ihsdbaas_mongodb_full}} is an {{site.data.keyword.cloud_notm}} service that provides {{site.data.keyword.mongodb}} databases on demand. It offers a flexible and scalable platform that allows you to quickly and easily provision and manage your database of choice.

{{site.data.keyword.IBM_notm}} hosts your databases in a highly available and secure environment.

For more information, see [Getting started with {{site.data.keyword.cloud_notm}} {{site.data.keyword.ihsdbaas_mongodb_full}}](/docs/services/hyper-protect-dbaas-for-mongodb?topic=hyper-protect-dbaas-for-mongodb-gettingstarted).
