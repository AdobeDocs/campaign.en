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

Secure Customer-Managed Key (CMK) Integration allows you to encrypt your instance and your data using your own encryption keys in your AWS account<!--instead of Adobe-owned keys-->.

Making you responsible for generating and managing your keys, this capacity enables you to have more control over them.

You can also revoke a key. However, in that case, you must be aware of the impacts. [Learn more](#cmk-callouts)

To enable this feature, follow the steps below:

1. Make sure you have an [AWS](https://aws.amazon.com/){target="_blank"} account.

1. Generate a key using the AWS Key Management Service (KMS). [Learn how](https://docs.aws.amazon.com/kms/latest/developerguide/create-keys.html){target="_blank"}

1. Apply the policy provided to you by Adobe into your AWS account, in order to grant access to your resources. [Learn more](https://docs.aws.amazon.com/kms/latest/developerguide/key-policy-services.html){target="_blank"} <!--link TBC-->

1. Share your Amazon Resource Name (key ARN) with [!DNL Adobe Campaign]. To do this, contact your Adobe representative. <!--or Adobe transition manager?-->

1. Create and test the Amazon EventBridge rules to enable the monitoring of your keys by Adobe.​ [Learn more](https://docs.aws.amazon.com/eventbridge/latest/userguide/eb-rules.html){target="_blank"}

## Secure VPN tunneling {#secure-vpn-tunneling}

Goal = Provide secure access over private network from customer premise to Campaign instance
3 use cases:
    * FDA over VPN
    * Instance login over VPN from thick client
    * Instance SFTP access over VPN
Customer can access on-prem database over VPN (only on-prem DB supported)
Job provided by Adobe to configure VPN automatically - customer cannot do it in a self-serving manner.
There will be 2 tunnels in case issue on one tunnel > monitoring and alerting on those VPN tunnels

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

Done after provisioning and before go live
Customer needs to configure his side VPN based on Adobe side VPN configuration
VPN connectivity with new UI is out of scope