---
title: Enhanced security add-on
description: Get started with Campaign Enhanced security add-on
feature: 
role: Developer
level: Experienced

---
# Enhanced security add-on {#enhanced-security}

To make your network connection more secure and provide improved security for your resources, [!DNL Adobe Campaign] offers a new **Enhanced security** add-on.

This add-on currently includes two ecosystem features:

* [Secure CMK integration](#secure-cmk-integration)

* [Secure VPN tunneling](#secure-vpn-tunneling)

## Secure CMK integration {#secure-cmk-integration}

Secure Customer-Managed Key (CMK) Integration allows you to encrypt your instance and your data using your own key through your AWS account<!--instead of Adobe-owned keys-->. By making you responsible for generating and managing encryption keys, this capacity enables you to have more control over them, including revoking a key.

>[!CAUTION]
>
>In case you revoke a key, you must be aware of the impacts. [Learn more](#cmk-callouts)

To enable this feature, follow the steps below:

1. Make sure you have an [AWS](https://aws.amazon.com/){target="_blank"} account.

1. Generate a key using the AWS Key Management Service (KMS). [Learn how](https://docs.aws.amazon.com/kms/latest/developerguide/create-keys.html){target="_blank"}

1. Apply the policy provided to you by Adobe into your AWS account, in order to grant access to your resources. [Learn more](https://docs.aws.amazon.com/kms/latest/developerguide/key-policy-services.html){target="_blank"} <!--link TBC-->

1. Share your Amazon Resource Name (key ARN) with [!DNL Adobe Campaign]. To do this, contact your Adobe representative. <!--or Adobe transition manager?-->

1. Create and test the Amazon EventBridge rules to enable the monitoring of your keys by Adobe.​ [Learn more](https://docs.aws.amazon.com/eventbridge/latest/userguide/eb-rules.html){target="_blank"}

## Secure VPN tunneling {#secure-vpn-tunneling}

Secure VPN Tunneling provides a secure access for data in transit over a private network from your premises to the [!DNL Adobe Campaign] instance.

Three use cases are supported:

* FDA over VPN<!--to access your on-premise database from the Campaign instance over VPN-->

    >[!CAUTION]
    >
    >For FDA over VPB, only on-premise databases are supported. [Learn more](#vpn-callouts)

* Instance login over VPN from thick client

* Instance SFTP access over VPN

This is a site-to-site VPN only. To ensure continuous availability, there are two tunnels to avoid any outage in case an issue happens on one tunnel.

>[!NOTE]
>
>Only AWS-supported VPN devices are supported.<!--Richa to provide more information?-->

To ensure proper use of this feature, you must:

* Set up your side VPN based on the Adobe-side VPN configuration.

* Keep both the tunnels up for High Availability.

* Monitor your side tunnel.

* Be the initiator of the tunnel, and be aligned to reinitiate the connection if the tunnel goes down.

* Set up a retry mechanism at your end in case connection failures happen.

## Customer onboarding and enablement {#onboarding-and-enablement}

Goal = assist customer to setup CMK and VPN
Customer needs to set up AWS key to share information with us
We want to monitor the key > customer needs to have AWS bridge for us to monitor CMK
Customer needs to set up VPN on his side based on Adobe VPN configuration
On-call enablement
MSIO enablement
We will be auditing change logs too

## Callouts / Guardrails / Prerequisites {#callouts}

* Make sure all of your use cases are valid.

* At this stage, communication with Adobe must be performed manually via email.

Encryption is done at account level, not database level
Not through Control Panel (maybe for v2)
Customer needs to reach out through a ticket
    * Collaborative process > transition managers to help on that > manual communication via email
    * No CMK or VPN at initial provisioning It will be done post provisioning (before go live)


### CMK {#cmk-callouts}

* Adobe does not provide an AWS account. You must have your own AWS account and set it up to generate and share your key with Adobe.

* Only [AWS Key Management Service](https://docs.aws.amazon.com/kms/latest/developerguide/overview.html){target="_blank"} (KMS) keys are supported. No customer-generated keys outside KMS can be used.​

* Some downtime will be involved for the first-time setup. ​The downtime duration will depend on the size of your database.

* As you own and maintain the key, you must reach out to Adobe in case of any change to your key.​

* You can audit your key using [AWS CloudTrail](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-user-guide.html){target="_blank"} and revoke it if needed.​

* In case you revoke, disable or delete the key, your encrypted resources and instance become inaccessible until you revert the corresponding action.

>[!CAUTION]
>
>If you disable the key and do not revert this action within 7 days, your database can only be recovered from backup.
>
>If you delete the key and do not revert this action within 30 days, then all your data is permanently delete and will be lost.​

### VPN {#vpn-callouts}

* For the FDA over VPN use case, only on-premise databases are currently supported. The list is as follows<!--Richa to check the list with PM-->:

    * MySQL
    * Netezza 
    * Oracle 
    * SAP HANA 
    * SQL Server 
    * Sybase 
    * Teradata 
    * Hadoop via HiveSQL


Done after provisioning and before go live
Customer needs to configure his side VPN based on Adobe side VPN configuration
VPN connectivity with new UI is out of scope