---
product: Adobe Campaign
title: Send direct mails with Adobe Campaign
description: Get started with direct mail in Campaign
feature: Overview
role: Data Engineer
level: Beginner
---
# Get started with direct mail deliveries

Direct mail deliveries let you generate an extraction file which contains data on the target population. You can then share this file with the provider who will deliver messages to the target populations.

Steps to generate the file are:

1. Create the delivery

    Create a direct mail delivery based on the template. You can duplicate and configure the **[!UICONTROL Deliver by direct mail (paper)]** built-in template. [Learn more](creating-a-direct-mail-delivery.md).

1. Define the audience

    The recipient profiles must contain at least their names and postal addresses.

    Postal addresses are calculated fields. An address can contain up to six lines by default: the first contains the first name and last name, the next lines contain the postal address (road etc.), and the last line contains the ZIP/Postal code and town or city. 
    
    An address is considered to be complete if the name, ZIP/Postal code field, and town/city fields are not empty.
    
    [Learn more about audiences](../steps-defining-the-target-population.md).

1. Define the content of the file

    Use the extraction wizard to define the information (columns) to be exported into the output file. 
    
    [Learn more about direct mail delivery content](defining-the-direct-mail-content.md).

1. Validate the delivery

    Check the result of the analysis and the content of the output file. 

    [Learn how to validate a direct mail delivery](validating.md).

    In the context of a marketing campaign, on the extraction date, the extraction file is created. You can view the content of the extracted file, approve it, or change the format and re-launch the extraction if needed. Once the file has been approved, you can send the notification e-mail to the router.

    [Learn how to set up a validation process](../../../campaign/using/marketing-campaign-approval.md#approving-an-extraction-file).

1. Start the  delivery

    Once you validated the extraction file, click **Confirm delivery** a confirmation message lets you launch the delivery.

    The confirmation starts the data extraction in the specified file.

    In the context of a marketing campaign, when all approvals have been granted, the extraction files are created via a special workflow which, in a default configuration, starts automatically when a direct mail delivery is pending extraction. 
    
    Learn more in [this section](../../../campaign/using/marketing-campaign-deliveries.md#starting-an-offline-delivery).