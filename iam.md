---

copyright:
  years: 2019, 2020
lastupdated: "2020-05-21"

keywords: IAM, identity, access management, role

subcollection: hyper-protect-dbaas-for-mongodb

---

{:shortdesc: .shortdesc}
{:external: target="_blank" .external}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:codeblock: .codeblock}
{:tip: .tip}
{:note: .note}
{:term: .term}
{:important: .important}

# Managing access with IAM for {{site.data.keyword.ihsdbaas_mongodb_full}}
{: #iam}

As the owner of your {{site.data.keyword.cloud}} {{site.data.keyword.ihsdbaas_mongodb_full}} service instance, you can assign access to other users or services to use your service instance.
{: shortdesc}

Access to {{site.data.keyword.ihsdbaas_mongodb_full}} service instances is controlled by {{site.data.keyword.cloud_notm}} [Identity and Access Management (IAM)](#x7547040){: term}. Every user or service that accesses the {{site.data.keyword.ihsdbaas_mongodb_full}} service in your account must be assigned an [access policy](#x2853407){: term} with an IAM role defined. The policy determines what actions a user or service can perform within the context of the service instance that you select. The allowable actions are customized and defined by {{site.data.keyword.ihsdbaas_mongodb_full}} as operations that are allowed to be performed on the service. The actions are then mapped to IAM roles.

Two types of IAM roles can be assigned: platform management roles and service access roles. The following documentation focuses on service access roles defined by {{site.data.keyword.ihsdbaas_mongodb_full}}. For more information about platform management roles, see [Platform management roles](/docs/account?topic=account-userroles#platformroles). For more information about IAM access, see [IAM access](/docs/account?topic=account-userroles).

## IAM service access roles
{: #service-access-roles}

The following tables outline what actions each service access role allows for the {{site.data.keyword.ihsdbaas_mongodb_full}} service.

| Service Access Role | Action Description |
| --- |--- |
| Reader | Get DB cluster details<br>List DB users<br>Get DB user details<br>List DBs<br>List DB log files |
| Writer | Get DB cluster details<br>List DB users<br>Get DB user details<br>List DBs<br>List DB log files<br>Enable DB logging<br>Enable DB Monitoring<br> |
| Manager | Get DB cluster details<br>List DB users<br>Get DB user details<br>List DBs<br>List DB log files<br>Enable DB logging<br>Enable DB Monitoring<br>Download a DB log file |
{: caption="Table 1. IAM service access roles and actions" caption-side="top"}

| Action Description | Action |
| --- | --- |
| Get DB cluster details | hyperp-dbaas-mongodb.clusters.read |
| Enable DB logging | hyperp-dbaas-mongodb.logging.enable |
| Enable DB Monitoring| hyperp-dbaas-mongodb.monitoring.enable |
| List DB users | hyperp-dbaas-mongodb.users.list |
| Get DB user details | hyperp-dbaas-mongodb.users.read |
| List DBs | hyperp-dbaas-mongodb.databases.list |
| List DB log files | hyperp-dbaas-mongodb.logs.list |
| Download a DB log file | hyperp-dbaas-mongodb.logs.read |
{: caption="Table 2. IAM service access actions" caption-side="top"}

## Difference between IAM service access and database user privileges
{: #compare-IAM-dbuser-access}

IAM service access applies to {{site.data.keyword.ihsdbaas_mongodb_full}} service instances. It manages the authorization of the service APIs. Database user privileges (as you see on the **Users** page in the service dashboard) apply to databases within your database cluster.

## Managing access
{: #manage-access}

For detailed instructions on managing access for users or services, see [Managing access to resources](/docs/account?topic=account-assign-access-resources). To organize a set of users and service IDs into a single entity that makes it easy for you to assign access, see [Setting up access groups](/docs/account?topic=account-groups).

Expect a maximum 10-minute interval before the IAM authorization change is refreshed.
