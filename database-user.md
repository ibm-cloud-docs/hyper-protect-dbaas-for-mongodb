---

copyright:
  years: 2019, 2020
lastupdated: "2020-10-13"

keywords: database user, Users page, user name

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

# Viewing information about database users
{: #database-users}

You can view information about your database users through the UI, the CLI, and the API. To manage the database users, use your database client.
{: shortdesc}

For more information about {{site.data.keyword.mongodb}} database roles and privileges, see [{{site.data.keyword.mongodb}} built-in roles](https://docs.mongodb.com/manual/reference/built-in-roles/){: external}.

For more information about **Auth Database**, see [Authentication Database](https://docs.mongodb.com/manual/core/security-users/#user-authentication-database){: external}.

## Viewing information about database users in the UI
{: webui-database-users}

In the service dashboard, select **Users** in the side navigation pane to view the information about your database users.

## Viewing information about database users from the CLI
{: cli-database-users}

Use the [commands](/docs/hyper-protect-dbaas-for-mongodb?topic=hyper-protect-dbaas-for-mongodb-dbaas_cli_plugin#user_cmds) to list all your database users in the service instance and get detailed information about the database users.

## Viewing information about database users with the API
{: api-database-users}

- Use the [request](/apidocs/hyperp-dbaas/hyperp-dbaas-v3#list-database-users){: external} to list all your database users in the service instance. 
- Use the [request](/apidocs/hyperp-dbaas/hyperp-dbaas-v3#get-database-user-details){: external} to get detailed information about the database users.
