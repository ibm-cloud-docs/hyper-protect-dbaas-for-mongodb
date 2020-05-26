---

copyright:
  years: 2019, 2020
lastupdated: "2020-05-21"

keywords: frequently asked questions, database

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
{:faq: data-hd-content-type='faq'}
{:external: target="_blank" .external}
{:support: data-reuse='support'}

# FAQs
{: #faqs}

You can use the following FAQs to help you with {{site.data.keyword.cloud}} {{site.data.keyword.ihsdbaas_mongodb_full}}. To find all FAQs for {{site.data.keyword.cloud_notm}}, see our [FAQ library](/docs/faqs).
{: shortdesc}

## General
{: #general}

### What's {{site.data.keyword.mongodb}}?
{: #whats-mongodb}
{: faq}

{{site.data.keyword.mongodb}} is a document database. It stores data in flexible, JSON-like documents. For more information, see [What is {{site.data.keyword.mongodb}}](https://www.mongodb.com/what-is-mongodb){: external}.

### Why do you use {{site.data.keyword.mongodb}} Enterprise instead of {{site.data.keyword.mongodb}} Community?
{: #why-mongodb-enterprise}
{: faq}

{{site.data.keyword.mongodb}} Enterprise provides a higher level of security and more features than the {{site.data.keyword.mongodb}} Community edition, including auditing, in-memory speed, support for enterprise software integration, etc. For more information, see [MongoDB Enterprise Server](https://www.mongodb.com/download-center/enterprise){: external}.

### What database types does {{site.data.keyword.ihsdbaas_full}} support?
{: #supported-databases}
{: faq}
{{site.data.keyword.mongodb}} EE and {{site.data.keyword.postgresql}} (see [{{site.data.keyword.ihsdbaas_postgresql_full}}](/docs/hyper-protect-dbaas-for-postgresql?topic=hyper-protect-dbaas-for-postgresql-gettingstarted)).

<!--## What are the next DB types supported (after {{site.data.keyword.postgresql}} and {{site.data.keyword.mongodb}})?

## Which DB version is included and when/how can I move to the latest?
How long can I stay on the current DB version until I have to move to the latest?-->

### What's Secure Service Container?
{: #whats-secure-service-container}
{: faq}

{{site.data.keyword.ihsdbaas_full}} is built with [{{site.data.keyword.IBM_notm}} Secure Service Container (SSC)](https://www.ibm.com/us-en/marketplace/secure-service-container){: external} technology. SSC provides the base infrastructure for an integration of operating system, middleware and software components, which are packaged to work autonomously and provide core services and infrastructure with a focus on consumability and security. It protects data and applications from internal or external threats, including misuse of privileged infrastructure admin credentials.  

### What's pervasive encryption?
{: #what-is-pervasive-encryption}
{: faq}

{{site.data.keyword.ihsdbaas_full}} is built on the {{site.data.keyword.IBM_notm}} LinuxONE platform, which provides pervasive encryption of data at rest and in transit. Pervasive encryption is an infrastructure for an end-to-end data protection. In particular, it includes data volume encryption with protected and secure keys. For more information, see [Pervasive encryption](https://www.ibm.com/support/knowledgecenter/linuxonibm/liaaf/lnz_r_crypt.html){: external}.

### How is {{site.data.keyword.ihsdbaas_full}} different from other cloud databases, including {{site.data.keyword.cloud_notm}} databases?
{: #hyper-protect-dbaas-difference}
{: faq}
{: support}

Built on {{site.data.keyword.IBM_notm}} LinuxONE technology, {{site.data.keyword.ihsdbaas_full}} offers the highest level of protection for customer data in the industry. For more information about security, see [Securing your data in {{site.data.keyword.ihsdbaas_mongodb_full}}](/docs/hyper-protect-dbaas-for-mongodb?topic=hyper-protect-dbaas-for-mongodb-mng-data). It also provides 2X performance compared to x86 based cloud databases. 

### Can I own and manage my data encryption keys?
{: #keep-or-bring-your-own-key}
{: faq}
{: support}

Yes, you can own and manage your data encryption keys by enabling the [integration with {{site.data.keyword.keymanagementserviceshort}}](/docs/hyper-protect-dbaas-for-mongodb?topic=hyper-protect-dbaas-for-mongodb-key-protect-byok) or [with {{site.data.keyword.hscrypto}}](/docs/hyper-protect-dbaas-for-mongodb?topic=hyper-protect-dbaas-for-mongodb-hpcs-byok) when you create a {{site.data.keyword.ihsdbaas_full}} service instance.

### Where can I find detailed pricing information?
{: #pricing-info}
{: faq}

You can find the pricing information on the [service creation page](https://cloud.ibm.com/catalog/services/hyper-protect-dbaas-for-mongodb){: external}.

<!--## Is there a pricing example I can refer to?

## Is there a way to deploy the free-plan without providing credit card information?-->

## Usage
{: #usage}

### How can I prevent data loss from hardware failure?
{: #protect-from-failure}
{: faq}
{: support}

{{site.data.keyword.ihsdbaas_mongodb_full}} provides [automatic in-region data redundancy and failover](/docs/hyper-protect-dbaas-for-mongodb?topic=hyper-protect-dbaas-for-mongodb-ha-dr#in-region-redundancy-failover) and [automatic database backups in all availability zones](/docs/hyper-protect-dbaas-for-mongodb?topic=hyper-protect-dbaas-for-mongodb-ha-dr#automatic-daily-backups). It also supports [manual cross-region backups](/docs/hyper-protect-dbaas-for-mongodb?topic=hyper-protect-dbaas-for-mongodb-ha-dr#cross-region-backups) to prepare for the disaster scenario where the entire region fails.

### Do I need to enable the replication to secondary nodes manually?
{: #replication-by-default}
{: faq}
{: support}

No. By default, your {{site.data.keyword.ihsdbaas_full}} service instance consists of three nodes, one primary and two secondary nodes in three different availability zones in the {{site.data.keyword.cloud_notm}} region. The data in your primary node is automatically replicated to secondary nodes (replicas) with low latency.

### Can {{site.data.keyword.ihsdbaas_full}} back up my data automatically?
{: #automatic-backup}
{: faq}
{: support}

Yes. {{site.data.keyword.ihsdbaas_full}} does [automatic database backups](/docs/hyper-protect-dbaas-for-mongodb?topic=hyper-protect-dbaas-for-mongodb-ha-dr#automatic-daily-backups) in all availability zones in the region of your service instance every day. You can restore your data from backups in the last seven days.

### Where can I find usage and billing information?
{: #metering-and-billing}
{: faq}
{: support}

Select **Manage > Billing and usage** on the top menu bar in the {{site.data.keyword.cloud_notm}} dashboard. For more information, see [How you're charged](/docs/billing-usage?topic=billing-usage-charges#charges).
