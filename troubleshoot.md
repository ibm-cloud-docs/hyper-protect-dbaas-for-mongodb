---

copyright:
  years: 2019, 2020
lastupdated: "2020-02-14"

keywords: troubleshoot, troubleshooting, can't get cluster id, Unable to obtain plug-in’s metadata, cannot connect from Hyper Protect Virtual Servers, get help

subcollection: hyper-protect-dbaas-for-mongodb

---

{:tsSymptoms: .tsSymptoms}
{:tsCauses: .tsCauses}
{:tsResolve: .tsResolve}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:note:.deprecated}
{:troubleshoot: data-hd-content-type='troubleshoot'}

# Troubleshooting for {{site.data.keyword.ihsdbaas_mongodb_full}}
{: #troubleshoot}

General problems with using {{site.data.keyword.cloud}} {{site.data.keyword.ihsdbaas_mongodb_full}} might include failing to get Cluster ID. In many cases, you can recover from these problems by following a few easy steps.
{:shortdesc}

## Unable to get Cluster ID
{: #troubleshoot-clusterid}
{: troubleshoot}

You might receive the error **Get Cluster ID Failed — Cannot get cluster id from cookie. Make sure that cookie is enabled in your browser!** when you use the Safari browser to open the {{site.data.keyword.ihsdbaas_mongodb_full}} service instance dashboard.
{: tsSymptoms}

Cookies are blocked or cross-site tracking is prevented.
{: tsCauses}

In the **Privacy** preferences of your Safari browser, clear the **Website tracking** and the **Block all cookies** checkboxes, and then restart the browser. If you still get the same error, restart your computer and try again.
{: tsResolve}

## Got error message `Unable to obtain plug-in’s metadata. Error: signal: abort trap` when installing the DBaaS CLI components
{: #troubleshoot-cli-install-error}
{: troubleshoot}

You might receive the error **Unable to obtain plug-in’s metadata. Error: signal: abort trap** when you install the DBaaS CLI components on MacOS.
{: tsSymptoms}

Either the installed Python version is not correct (only Python 3.6.x is supported), or the `python-dev` is not included in the installed python package.
{: tsCauses}

Make sure to download the python package from https://www.python.org/downloads/mac-osx/ and install Python again.
{: tsResolve}

## Failed to connect from {{site.data.keyword.hpvs}} within the same region
{: #troubleshoot-hpvs-connection}
{: troubleshoot}

You might receive a connection failed message or warnings on connections in your logs when you try to connect to an instance of {{site.data.keyword.ihsdbaas_mongodb_full}} from your application that is running in an instance of {{site.data.keyword.hpvs}} within the same {{site.data.keyword.cloud_notm}} region.
{: troubleshoot}

The {{site.data.keyword.ihsdbaas_mongodb_full}} connection string contains host names that are mapping to public IP addresses, which cannot be used to connect from within the same region.
{: tsSymptoms}

The domain names are resolved incorrectly to the public IP address, which cannot be used to connect from within the same region.
{: tsCauses}

Before {{site.data.keyword.ihsdbaas_mongodb_full}} provides a long-term solution, you can select different regions for your virtual servers and the MongoDB instances. For example, if your virtual servers are in `us-south` (Dallas), you need to create Hyper Protect DBaaS MongoDB instances in either `eu-de` (Frankfurt) or `au-syd` (Sydney).
{: tsResolve}

## Getting help and support
{: #getting-help}
{: troubleshoot}

If you still have problems with using {{site.data.keyword.cloud}} {{site.data.keyword.ihsdbaas_mongodb_full}}, see [Getting help and support](/docs/hyper-protect-dbaas-for-mongodb?topic=hyper-protect-dbaas-for-mongodb-getting-help-and-support).
