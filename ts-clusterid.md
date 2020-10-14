---

copyright:
  years: 2019, 2020
lastupdated: "2020-10-14"

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
{:support: data-reuse='support'}

# Why can't I get cluster ID?
{: #troubleshoot-clusterid}
{: troubleshoot}
{: support}

You might receive the error **Get Cluster ID Failed — Cannot get cluster id from cookie. Make sure that cookie is enabled in your browser!** when you use the Safari browser to open the {{site.data.keyword.ihsdbaas_mongodb_full}} service instance dashboard.
{: tsSymptoms}

Cookies are blocked or cross-site tracking is prevented.
{: tsCauses}

In the **Privacy** preferences of your Safari browser, clear the **Website tracking** and the **Block all cookies** checkboxes, and then restart the browser. If you still get the same error, restart your computer and try again.
{: tsResolve}
