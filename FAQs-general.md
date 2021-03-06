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


# General FAQs
{: #faqs-general}

You can use the following FAQs to help you with {{site.data.keyword.cloud}} {{site.data.keyword.ihsdbaas_mongodb_full}}. To find all FAQs for {{site.data.keyword.cloud_notm}}, see our [FAQ library](/docs/faqs).
{: shortdesc}

## What's {{site.data.keyword.mongodb}}?
{: #whats-mongodb}
{: faq}

{{site.data.keyword.mongodb}} is a document database. It stores data in flexible, JSON-like documents. For more information, see [What is {{site.data.keyword.mongodb}}](https://www.mongodb.com/what-is-mongodb){: external}.

## Why do you use {{site.data.keyword.mongodb}} Enterprise instead of {{site.data.keyword.mongodb}} Community?
{: #why-mongodb-enterprise}
{: faq}

{{site.data.keyword.mongodb}} Enterprise provides a higher level of security and more features than the {{site.data.keyword.mongodb}} Community edition, including auditing, in-memory speed, support for enterprise software integration, etc. For more information, see [MongoDB Enterprise Server](https://www.mongodb.com/download-center/enterprise){: external}.

## What database types does {{site.data.keyword.ihsdbaas_full}} support?
{: #supported-databases}
{: faq}

{{site.data.keyword.postgresql}} and {{site.data.keyword.mongodb}} EE (see [{{site.data.keyword.ihsdbaas_postgresql_full}}](/docs/hyper-protect-dbaas-for-postgresql?topic=hyper-protect-dbaas-for-postgresql-gettingstarted#postgresql_supported_version) and [{{site.data.keyword.ihsdbaas_mongodb_full}}](/docs/hyper-protect-dbaas-for-mongodb?topic=hyper-protect-dbaas-for-mongodb-gettingstarted#mongodb_supported_version)).



## What's Secure Service Container?
{: #whats-secure-service-container}
{: faq}

{{site.data.keyword.ihsdbaas_full}} is built with [{{site.data.keyword.IBM_notm}} Secure Service Container (SSC)](https://www.ibm.com/us-en/marketplace/secure-service-container){: external} technology. SSC provides the base infrastructure for an integration of operating system, middleware and software components. They're packaged to work autonomously and provide core services and infrastructure with a focus on consumability and security. It protects data and applications from internal or external threats, including misuse of privileged infrastructure admin credentials.  

## What's pervasive encryption?
{: #what-is-pervasive-encryption}
{: faq}

{{site.data.keyword.ihsdbaas_full}} is built on {{site.data.keyword.IBM_notm}} LinuxONE, which provides pervasive encryption of data at rest and in transit. Pervasive encryption is an infrastructure for an end-to-end data protection. In particular, it includes data volume encryption with protected and secure keys. For more information, see [Pervasive encryption](https://www.ibm.com/support/knowledgecenter/linuxonibm/liaaf/lnz_r_crypt.html){: external}.

## How is {{site.data.keyword.ihsdbaas_full}} different from other cloud databases, including {{site.data.keyword.cloud_notm}} databases?
{: #hyper-protect-dbaas-difference}
{: faq}
{: support}

Built on {{site.data.keyword.IBM_notm}} LinuxONE technology, {{site.data.keyword.ihsdbaas_full}} offers the highest level of protection for customer data in the industry. For more information about security, see [Securing your data in {{site.data.keyword.ihsdbaas_mongodb_full}}](/docs/hyper-protect-dbaas-for-mongodb?topic=hyper-protect-dbaas-for-mongodb-data-security). It also provides 2X performance compared to x86 based cloud databases. 

## Can I own and manage my data encryption keys?
{: #keep-or-bring-your-own-key}
{: faq}
{: support}

Yes, you can own and manage your data encryption keys by enabling the [integration with {{site.data.keyword.keymanagementserviceshort}}](/docs/hyper-protect-dbaas-for-mongodb?topic=hyper-protect-dbaas-for-mongodb-key-protect-byok) or [with {{site.data.keyword.hscrypto}}](/docs/hyper-protect-dbaas-for-mongodb?topic=hyper-protect-dbaas-for-mongodb-hpcs-byok) when you create a {{site.data.keyword.ihsdbaas_full}} service instance.
