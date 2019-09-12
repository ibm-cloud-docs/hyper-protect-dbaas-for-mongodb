---

copyright:
  years: 2019
lastupdated: "2019-09-13"

keywords: database cluster, create service instance, DBaaS dashboard

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

# Creating and managing service instances
{: #dbaas_webui_service}

## Creating a service instance
{: #dbaas_webui_create_service}

1. [Log in to your {{site.data.keyword.cloud_notm}} account](https://cloud.ibm.com/login){: external}.
2. Click **Catalog** on the top menu bar to view the list of services that are available on {{site.data.keyword.cloud_notm}}.
3. Type `{{site.data.keyword.ihsdbaas_full}}` into the search field. Click the **{{site.data.keyword.ihsdbaas_mongodb_full}}** tile.
4. Choose a pricing plan. Free plans are designed for evaluation purposes and are not suitable for production usage. If you create free-plan instances, note that they will be automatically deleted 30 days after creation. Free plans follow [{{site.data.keyword.cloud_notm}} Service Level Agreements (SLAs)](https://www-03.ibm.com/software/sla/sladb.nsf/pdf/6605-18/$file/i126-6605-18_08-2019_en_US.pdf){: external}.
5. Enter the required values on the provisioning page and click **Create**. **Tags** is optional and can be added after you create the instance.

  The database administrator does not have SUPERUSER authority. The authorities of the database administrator are limited to INHERIT, CREATEROLE, CREATEDB, LOGIN, and REPLICATION.
  {: note}
6. Refresh the **Resource List** page after several minutes. When the status of the service instance is **Provisioned**, the instance is ready to use.

  To even further strengthen security, it is suggested that you update the **database admin password** immediately after the service instance is provisioned. You need to follow the same rules that are previously mentioned to set the new password.
  {: note}

## Viewing detailed information of a service instance
{: #dbaas_webui_show_detail_service}

1. In the {{site.data.keyword.cloud_notm}} dashboard, click **View resources** on the **Resource summary** pane, or click the **Resource List** button in the upper left corner, to display all your resources.
2. Click the service instance on the **Resource list** to display the service dashboard.
3. On the **Overview** tab page, you can see the overall information of the service instance.
4. Select the **Instances** tab to view the detailed information of each replica.

## Renaming, deleting, or adding tags to a service instance
{: #dbaas_webui_delete_service}

1. Navigate to the **Resource list** page.
2. In the **Services** drop-down list, Click the three dots button on the right of the target service instance.
3. Select the action you want to complete.
