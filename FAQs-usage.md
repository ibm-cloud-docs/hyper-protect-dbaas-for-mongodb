---

copyright:
  years: 2019, 2021
lastupdated: "2021-05-12"

keywords: frequently asked questions, database

subcollection: hyper-protect-dbaas-for-mongodb

content-type: faq

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


# FAQs about usage
{: #faqs-usage}

You can use the following FAQs to help you with {{site.data.keyword.cloud}} {{site.data.keyword.ihsdbaas_mongodb_full}}. To find all FAQs for {{site.data.keyword.cloud_notm}}, see our [FAQ library](/docs/faqs).
{: shortdesc}

## How can I change my password?
{: #change-password}
{: faq}
{: support}

After you connect to the databases, follow the instructions in the [MongoDB documentation](https://docs.mongodb.com/manual/reference/method/db.changeUserPassword/){: external} to change the database admin password that you set when you created the service instance. You need to follow the same rules to set the new password. The password needs to contain 15 characters minimum, at least one uppercase character, one lowercase character, and one digit. Don't use special characters such as `&` and `#`.

## How can I prevent data loss from hardware failure?
{: #protect-from-failure}
{: faq}
{: support}

{{site.data.keyword.ihsdbaas_mongodb_full}} provides [automatic in-region data redundancy and failover](/docs/hyper-protect-dbaas-for-mongodb?topic=hyper-protect-dbaas-for-mongodb-high-availability-disaster-recovery#in-region-redundancy-failover) and [automatic database backups in all availability zones](/docs/hyper-protect-dbaas-for-mongodb?topic=hyper-protect-dbaas-for-mongodb-high-availability-disaster-recovery#automatic-daily-backups). It also supports [manual cross-region backups](/docs/hyper-protect-dbaas-for-mongodb?topic=hyper-protect-dbaas-for-mongodb-high-availability-disaster-recovery#cross-region-backups) to prepare for the disaster scenario where the entire region fails.

## Do I need to enable the replication to secondary nodes manually?
{: #replication-by-default}
{: faq}
{: support}

No. By default, your {{site.data.keyword.ihsdbaas_full}} service instance consists of three nodes, one primary and two secondary nodes in three different availability zones in the {{site.data.keyword.cloud_notm}} region. The data in your primary node is automatically replicated to secondary nodes (replicas) with low latency.

## Can {{site.data.keyword.ihsdbaas_full}} back up my data automatically?
{: #automatic-backup}
{: faq}
{: support}

Yes. {{site.data.keyword.ihsdbaas_full}} does [automatic database backups](/docs/hyper-protect-dbaas-for-mongodb?topic=hyper-protect-dbaas-for-mongodb-high-availability-disaster-recovery#automatic-daily-backups) in all availability zones in the region of your service instance every day. You can restore your data from backups in the last seven days.

## Where can I find usage and billing information?
{: #metering-and-billing}
{: faq}
{: support}

Go to **Manage > Billing and usage** in the {{site.data.keyword.cloud_notm}} console. For more information, see [Viewing your usage](/docs/billing-usage?topic=billing-usage-viewingusage).
