---
title: Send direct mails with Adobe Campaign
description: Get started with direct mail in Campaign
feature: Direct Mail
role: User
level: Beginner
exl-id: ff2be012-72f3-428d-a973-196fea7ec4ab
---
# Create direct mail deliveries

Direct mail deliveries let you generate an extraction file which contains data on the target population. You can then share this file with the provider who will deliver messages to the target populations.

Steps to generate the file are:

1. Create the delivery

    Create a direct mail delivery based on the template. You can duplicate and configure the **[!UICONTROL Deliver by direct mail (paper)]** built-in template.

    ![](../assets/do-not-localize/book.png) Learn more in [Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-direct-mail/creating-a-direct-mail-delivery.html){target="_blank"}

1. Define the audience

    The recipient profiles must contain at least their names and postal addresses.

    Postal addresses are calculated fields. An address can contain up to six lines by default: the first contains the first name and last name, the next lines contain the postal address (road etc.), and the last line contains the ZIP/Postal code and town or city. 
    
    An address is considered to be complete if the name, ZIP/Postal code field, and town/city fields are not empty.

    ![](../assets/do-not-localize/book.png) Learn more in [Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-defining-the-target-population.html){target="_blank"}

1. Define the content of the file

    Use the extraction wizard to define the information (columns) to be exported into the output file. 

    ![](../assets/do-not-localize/book.png) Learn more in [Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-direct-mail/defining-the-direct-mail-content.html){target="_blank"}

1. Validate the delivery

    Check the result of the analysis and the content of the output file. 

    ![](../assets/do-not-localize/book.png) Learn more in [Campaign Classic v7 documentation](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-direct-mail/validating.html){target="_blank"}

    In the context of a marketing campaign, on the extraction date, the extraction file is created. You can view the content of the extracted file, approve it, or change the format and re-launch the extraction if needed. Once the file has been approved, you can send the notification e-mail to the router. Learn more in [this page](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-approval.html)

1. Start the  delivery

    Once you validated the extraction file, click **Confirm delivery** a confirmation message lets you launch the delivery.

    The confirmation starts the data extraction in the specified file.

    In the context of a marketing campaign, when all approvals have been granted, the extraction files are created via a special workflow which, in a default configuration, starts automatically when a direct mail delivery is pending extraction. Learn more in [this section](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-deliveries.html)
