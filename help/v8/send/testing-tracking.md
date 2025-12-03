---
title: Test message tracking
description: Learn how to test message tracking before sending your deliveries
feature: Monitoring
role: User
level: Beginner
exl-id: 16ad36b7-c13e-4b77-86ca-41c9ef174172
---
# Test message tracking {#testing-tracking}

You can test tracking on mirror pages, email logs and links before sending your delivery to your entire audience. To do this:

## Create a test delivery {#create-test-delivery}

1. Create a new email delivery that will be used for testing.
1. Design your email content with links that you want to track.
1. Add a mirror page personalization block in the email content.
1. Specify the user that will receive the email. Since this user will have to open the email and click the links it contains, make sure you select a test recipient address that you control.

## Send the test delivery {#send-test}

1. Verify that tracking is enabled in the delivery settings:
   * Open the **[!UICONTROL Properties]** of your delivery
   * Go to the **[!UICONTROL Tracking & Images]** section
   * Ensure that **[!UICONTROL Activate tracking]** is checked
   * Ensure that **[!UICONTROL Opens tracking]** is checked if you want to track opens

1. Send the delivery to your test recipient.

## Verify tracking functionality {#verify-tracking}

1. Once you have received the email, open it and click the mirror page link.
1. Click on various links in the email to generate tracking data.
1. After you are correctly redirected to the mirror page, access the **[!UICONTROL Administration > Production > Technical workflows]** folder.
1. Open the **[!UICONTROL Tracking]** workflow.
1. Start the workflow, or right-click the **[!UICONTROL Scheduler]** activity and select **[!UICONTROL Execute pending task now]**.
1. Wait around 30 seconds for the workflow to process the tracking logs.
1. Select the **[!UICONTROL Audit]** tab of the workflow. Ensure that at least one tracking log record is found.

   Click **[!UICONTROL Refresh]** if you do not see any new logs.

## Check recipient tracking tab {#check-recipient-tracking}

1. Go to the profile page of the recipient you used for the test.
   * The recipient's profile page is located in the **[!UICONTROL Profiles and Targets > Recipients]** folder by default.

1. Select the **[!UICONTROL Tracking]** tab.
1. Verify that tracking records appear with:
   * The **[!UICONTROL Mirror Page]** value in the **[!UICONTROL Type]** column
   * **[!UICONTROL Open]** values in the **[!UICONTROL Type]** column for email opens
   * **[!UICONTROL Email click]** values in the **[!UICONTROL Type]** column for link clicks

## Troubleshooting tracking test {#troubleshooting-tracking-test}

If the tracking logs do not appear:

1. **Check delivery settings**: Go to the delivery and access its **[!UICONTROL Properties]** to make sure that both **[!UICONTROL Activate tracking]** and **[!UICONTROL Opens tracking]** options are checked.

1. **Verify the Tracking workflow**: Make sure the **[!UICONTROL Tracking]** technical workflow is running without errors.

1. **Check URL format**: Verify that your URLs are correctly formatted and enclosed in delimiters. See [this section](tracked-links.md) for more information.

1. **Review email client behavior**: Some email clients may block tracking pixels or modify links. Try testing with different email clients.

1. **Wait for processing**: The Tracking workflow runs hourly by default. If you manually trigger it, allow sufficient time for processing before checking results.

## Related topics {#related-topics}

* [Learn how to configure tracked links](tracked-links.md)
* [Learn how to access tracking logs](tracking-logs.md)
* [Understand tracking reports](../reporting/delivery-reports.md#tracking-indicators)

