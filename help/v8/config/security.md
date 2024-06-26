---
title: Campaign security best practices
description: Get started with Campaign security best practices
feature: Privacy, PI
role: Developer
level: Beginner
exl-id: 1d593c8e-4b32-4902-93a7-7b18cef27cac
---
# Campaign security best practices {#ac-security}

At Adobe, we take the security of your digital experience very seriously. Security practices are deeply ingrained into our internal software development and operations processes and tools and are rigorously followed by our cross-functional teams to prevent, detect, and respond to incidents in an expedient manner.

Furthermore, our collaborative work with partners, leading researchers, security research institutions, and other industry organizations helps us keep up to date with the latest threats and vulnerabilities and we regularly incorporate advanced security techniques into the products and services we offer.

## Privacy

Privacy configuration and hardening is a key element of security optimization. Here are some best practices to follow regarding privacy:

* Protect your customer Personal Information (PI) by using HTTPS instead of HTTP
* Use [PI view restriction](../dev/restrict-pi-view.md) to protect privacy and prevent data from being misused
* Make sure that encrypted passwords are restricted
* Protect the pages that might contain personal information such as mirror pages, web applications, etc.


>[!NOTE]
>
>As a Managed Cloud Services user, Adobe will work with you to implement these configurations on your environment.


## Access management

Access management is an important part of security hardening. Here are some of the main best practices:

* Create enough security groups
* Check that each operator has the appropriate access rights

Learn more about permissions in [this section](../start/gs-permissions.md)

## Coding guidelines

When developing in Adobe Campaign (workflows, Javascript, JSSP, etc.), always follow these guidelines:

* **Scripting**: try to avoid SQL statements, use parameterized functions instead of string concatenation, avoid SQL injection by adding the SQL functions to use to the allow list.

* **Secure the data model**: use named rights to limit operator actions, add system filters (sysFilter)

* **Add captchas in web applications**: add captchas in your public landing pages and subscription pages.

Learn more in [Adobe Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/installing-campaign-classic/security-privacy/scripting-coding-guidelines.html#installing-campaign-classic){target="_blank"}.


## Personalization

When adding personalized links to your content, always avoid having any personalization in the hostname part of the URL to avoid potential security gaps. The following examples should never be used in all URL attributes <`a href="">` or `<img src="">`:

* `<%= url >`
* `https://<%= url >`
* `https://<%= domain >/path`
* `https://<%= sub-domain >.domain.tld/path`
* `https://sub.domain<%= main domain %>/path`

## Data restriction

You have to make sure that the encrypted passwords will not be accessible by a low privilege authenticated user. To do that, there are two main ways: restrict access to password fields only or to the entire entity.

This restriction allows you to remove passwords fields but leaves the external account accessible from the interface for all users. Learn more in [this page](../dev/restrict-pi-view.md).

1. Go in **[!UICONTROL Administration]** > **[!UICONTROL Configuration]** > **[!UICONTROL Data schemas]**.

1. Create a new **[!UICONTROL Extension of a schema]**.

1. Choose **[!UICONTROL External Account]** (extAccount).

1. In the last screen, you can edit your new srcSchema to restrict access to all password fields:

    You can replace the main element (`<element name="extAccount" ... >`) by:

    ```
    <element name="extAccount">
        <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="password"/>
        <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="clientSecret"/>
   
        <element name="s3Account">
            <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="awsSecret"/>
        </element>
        <element name="wapPush">
            <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="password"/>
            <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="clientSecret"/>
        </element>
        <element name="mms">
            <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="password"/>
            <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="clientSecret"/>
        </element>
    </element>
    ```

    So your extended srcSchema can look like:

    ```
    <...>
        <element name="extAccount">
            <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="password"/>
            <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="clientSecret"/>
  
            <element name="s3Account">
                <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="awsSecret"/>
            </element>
            <element name="wapPush">
                <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="password"/>
                <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="clientSecret"/>
            </element>
            <element name="mms">
                <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="password"/>
                <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="clientSecret"/>
            </element>
        </element>
    <...> 
    ```

    >[!NOTE]
    >
    >You can replace `$(loginId) = 0 or $(login) = 'admin'` by `hasNamedRight('admin')` to let all users with admin right see these passwords.


## Access management

Access management is an important part of security hardening. Here are some of the main best practices:

* Create enough security groups
* Check that each operator has the appropriate access rights

Learn more about permissions in [in this section](../start/gs-permissions.md).

## Coding guidelines

When developing in Adobe Campaign (workflows, Javascript, JSSP, etc.), always follow these guidelines:

* **Scripting**: try to avoid SQL statements, use parameterized functions instead of string concatenation, avoid SQL injection by adding the SQL functions to use to the allow list.

* **Secure the data model**: use named rights to limit operator actions, add system filters (sysFilter)

* **Add captchas in web applications**: add captchas in your public landing pages and subscription pages.

Learn more in [Adobe Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/installing-campaign-classic/security-privacy/scripting-coding-guidelines.html#installing-campaign-classic){target="_blank"}.
