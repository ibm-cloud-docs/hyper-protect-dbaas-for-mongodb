---

copyright:
  years: 2019, 2021
lastupdated: "2021-05-12"

keywords: high availability disaster recovery

subcollection: hyper-protect-dbaas-for-mongodb

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


# High availability and disaster recovery
{: #high-availability-disaster-recovery}

{{site.data.keyword.cloud}} {{site.data.keyword.ihsdbaas_mongodb_full}} provides several ways to protect your data and help keep your applications operational.
{: shortdesc}

## Types of protection
{: #types-of-protection}

High Availability (HA) means providing the best possible continuous data availability after hardware failure to avoid impact on operations. Disaster Recovery (DR) means the ability to make all the data available on an alternative system as quickly as possible after a severe or extensive hardware failure.

{{site.data.keyword.ihsdbaas_mongodb_full}} provides [automatic in-region data redundancy and failover](/docs/hyper-protect-dbaas-for-mongodb?topic=hyper-protect-dbaas-for-mongodb-high-availability-disaster-recovery#in-region-redundancy-failover) by default. The service is offered in [Multi-Zone regions](#x9774820){: term} (Dallas, Washington DC, Frankfurt, and Sydney), each with three availability zones for redundancy.

To prepare for the disaster scenario where the entire region fails (broken network, for example) and the service in that region becomes unavailable, you need to define your own cross-region backup policy to restore your data in another available region. {{site.data.keyword.ihsdbaas_mongodb_full}} supports [manual cross-region backups](/docs/hyper-protect-dbaas-for-mongodb?topic=hyper-protect-dbaas-for-mongodb-high-availability-disaster-recovery#cross-region-backups).

{{site.data.keyword.ihsdbaas_mongodb_full}} does [automatic database backups in all availability zones](/docs/hyper-protect-dbaas-for-mongodb?topic=hyper-protect-dbaas-for-mongodb-high-availability-disaster-recovery#automatic-daily-backups) in the region of your service instance every day. You can restore your data from backups in the last seven days.

The following documentation gives more details on each type of protection.

## Automatic in-region data redundancy and failover
{: #in-region-redundancy-failover}

You can create {{site.data.keyword.ihsdbaas_mongodb_full}} service instances in one of the supported {{site.data.keyword.cloud_notm}} regions, which represent the geographic area where your service requests are handled and processed. By default, your {{site.data.keyword.ihsdbaas_mongodb_full}} service instance consists of three nodes, one primary and two secondary nodes in three different availability zones in the {{site.data.keyword.cloud_notm}} region.

The data in your primary node is automatically replicated to secondary nodes (replicas) with low latency. You don't need to do anything to enable the replication. When your primary node fails, a secondary node in the cluster is elected as the primary to prevent your applications from being affected. In this way, you have automatic high availability within one region for your data.

## Manual cross-region backups
{: #cross-region-backups}

To protect your data across more than one region against the disaster scenario where the entire region fails, you need to define your own cross-region backup policy. To create cross-region data redundancy, you need to have regular backups of your complete databases from your service instance in a region. When the region is unavailable, you can provision a new service instance in another available region to restore your database manually. For detailed instructions on backing up and restoring your data in a different region, see [Backing up and restoring your databases using IBM Cloud Object Storage](/docs/hyper-protect-dbaas-for-mongodb?topic=hyper-protect-dbaas-for-mongodb-backup_mongodb_databases).

Time of restoration varies, depending on the size of your data and network condition. For your reference, it takes about 45 minutes to restore data of 10G from Poughkeepsie to a {{site.data.keyword.ihsdbaas_mongodb_full}} service instance deployed in Dallas. Therefore, to minimize the impact of region-wide failures, you need to plan ahead, for example, by having a service instance in a second region as a cold standby.

## Automatic database backups in all availability zones
{: #automatic-daily-backups}

[Automatic in-region data redundancy and failover](/docs/hyper-protect-dbaas-for-mongodb?topic=hyper-protect-dbaas-for-mongodb-high-availability-disaster-recovery#in-region-redundancy-failover) provide high availability within one region. [Manual cross-region backups](/docs/hyper-protect-dbaas-for-mongodb?topic=hyper-protect-dbaas-for-mongodb-high-availability-disaster-recovery#cross-region-backups) provide a disaster recovery capability that helps you protect against failures across an entire region. Both of the HA/DR capabilities help you to maintain access to the current copy of your data.

You can also choose to restore your data from automatic historical backups. {{site.data.keyword.ihsdbaas_mongodb_full}} automatically triggers a backup of your complete database once every 24 hours. These encrypted backups are available for the last seven days and redundantly available on local storage in all availability zones in the region of your service instance. If you want to restore one of the backups, see [Restoring your databases by IBM Support](/docs/hyper-protect-dbaas-for-mongodb?topic=hyper-protect-dbaas-for-mongodb-restore_mongodb_databases).
