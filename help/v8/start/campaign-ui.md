---
title: Discover Campaign user interface
description: Learn how to browse and use Campaign user interface
feature: Overview
role: User
level: Beginner
version: Campaign v8, Campaign Classic v7
exl-id: a7846b95-7570-4dce-b3f4-d3cc23eefcac
---
# Discover the user interface {#ui-client-console}

You can access to Adobe Campaign via its client console or its Web user interface. You can also use APIs to manage data and perform tasks in your Campaign platform.

* **Client console** - Campaign client console is a native application which communicates with the Adobe Campaign application server through standard internet protocols, such as SOAP and HTTP. Campaign client console centralizes all capabilities and settings, and requires minimal bandwidth as it relies on a local cache. Designed for easy deployment, Campaign client console can be deployed from an internet browser, updated automatically, and does not require any specific network configuration as it only generates HTTP(S) traffic. [Learn more](#ui-access)

    Learn how to install and configure Campaign client console in [this section](../start/connect.md).

* **Web access** - Adobe Campaign web access capabilities lets you access to a subset of Campaign features with a web browser, using an HTML user interface. Use this web interface to access reports, control and validate messages, access monitoring dashboards, and more.  Learn more about Campaign Web Access [in this section](../start/connect.md#web-access).

* **APIs** - To address more use cases, the system can be called from external applications using the Web Services APIs exposed via the SOAP protocol. Learn more about Campaign APIs [in this page](../dev/api.md).

* **Web user interface** - As a Campaign v8 user, starting v8.6.1 release, you now have access to a web environment, available through the central Adobe Experience Cloud user interface. You can then connect to Adobe Campaign from a web browser. This new interface lets you create, manage and execute key marketing actions. However, all Campaign capabilities are not available. [Learn more](#ac-web-ui).
    
    >[!AVAILABILITY]
    >
    >Campaign Web user interface is only available to Campaign v8 users connecting to Campaign with their Adobe ID. Learn more about [Adobe Identity Management System (IMS)](https://helpx.adobe.com/enterprise/using/identity.html){target="_blank"}.
    >

>[!CAUTION]
>
>This documentation is focused on Campaign Client console usage. As a Campaign v8 user, if you are using the Campaign Web user interface, refer to [this documentation](https://experienceleague.adobe.com/docs/campaign-web/v8/campaign-web-home.html){target="_blank"}.

## Work with the client console {#ui-access}

Campaign client console is a native application which communicates with the Adobe Campaign application server, through standard internet protocols, such as SOAP and HTTP. Campaign client console centralizes all capabilities and settings, and requires minimal bandwidth as it relies on a local cache. Designed for easy deployment, Campaign client console can be deployed from an internet browser, updated automatically, and does not require any specific network configuration as it only generates HTTP(S) traffic.  [Learn more about Campaign client console](../start/connect.md). 



>[!BEGINTABS]

>[!TAB Campaign v8]

Once you are connected to Campaign, you access the Adobe Campaign home page. In Campaign v8, use the central cards to browse the new Campaign Web user interface, and Campaign Control panel.

![Campaign v8 Client Console Home](assets/web-ui.png) 

>[!NOTE]
>
>If the Web user interface card is not displayed, ensure that the following fields are not left empty within your A[dobe Experience Cloud external account](../config/external-accounts.md): **Server**, **Tenant**, **Callback server**, and **Association mark**.

You can also access the [Campaign Control Panel](../config/self-service.md) from the home page. 

>[!TAB Campaign Classic v7] 

Once you are connected to Campaign, you access the Adobe Campaign home page with links and shortcuts to access capabilities, documentation, support website, and Campaign community.

![Campaign Classic v7 Client Console Home](assets/v7_user_interface_home.png) 


>[!ENDTABS]


You can also use a web browser to access Campaign. In this context, only a sub-set of Campaign capabilities are available. [Learn more](#web-browser)

### Browse the interface {#ui-browse}

Once you are connected to Campaign client console, browse the tabs in the upper section to access Campaign key capabilities:

![](assets/overview-home.png)

>[!NOTE]
>
>The list of core capabilities you can access depends on your permissions, and on your implementation.

For each capability, you can access the set of key features in the **[!UICONTROL Browsing]** section. The **[!UICONTROL More]** link lets you access all the other components.

For example, when browsing to the **[!UICONTROL Profiles and targets]** tab, you can access to the recipient lists, subscription services, existing targeting workflows and the shortcuts for creating all these components.

![](assets/overview-list.png)

When you select an element in the screen, it is loaded in a new tab so that you can easily browse content.

![](assets/new-tab.png)

### Create an element {#create-an-element}

Use shortcuts in the **[!UICONTROL Create]** section on the left of the screen to add new elements. You can also use the **[!UICONTROL Create]** button above the list to add new elements to the current list.

For example, on the delivery page, use the **[!UICONTROL Create]** button to create a new delivery.

![](assets/new-recipient.png)

<!--
## Use a web browser {#web-browser}

You can also access a subset of Campaign capabilities through the a web browser.

The web access interface is similar to the console interface. From a browser, you can use the same navigation and display features as in the console, but you can perform only a reduced set of actions on campaigns. For example, you can view and cancel campaigns, but you cannot modify campaigns. 

[Learn more about Campaign web access](../start/connect.md#web-access).-->

### Access Campaign Explorer {#ac-explorer-ui}

Browse Campaign Explorer to access all the Adobe Campaign capabilities and settings. 

![](assets/explorer.png) 

This workspace lets you access the Explorer tree to browse all features and options.

* The left section shows Campaign Explorer tree and lets you browse all components and settings of your instance - based on your permissions. You can add and customize folders as explained in [this page](../audiences/folders-and-views.md).

* The upper section shows the list of records in the current folder. These lists are fully customizable. [Learn more](../config/ui-settings.md)

* The lower section shows the details of the selected record. 


## Campaign Web user interface {#ac-web-ui}

As a Campaign v8 user, starting v8.6.1 release, you have access to a web environment, available through the central Adobe Experience Cloud user interface. Experience Cloud is Adobe's integrated family of digital marketing applications, products, and services. From its intuitive interface, you can quickly access your cloud applications, product features, and services. 

![Adobe Campaign Web User Interface Home Page](assets/ac-web-home.png)

>[!AVAILABILITY]
>
>Campaign Web user interface is only available to Campaign v8 users connecting to Campaign with their Adobe ID. Learn more about [Adobe Identity Management System (IMS)](https://helpx.adobe.com/enterprise/using/identity.html){target="_blank"}.
>

Learn more about the new Campaign Web User Interface in [this documentation](https://experienceleague.adobe.com/docs/campaign-web/v8/campaign-web-home.html){target="_blank"}. You can also visit the dedicated [Frequently Asked Questions page](https://experienceleague.adobe.com/en/docs/campaign-web/v8/start/faq){target="_blank"}, in Campaign Web User Interface documentation.

Additional and advanced capabilities, configuration and settings are only available in the client console. Learn more about capabilities available in both user interfaces [in Campaign Web user interface documentation](https://experienceleague.adobe.com/docs/campaign-web/v8/start/capability-matrix.html){target="_blank"}.


## Supported languages {#languages}

Languages supported depend on the user interface. 

* For Campaign client console interface, supported languages are:

    * English (UK)
    * English (US)
    * French
    * German
    * Japanese


    >[!CAUTION]
    >
    >The language is selected during the installation process, and **cannot be changed** afterwards. 

* For Campaign Web user interface supported languages, [refer to this page](https://experienceleague.adobe.com/docs/campaign-web/v8/start/connect-to-campaign.html#language-pref){target="_blank"}.

## Formats

Language affects dates and time formats. 

Main differences between US English and UK English are: 

<table> 
 <thead> 
  <tr> 
   <th> Formats<br /> </th> 
   <th> English (US)<br /> </th> 
   <th> English (EN)<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Date<br /> </td> 
   <td> Week starts on Sunday<br /> </td> 
   <td> Week starts on Monday<br /> </td> 
  </tr> 
  <tr> 
   <td> Short date<br /> </td> 
   <td> <p>%2M/%2D/%4Y</p><p><strong>ex: 09/25/2025</strong></p> </td> 
   <td> <p>%2D/%2M/%4Y</p><p><strong>ex: 25/09/2025</strong></p> </td> 
  </tr> 
  <tr> 
   <td> Short date with time<br /> </td> 
   <td> <p>%2M/%2D/%4Y %I:%2N:%2S %P</p><p><strong>ex: 09/25/2025 10:47:25 PM</strong></p> </td> 
   <td> <p>%2D/%2M/%4Y %2H:%2N:%2S</p><p><strong>ex: 25/09/2025 22:47:25</strong></p> </td> 
  </tr> 
 </tbody> 
</table>


## Additional Resources

* **[Work with Enumerations](../config/enumerations.md)** - Standardize field values with predefined drop-down lists for faster, more consistent data entry.
* **[Enumerations in schemas](../dev/schema-structure.md#enumerations)** - As a Campaign developer, use free, fixed, or database-based enumerations in your schemas to control field values.