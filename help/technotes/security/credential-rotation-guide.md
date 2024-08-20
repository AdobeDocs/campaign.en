---
product: campaign
title: Technical Note - Credential Rotation Guide
description: Adobe Campaign Technical Note - Credential Rotation Guide
hide: yes
hidefromtoc: yes
exl-id: 0848ee2d-3506-4167-9aea-a1589aa82805
---
# Technical Note: Credential Rotation Guide {#ac-customer-credentials}

As a customer, you are responsible for replacing your credentials with a new set periodically to mitigate the risk of compromise. 

## Adobe Campaign Options credentials {#ac-options-credentials}

From Adobe Campaign Explorer, the **Administration > Platform > Options** node allows you to make amendments to Adobe Campaign options. If you have stored some credentials here, please make sure to rotate them.

![](assets/technote-2.png)

## External Account credentials {#ac-accounts-credentials}

The **Administration > Platform > External Accounts** node allows you to make amendments to Adobe Campaign external accounts. 

Please rotate all your credentials saved in the external accounts.  

>[!CAUTION]
>
>**Do not** modify the Adobe managed credentials. Any External accounts having `adobe` related server should not be modified.

![](assets/technote-1.png)

For the specific technical `mc*` (ex: mc1, mc2, etc) and `Interaction*` (ex: interaction1, interaction2, etc ) operators, any of the two approach below can followed: 

1. Adobe can change the credentials for such operators and share it with you. Note that all the integrations using these operators will stop working until the credentials for these operators get updated on your side.

1. Adobe can create **new** operators corresponding to each existing operators and share them with you. Adobe will delete all occurrences of old operators after you switched to these new operators. 


## Mobile Services Private Key/Certificate  {#ac-key-credentials}

For rotation of the mobile services related Private keys and Certificate, refer to the links below. 

* For Android, refer to [this documentation](https://experienceleague.adobe.com/en/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application-android){target="_blank"}.
    Browse to the **Create the Android mobile application > Configure the API version** section.

* For iOS, refer to [this documentation](https://experienceleague.adobe.com/en/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application){target="_blank"}.
    Browse to the **Create iOS mobile app->Authentication mode** section. 

## GPG Keys {#ac-gpg-credentials}

For the rotation of GPG keys, the following steps need to be followed: 

1. Decrypt the existing data using the existing key. [Learn more](https://experienceleague.adobe.com/en/docs/control-panel/using/instances-settings/gpg-keys-management#decrypting-data){target="_blank"}.

1. Create a new GPG key pair. Learn more about GPG key management in [this documentation](https://experienceleague.adobe.com/en/docs/control-panel/using/instances-settings/gpg-keys-management#decrypting-data){target="_blank"}.

1. Replace existing GPG key usage in all workflows with the newly created key. 

1. Delete the existing GPG key.
