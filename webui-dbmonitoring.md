---

copyright:
  years: 2019
lastupdated: "2019-09-23"

keywords: database monitoring, database cluster, database metrics

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

# Monitoring databases
{: #dbaas-webui-database-monitor}

After you have enabled database monitoring, you can view the database metrics using Grafana.
{: shortdesc}

## Before you begin
{: #webui-database-monitoring-byb}

1.  Be sure to have access to a Cloud Foundry organization and space in Dallas (us-south), Frankfurt (eu-de), or Sydney (au-syd).
    For information about how to obtain such access, see [Managing Cloud Foundry access](https://cloud.ibm.com/docs/iam?topic=iam-mngcf#mngcf){: external}.

2.  Make sure that all instances of the database cluster are running.

3.  In the {{site.data.keyword.cloud_notm}} {{site.data.keyword.ihsdbaas_mongodb_full}} dashboard, select the **Monitoring** tab.

## Enabling database monitoring
{: #webui-enable-database-monitoring}

In case the message **Monitoring is disabled** is displayed in the **Monitoring** tab:

1. Click **Enable**.
2. In the **Enable Monitoring** window, select your organization and space, then click **Submit**.


## Viewing database metrics
{: #webui-view-database-metrics}

There are two ways to view the metrics in Grafana:

- Copy the displayed link, then open a new tab or window and paste the link to the browser.
- Click **View in Grafana**.

To display the metrics in a new dashboard in Grafana, select the upper left Grafana icon, then select **Dashboards > New**.
It may take a while until your database cluster ID and instance IDs are displayed, and you might have to reload the dashboard.

For more information about using Grafana, see [{{site.data.keyword.cloud_notm}} Monitoring](/docs/services/cloud-monitoring?topic=cloud-monitoring-getting-started).

## Available metrics
{: #available-metrics}

The table describes all the available metrics for {{site.data.keyword.cloud_notm}} {{site.data.keyword.ihsdbaas_mongodb_full}} deployments.

| Metric | Description|
|----------|-----------|
| `memory-percent-used` | How much percent of memory that your deployment is using for the instance. |
{: caption="Table 1. {{site.data.keyword.cloud_notm}} {{site.data.keyword.ihsdbaas_mongodb_full}} metrics" caption-side="top"}
