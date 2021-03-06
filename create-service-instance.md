---

copyright:
  years: 2019, 2021
lastupdated: "2021-06-07"

keywords: database cluster, create service instance, DBaaS dashboard

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
{:terraform: .ph data-hd-interface='terraform'}
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


# Creating a service instance
{: #create-service}

You can create your {{site.data.keyword.cloud}} {{site.data.keyword.ihsdbaas_mongodb_full}} service instance through the UI, CLI, and API.
{: shortdesc}

## Before you begin
{: #create-service-prerequisite}

Make sure you are familiarized with the following information. **Especially if you want to use your own encryption key or use private endpoints**, you need to follow the instructions in the corresponding topics **before** you create a service instance.
{: note}

- You can create a 30-day free plan service instance with three types of accounts: [Pay-As-You-Go, Subscription](/docs/account?topic=account-accounts), or [trial accounts](/docs/account?topic=account-accountfaqs#freetrial) (trial accounts are available for faculty and students at accredited academic institutions). To check your account type, go to the [Account settings](https://cloud.ibm.com/account/settings){: external} page. If you have a Lite account, you need to [upgrade your account to a Pay-As-You-Go or Subscription account](/docs/account?topic=account-upgrading-account), or [convert it to a trial account](/docs/account?topic=account-accountfaqs#convertacct).

- Free plans are designed for evaluation purposes and are not suitable for production usage. Free-plan service instances will be automatically deleted 30 days after creation. Free plans follow [{{site.data.keyword.cloud_notm}} Service Level Agreements (SLAs)](https://www-03.ibm.com/software/sla/sladb.nsf/pdf/6605-18/$file/i126-6605-18_08-2019_en_US.pdf){: external}.

- For the flexible plan, billing is based on the total amount of resources that are allocated to your service instance. For more information about resources and pricing, see [Resource breakdown](/docs/hyper-protect-dbaas-for-mongodb?topic=hyper-protect-dbaas-for-mongodb-resources-scaling#resources-breakdown).

- If you want to create a service instance with your own encryption key, follow the instructions in [{{site.data.keyword.keymanagementserviceshort}} Integration](/docs/hyper-protect-dbaas-for-mongodb?topic=hyper-protect-dbaas-for-mongodb-key-protect-byok) or [{{site.data.keyword.hscrypto}} Integration](/docs/hyper-protect-dbaas-for-mongodb?topic=hyper-protect-dbaas-for-mongodb-hpcs-byok). You can select your own key only when you create the service instance. Otherwise, a randomly generated key is used by default.

- If you want to create a service instance with private endpoints, follow the instructions in [Securing your connection to {{site.data.keyword.ihsdbaas_mongodb_full}}](/docs/hyper-protect-dbaas-for-mongodb?topic=hyper-protect-dbaas-for-mongodb-service-connection#prereq-service-endpoint).

- In some cases, your service instance might be provisioned with two nodes available at first, which is considered successful provisioning because it doesn't affect the functioning of your cluster. The pending node will be provisioned automatically later. Metering for service instances with two nodes provisioned is the same as metering for three nodes.

## Creating a service instance in the UI
{: #webui-create-service}
{: ui}

1. [Log in to your {{site.data.keyword.cloud_notm}} account](https://cloud.ibm.com/login){: external}.
2. Click **Catalog** on the top menu bar to view the list of services that are available on the {{site.data.keyword.cloud_notm}}.
3. Type `{{site.data.keyword.ihsdbaas_full}}` into the search field. Click the **{{site.data.keyword.ihsdbaas_mongodb_full}}** tile.
4. Choose the free plan or the flexible plan. Enter the required values on the service creation page. For **Database admin password**, don't use special characters such as `&` and `#`. If you choose the flexible plan, select the initial allocation values of RAM, disk, and vCPU. To estimate your costs, click **Add to estimate** or **Estimate costs** and input your total allocation values. **Tags** are optional and can be added after you create the service instance. Don't use special characters such as `&` and `#` in your password.
5. Click **Create**. 

## Creating a service instance from the CLI
{: #cli-create-service}
{: cli}

1. [Set up the CLI.](/docs/hyper-protect-dbaas-for-mongodb?topic=hyper-protect-dbaas-for-mongodb-install-dbaas-cli-plugin)

2. To create a {{site.data.keyword.cloud_notm}} {{site.data.keyword.ihsdbaas_mongodb_full}} service instance, use the `ibmcloud resource service-instance-create` command, as shown in the following example. In Windows, it is recommended that you use a Bash terminal such as Cygwin or Git Bash to enter the command.
{: shortdesc}

```
ibmcloud resource service-instance-create MyDBaaSIns03 hyperp-dbaas-mongodb mongodb-flexible us-south -p '{"name":"DBaaSTestCLICluster03", "admin_name":"admin","password":"passWORD4User19", "confirm_password":"passWORD4User19", "cpu":2, "memory":"2GiB", "storage":"5GiB", "kms_instance":"crn:v1:bluemix:public:kms:us-south:a/5b9cd17284125db65be173928b05bd50:e0e6a08c-f751-45ce-835f-9db8d01ff54a::", "kms_key":"66f22ec7-1ca9-4ad4-bdae-4ad949470a7c", "db_version":"4.4"}'  --service-endpoints private
```
{: codeblock}

Where the parameters have the following definitions:

| Parameter        |  Definition                                                    |
| ---------------- |  -------------------------------------------------------------- |
| *MyDBaaSIns03*   |  The name of the service instance (replace with a name of your own choosing). |
| *hyperp-dbaas-mongodb* | The catalog name of {{site.data.keyword.ihsdbaas_mongodb_full}}. |
| *mongodb-flexible*  | The plan name. For a 30-day free trial, use `mongodb-free` and omit the values of cpu, memory, and storage in the `-p` JSON string.  |
| *us-south*            | The location of your new databases. Available regions are `us-south` (Dallas), `us-east` (Washington DC), `eu-de` (Frankfurt), and `au-syd` (Sydney). |
| *-p*               | A valid JSON string, which must contain the required parameters in Table 2. |
| *--service-endpoints* | Enter `private` or `public` for the *--service-endpoints* option. If you omit this option, you will create a service instance with public endpoints.|
{: caption="Table 1. Parameters that are used in creating a service instance" caption-side="top"}

| Parameter        |  Definition                                                    |
| ---------------- |  -------------------------------------------------------------- |
| *name* | The name of your database cluster. |
| *admin_name* | The administrator's user name of the database to be created. |
| *password* | The administrator's user password of the database to be created. You need to create a strong password with a minimum of **15 characters**, at least **one uppercase** character, **one lowercase** character, and **one digit**. Don't use special characters such as `&` and `#`. |
| *confirm_password* | The same password. |
| *cpu* | Total number of dedicated CPU cores. For the valid value range of *cpu*, *memory*, and *storage*, see the [value table](/docs/hyper-protect-dbaas-for-mongodb?topic=hyper-protect-dbaas-for-mongodb-resources-scaling#before-scaling). |
| *memory* | Total memory allocation in GiB. |
| *storage* | Total disk allocation in GiB. |
| *kms_instance* | (Optional) Valid CRN of the selected KMS (key management service) instance. |
| *kms_key* | (Optional, paired with *kms_instance*) UUID of the selected root key. |
| *db_version*| (Optional) Supports {{site.data.keyword.mongodb}} 4.4 only. |
{: caption="Table 2. -p parameters" caption-side="top"}

The *kms_instance* and *kms_key* parameters are required if you want to create a service instance with your own encryption key. {{site.data.keyword.ihsdbaas_mongodb_full}} doesn't verify the *kms_instance* and *kms_key* parameters from the CLI. Make sure you copy and paste the correct values in the same format as the example.
{: important}

After you enter the command, the state of the new service instance might temporarily appear as **inactive** because it takes a few minutes to prepare the cluster. To get an update of the cluster status, use the `ibmcloud resource service-instance` command.

```
ibmcloud resource service-instance MyDBaaSIns03
```
{: codeblock}

For more {{site.data.keyword.cloud_notm}} CLI commands, see the [REFERENCE section of the {{site.data.keyword.cloud_notm}} CLI documentation](/docs/cli?topic=cli-ibmcloud_cli).

## Creating a service instance with the API
{: #api-create-service}
{: api}

1. [Set up authentication to use the APIs.](/docs/hyper-protect-dbaas-for-mongodb?topic=hyper-protect-dbaas-for-mongodb-api-setup#api-auth)
2. For the detailed API request, see [{{site.data.keyword.ihsdbaas_full}} RESTful APIs](/apidocs/hyperp-dbaas/hyperp-dbaas-v3#create-service){: external}.

## Creating a service instance with Terraform
{: #terraform-create-service}
{: terraform}

Follow instructions in [Step 2. Work with Hyper Protect DBaaS for MongoDB resources in Terraform](/docs/hyper-protect-dbaas-for-mongodb?topic=hyper-protect-dbaas-for-mongodb-terraform-setup) to create a service instance. Complete Step 1 if you haven't set up Terraform before.

## What's next
{: #create-connect}

1. To connect to your databases, see [Connecting to databases](/docs/hyper-protect-dbaas-for-mongodb?topic=hyper-protect-dbaas-for-mongodb-gettingstarted#accessing-database-introduction).
2. To manage your service instance, see [Managing your service instance](/docs/hyper-protect-dbaas-for-mongodb?topic=hyper-protect-dbaas-for-mongodb-manage-service).

To even further strengthen security, it's suggested that you [update the database admin password](https://docs.mongodb.com/manual/reference/method/db.changeUserPassword/){: external} immediately after you create the service instance and connect to the databases. You need to follow the same rules to set the new password. The password needs to contain 15 characters minimum, at least one uppercase character, one lowercase character, and one digit. Don't use special characters such as `&` and `#`.
{: note}
