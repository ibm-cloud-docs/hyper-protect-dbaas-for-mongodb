---

copyright:
  years: 2019, 2020
lastupdated: "2020-11-25"

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
{:term: .term}
{:external: target="_blank" .external}

# Managing your service instance
{: #manage-service}

You can manage your {{site.data.keyword.cloud}} {{site.data.keyword.ihsdbaas_mongodb_full}} service instance through the UI, the CLI, and the API.
{: shortdesc}

To scale your resources, see [Scaling RAM, disk, and vCPU](/docs/hyper-protect-dbaas-for-mongodb?topic=hyper-protect-dbaas-for-mongodb-resources-scaling).

## Viewing information about your service instance
{: #show_detail_service}

You can view information about your service instances, databases, users, and nodes. To enable logging and monitoring, see [Sending logs to {{site.data.keyword.la_full_notm}}](/docs/hyper-protect-dbaas-for-mongodb?topic=hyper-protect-dbaas-for-mongodb-sendlogs) and [Monitoring databases](/docs/hyper-protect-dbaas-for-mongodb?topic=hyper-protect-dbaas-for-mongodb-monitor).

### Viewing information in the UI
{: #webui-show-service}

1. In the {{site.data.keyword.cloud_notm}} dashboard, click **View resources** on the **Resource summary** pane, or click **Resource List** in the upper left corner, to display all your resources.
2. Select the service instance on the **Resource list** to display the service dashboard. On the **Manage** page, you can see the overall information and connection information of the service instance.
3. Select **Databases**, **Users**, or **Nodes** in the side navigation pane to view more information.

### Viewing information from the CLI
{: #cli-show-service}

- [List your service instances.](/docs/cli?topic=cli-ibmcloud_commands_resource#ibmcloud_resource_service_instances)
- [Show the details of your service instance.](/docs/cli?topic=cli-ibmcloud_commands_resource#ibmcloud_resource_service_instance)
- To view information about your databases, users, and nodes, use the DBaaS CLI plug-in commands in [DBaaS CLI reference](/docs/hyper-protect-dbaas-for-mongodb?topic=hyper-protect-dbaas-for-mongodb-dbaas_cli_plugin).

### Viewing information with the API
{: #api-show-service}

Use the [{{site.data.keyword.ihsdbaas_full}} RESTful APIs](/apidocs/hyperp-dbaas/hyperp-dbaas-v3#get-service-instances){: external} to list your service instances, get detailed information about your service instance, etc.

## Managing your service instance
{: #manage-service-how}

With the required access, you can rename, delete, add tags to, and export the access report (a list of users and services that have access to your resource) of your service instance.

For more information and detailed instructions on deleting (and restoring) your service instance, see [Deleting your data in {{site.data.keyword.ihsdbaas_mongodb_full}}](/docs/hyper-protect-dbaas-for-mongodb?topic=hyper-protect-dbaas-for-mongodb-data-security#data-delete).
{: important}

To assign access to other users or services to use your service instance, see [Managing access for {{site.data.keyword.ihsdbaas_mongodb_full}}](/docs/hyper-protect-dbaas-for-mongodb?topic=hyper-protect-dbaas-for-mongodb-iam).

### Managing your service instance in the UI
{: #webui-manage-service}

1. In the {{site.data.keyword.cloud_notm}} dashboard, go to the **Resource list** page.
2. Expand **Services**. Find the target service instance and click the overflow icon.
3. Select the action that you want to complete.

### Managing your service instance from the CLI
{: #cli-manage-service}

- [Rename your service instance.](/docs/cli?topic=cli-ibmcloud_commands_resource#ibmcloud_resource_service_instance_update)
- [Delete your service instance.](/docs/cli?topic=cli-ibmcloud_commands_resource#ibmcloud_resource_service_instance_delete)
- [Add tags to your service instance.](/docs/cli?topic=cli-ibmcloud_commands_resource#ibmcloud_resource_tag_attach)
- Downloading in the [UI](/docs/hyper-protect-dbaas-for-mongodb?topic=hyper-protect-dbaas-for-mongodb-manage-service#webui-manage-service) is only way to get your access report. 

### Managing your service instance with the API
{: #api-manage-service}

Use the [request](/apidocs/hyperp-dbaas/hyperp-dbaas-v3#delete-a-service-instance){: external} to delete your service instance.
