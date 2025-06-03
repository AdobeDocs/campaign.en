---
title: Campaign security best practices
description: Get started with Campaign security best practices
feature: Privacy, PI
role: Developer
level: Beginner
exl-id: 1d593c8e-4b32-4902-93a7-7b18cef27cac
version: Campaign v8, Campaign Classic v7
---
# Campaign security best practices {#ac-security}

At Adobe, we take the security of your digital experience very seriously. Security practices are deeply ingrained into our internal software development and operations processes and tools and are rigorously followed by our cross-functional teams to prevent, detect, and respond to incidents in an expedient manner.

Furthermore, our collaborative work with partners, leading researchers, security research institutions, and other industry organizations helps us keep up to date with the latest threats and vulnerabilities and we regularly incorporate advanced security techniques into the products and services we offer.

## Privacy

To correctly handle privacy and manage personal data, work within the legislations applicable to the region(s) where you operate. Adobe Campaign's capabilities help you comply with the regulations listed in [this page](../start/privacy.md)

### Adobe Experience Cloud privacy {#experience-cloud-privacy}

Adobe Campaign is part of the Adobe Experience Cloud solutions. The way privacy is handled in Campaign obeys the Experience Cloud general principles, such as the following:

* **What information is collected when using Adobe Experience Cloud**

    As a company using Adobe Experience Cloud solutions, you choose what information to collect and send to your Adobe Experience Cloud account. Examples of the types of information that may be collected include web browsing activity, IP addresses, location information from mobile devices, campaign success rates, items purchased or placed in shopping cart, etc.

    >[!NOTE]
    >
    >As for all Adobe products, Campaign collects information about app and website users. For more on this, see the [Adobe Privacy Policy](https://www.adobe.com/privacy/policy.html).

* **How Adobe Experience Cloud is used to collect information**

    * Adobe Experience Cloud solutions use cookies and similar technologies, such as web beacons (also known as tags or pixels), to enable you to collect information. For more on cookies and tracking capabilities with Adobe Campaign, see [this section](#tracking-capabilities).
    * You may also use Adobe Experience Cloud technologies within your mobile apps. For more on sending mobile deliveries with Campaign, see [SMS channel](../send/sms/sms-channel.md) and Mobile app channel.

* **You users' privacy choices about your use of Adobe Experience Cloud**

    Adobe asks you to provide your customers privacy policies describing:

    * Your privacy practices in connection with Adobe Experience Cloud
    * How users can set their preferences for the collection or use of their information in connection with Adobe Experience Cloud

    >[!NOTE]
    >
    >As for all Adobe products, Campaign users can opt-out sharing information collected about them through apps and websites. For more on this, see the [Adobe Experience Cloud Usage Information FAQ](https://www.adobe.com/privacy/experience-cloud-usage-info-faq.html).

For further details on the Adobe Experience Cloud privacy, see [this page](https://www.adobe.com/privacy/marketing-cloud.html).

## Personal Data and Personas {#personal-data}

When managing Privacy, it is important to define what data should be handled with care and by whom.
* **Personal Data** is information that can directly or indirectly identify a living individual.
* **Sensitive Personal Data** is information related to an individual's race, political views, religious beliefs, criminal background, genetic information, health data, sexual preference, biometric information, as well as trade union membership.

When integrating Campaign with other Experience Cloud solutions where audiences can be transferred from one system to another, such as [Adobe Analytics](../connect/ac-aa.md), [Experience Cloud Audiences](../start/shared-audiences.md), Campaign Standard, or with other solutions through [CRM Connector](../../automation/workflow/crm-connector.md), you need to pay extra care to personal data protection.

The [main regulations](#privacy-regulations) refer to the different entities that manage data as follows:

* A **Data Controller** is the authority that determines the means and purpose of collecting, using, and sharing personal data.

* A **Data Processor** is any individual or party that collects, uses, or shares personal data as directed by the Data Controller.

* A **Data Subject** is any living individual whose personal data is being collected, used or shared, and who can be identified, directly or indirectly, by reference to that personal data.

Therefore, as a company collecting and sharing personal data, you are the Data Controller, your clients are the Data Subjects and Adobe Campaign acts as a Data Processor when handling their personal data as directed by you. Note that it is your responsibility as a Data Controller to handle the relationship with the Data Subjects such as when managing [privacy requests](#privacy-requests).

### Use case scenario {#use-case-scenario}

To illustrate how the different personas are interacting, here is an example of a high-level GDPR customer experience use case.

In this example, an airline company is the Adobe Campaign customer. This company is the **Data Controller** and all the clients of the airline company are **Data Subjects**. Laura in this particular case is a client of the airline company.

Here are the different personas used in this example:

* **Laura** is the **Data subject**. She is the recipient who receives messages from the airline company. Laura may be a frequent flyer, but may decide at some point that she does not want any personalized advertising or marketing messages from the airline company. She will ask the airline company (based on their process) to delete her frequent flier number.

* **Anne** is the **Data Controller** at the airline company. She receives Laura's request, retrieves useful IDs requested to identify the Data Subject and submits the request in Adobe Campaign.

* **Adobe Campaign** is the **Data Processor**.

![](assets/privacy-gdpr-flow.png)

Here is the general flow for this use case:

1. The **Data Subject** (Laura) sends a GDPR request to the **Data Controller**, via email, customer care or a web portal.

1. The **Data Controller** (Anne) pushes the GDPR request to Campaign via the interface or using an API.

1. Once the **Data Processor** (Adobe Campaign) receives the information, it takes action on the GDPR request and sends a response or acknowledgement to the **Data Controller** (Anne).

1. The **Data Controller** (Anne) then reviews the information and sends it back to the **Data Subject** (Laura).

## Data acquisition {#data-acquisition}

Adobe Campaign enables you to collect data, including personal and sensitive information. It is therefore essential that you receive and monitor consent from your recipients.

* Always have recipients agree to receive communications. To do this, keep honoring opt-out requests as quickly as possible and verify consent through a double opt-in process. For more on this, see [Create a subscription form with double opt-in](https://experienceleague.adobe.com/en/docs/campaign-classic/using/designing-content/web-forms/use-cases-web-forms){target=_blank}.
* Do not import fraudulent lists and use seed addresses to check that your client file is not being used fraudulently. For more on this, see [About seed addresses](https://experienceleague.adobe.com/en/docs/campaign-classic/using/sending-messages/using-seed-addresses/about-seed-addresses){target=_blank}.
* Through consent and rights management, you can track your recipients' preferences as well as manage who within your organization can access which data. For more on this, see [this section](#consent).
* Facilitate and manage Privacy requests from your recipients. For more on this, see [this section](#privacy-requests).

## Privacy management {#privacy-management}

Privacy management refer to all the processes and tools that can help you comply with Privacy regulations (GDPR, CCPA, etc.).

Adobe Campaign provides you with various sets of features dedicated to privacy management:
* Consent management, data Retention and user Roles. See [this section](#consent).
* Privacy requests (Right to Access and Right to be Forgotten). See [this section](#privacy-requests).
* Opt-out for the Sale of Personal Information (CCPA-specific).

The main Privacy capabilities in Campaign and an example of the personas involved are presented in [this section](https://helpx.adobe.com/campaign/kb/campaign-privacy-more.html#gdprpersonasandflow).

### Consent, Retention and Roles {#consent}

Originally, Adobe Campaign offers important features that are essential to Privacy:

* **Consent management**: Through the subscription management process, you can manage your recipients' preferences and track which recipients have opted-in to which type of subscriptions. For more on this, see [About subscriptions](../../automation/workflow/subscription-services.md).
* **Data retention**: All built-in standard log tables have pre-set retention periods, generally limiting their data storage to 6 months or less. Additional retention periods can be set up with workflows. For more on this, reach out to the Adobe consultants or technical administrators.
* **Rights management**: Adobe Campaign provides you with the ability to manage the rights assigned to the various Campaign operators via different pre-built or custom roles. This allows you to manage who within your company can access, modify or export different types of data. For more on this, see [About access management](https://experienceleague.adobe.com/en/docs/campaign-classic/using/installing-campaign-classic/security-privacy/access-management){target=_blank}.

### Privacy requests {#privacy-requests}

Adobe Campaign provides additional capabilities to help you facilitate your readiness as a Data Controller for certain Privacy requests:

* The **Right to Access** is the right for the Data Subject to obtain from the Data Controller confirmation as to whether or not personal data concerning them is being processed, where and why.

* The **Right to be Forgotten** (delete request) entitles the Data Subject to have the Data Controller erase their personal data.

The **Access** and **Delete** requests are presented in [this section](../start/privacy.md).

The implementation steps to create these requests are detailed in [this section](../start/privacy.md).

## Tracking capabilities {#tracking-capabilities}

### Cookies {#cookies}

Thanks to its tracking functionalities, Adobe Campaign enables you to track the browsing of your delivery recipients using three types of cookies: a session cookie and two permanent cookies.

* A **session** cookie: the **nlid** cookie contains the identifier of the email sent to the contact (**broadlogId**) and the identifier of the message template (**deliveryId**). It is added when the contact clicks a URL included in an email sent by Adobe Campaign and enables you to track their behavior on the web. This session cookie is erased automatically when the browser is closed. The contact can configure their browser to refuse cookies.

* Two **permanent** cookies: 
    * The **UUID** (Universal Unique IDentifier) cookie is shared between Adobe Experience Cloud solutions. It is set once until it disappears from the client browser when a new value is generated. This cookie enables you to identify the users who interact with the Experience Cloud solutions when they visit a website. It can be deposited by a landing page (to associate unknown customer activities to a recipient) or by a delivery. The description of this cookie is available on [this page](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-mc.html#ec-cookies).
    * The **nllastdelid** cookie (introduced in Campaign Classic 20.3) is a permanent cookie which contains the **deliveryId** of the last delivery that user clicked the link from. This cookie is used - when the session cookie is missing - to identify the tracking table that will be used.

Regulations such as the General Data Protection Regulation (GDPR) state that companies require the agreement of website users before installing any cookies.

* You must inform users that your sites are equipped with web tracking tools via an authorization request (that comes up over the page, for example) with a checkbox to authorize the use of cookies, or add a banner at the top of the first page they land on, etc.
* Pop-up windows should be avoided as they are often blocked by browsers.

### Message tracking {#message-tracking}

Adobe Campaign lets you track the emails sent and the behavior of your delivery recipients: opening, clicks on links, unsubscriptions, etc. For more on this, see [About messages](../start/gs-message.md).

To do this, add tracked links to your messages in order to measure the impact of your delivery and recipient behavior in the Tracking tab of the delivery dashboard. Tracking data is interpreted in the Tracking indicators report. To learn more about tracking, refer to [this page](../start/tracking.md).

### Web tracking {#web-tracking}

Adobe Campaign also lets you monitor how recipients browse your website: insert tracking tags to collect information and measure visits on web application pages.

The configuration of web tracking is explained in [this section](../start/tracking.md).

To further manage tracking, Adobe Campaign enables you to display an opt-out banner to stop tracking web behaviors of end users who opt-out of behavioral tracking. For more on this, see [Web application tracking opt-out](https://experienceleague.adobe.com/en/docs/campaign-classic/using/designing-content/web-applications/web-application-tracking-opt-out){target=_blank}.

<!--
Privacy configuration and hardening is a key element of security optimization. Here are some best practices to follow regarding privacy:

* Protect your customer Personal Information (PI) by using HTTPS instead of HTTP
* Use [PI view restriction](../dev/restrict-pi-view.md) to protect privacy and prevent data from being misused
* Make sure that encrypted passwords are restricted
* Protect the pages that might contain personal information such as mirror pages, web applications, etc.
-->

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
