---
title: Enhanced security add-on
description: Get started with the Campaign Enhanced security add-on
feature: Configuration
role: Developer
level: Experienced
hide: yes
hidefromtoc: yes
exl-id: 7c586836-82e1-45fb-9c28-18361572e1fa
---
# Enhanced security add-on {#enhanced-security}

To make your network connection more secure and provide improved security for your resources, [!DNL Adobe Campaign] offers a new **Enhanced security** add-on.

This add-on includes two ecosystem features:

* [Secure CMK integration](#secure-cmk-integration)

* [Secure VPN tunneling](#secure-vpn-tunneling)

These features are detailed below.

## Secure CMK integration {#secure-cmk-integration}

The **Secure Customer-Managed Key (CMK) integration** allows you to encrypt your instance and your data using your own key through your Amazon Web Services (AWS) account.

Customer managed keys are Key Management Service (KMS) keys in your AWS account that you create, own, and manage. You have full control over these KMS keys, and use them to encrypt and decrypt data. By making you responsible for generating and managing encryption keys, this capacity enables you to have more control over them, including revoking a key.

>[!CAUTION]
>
>In case you revoke a key, you must be aware of the impacts. [Learn more](#cmk-callouts)

To enable the CMK integration with Campaign, follow the steps below:

1. Connect to your [Amazon Web Services (AWS)](https://aws.amazon.com/){target="_blank"} account.

1. Generate a key with auto-rotation on using the AWS Key Management Service (KMS). [Learn how](https://docs.aws.amazon.com/kms/latest/developerguide/create-keys.html){target="_blank"}.

1. Apply the policy provided to you by Adobe into your AWS account, in order to grant access to your resources. [Learn more](https://docs.aws.amazon.com/kms/latest/developerguide/key-policy-services.html){target="_blank"}. <!--link TBC-->

1. Share your [Amazon Resource Name (key ARN)](https://docs.aws.amazon.com/kms/latest/developerguide/find-cmk-id-arn.html){target="_blank"} with [!DNL Adobe Campaign]. To do this, contact your Adobe representative. <!--or Adobe transition manager?-->

1. Create and test the Amazon EventBridge rules to enable the monitoring of your keys by Adobe.​ [Learn more](https://docs.aws.amazon.com/eventbridge/latest/userguide/eb-rules.html){target="_blank"}.

## Secure VPN tunneling {#secure-vpn-tunneling}

The **Secure Virtual Private Network (VPN) tunneling** is a site-to-site VPN that provides secure access for your data in transit over a private network, from your premises to the [!DNL Adobe Campaign] instance.

<!--As it connects two networks together, it is a site-to-site VPN.-->

To ensure High Availability (HA), it uses two tunnels to avoid any outage in case an issue happens on one tunnel.

Three use cases are supported:

* Federated Data Access (FDA) over VPN<!--to access your on-premise database from the Campaign instance over VPN-->

* Instance login over VPN from a thick client

* Instance SFTP access over VPN

>[!CAUTION]
>
>Only on-premise databases and AWS-compliant VPN devices are supported. [Learn more](#vpn-callouts)

To ensure proper use of this feature, follow the guidelines below:

* Set up your side VPN based on the Adobe-side VPN configuration.

* Keep both tunnels up for High Availability.

* Monitor your side tunnel.

* You must be the initiator of the tunnel, and be aligned to reinitiate the connection if the tunnel goes down.

* Set up a retry mechanism at your end in case connection failures happen.

## Guardrails {#callouts}

Some guardrails and limitations relating to the Enhanced security features are listed below.

* Make sure all of your Secure CMK integration / Secure VPN tunneling use cases are working.

<!--* Adobe shall reach out to you or your technical team if any issue is found on your side.

* Currently, when using Enhanced security features, any communication with Adobe must be performed manually via email.-->

* Adobe will be monitoring:

    * Your instance availability, and proceed with alerting if the key is not available.

    * The VPN tunnels, and proceed with alerting in case any issue arise.

### Secure CMK integration guardrails {#cmk-callouts}

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
    >If you delete the key and do not revert this action within 30 days, then all your data is permanently deleted and will be lost.​

### Secure VPN tunneling guardrails {#vpn-callouts}

* Currently, only on-premise databases are supported, such as<!--Richa to check the list with PM-->:

    * MySQL
    * Netezza 
    * Oracle 
    * SAP HANA 
    * SQL Server 
    * Sybase 
    * Teradata 
    * Hadoop via HiveSQL

* Only AWS-compliant VPN devices are supported. A list of compatible devices is available on [this page](https://docs.aws.amazon.com/vpn/latest/s2svpn/your-cgw.html#example-configuration-files){target="_blank"}<!--check which list should be communicated-->.

* VPN connectivity to third parties or external vendors is not supported.

* Adobe-managed additional VPNs to private Cloud databases are not included.
