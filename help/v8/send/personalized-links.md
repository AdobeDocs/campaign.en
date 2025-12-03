---
title: Track personalized links
description: Learn how to track personalized links in emails
feature: Personalization
role: User
level: Beginner
exl-id: d0e00b40-e7dd-4484-b37c-fd3f3ac70fda
---
# Track personalized links {#tracking-personalized-links}

The links in email content that contain personalization need specific syntax to be tracked.

Using JavaScript in email content (HTML or Text) allows you to generate and send dynamic content to the recipients, with two limitations:

* The script cannot access the database directly (SQL function and API functions are not available),
* Adobe Campaign must be able to detect URLs so that links can be tracked.

## Pre-processing instructions {#pre-processing-instructions}

You can add specific pre-processing instructions to script the URL and track it. These instructions must be written in JavaScript and start with `<%@`.

For example:

```
<%@ value object="myObject" xpath="@myField" %>
```

This instruction retrieves the value of the `myField` field from the `myObject` object.

## URL detection {#url-detection}

For tracking detection, Adobe Campaign embeds [Tidy](https://www.html-tidy.org/) to parse the HTML source and detect the pattern. It lists all the URLs of the content so that they can be tracked individually. Adobe Campaign uses Tidy again to replace the URL (`http://myurl.com`) with a URL pointing to the Adobe Campaign redirection server.

For example, in the initial content: `http://myurl.com/a.php?name=<%=escapeUrl(recipient.lastName)%>` is replaced for one particular recipient with: `http://emailing.customer.com/r/?id=h617791,71ffa3,71ffa8&p1=CustomerName`

Where:

* "h" means HTML content (or "t" for text content).
* 617791 is the message ID / broadLog ID (hexadecimal).
* 71ffa3 is the NmsDelivery ID (hexadecimal).
* 71ffa8 is the NmsTrackingUrl ID (hexadecimal).
* p1, p2, and so on, are all the parameters to substitute in the URL.

### Example of non-detection {#non-detection-example}

`<%= getURL("http://mynewsletter.com") %>` works and sends the actual content of the web page via email to the recipients. But none of the links are tracked. The reason for this is that the MTA executes `"<%=getURL(..."` for each email before sending. It can be different for each recipient, so Adobe Campaign cannot know the URLs for tracking and assign them a tag ID.

When the page to download is the same for all recipients, the best practice is to use:

```
<%@ include url="http://mynewsletter.com" %>
```

In that case, the page is downloaded during the analysis, before the tracking detection. It allows Adobe Campaign to discover the links, assign a tag ID, and track them.

### Recommended pattern {#recommended-pattern}

After processing `<%@` instructions, the URL to be tracked should have the following syntax:

```
<a href="http://myurl.com/a.php?param1=aaa&param2=<%=escapeUrl(recipient.xxx)%>&param3=<%=escapeUrl(recipient.xxx)%>">
```

>[!IMPORTANT]
>
>All other patterns are not supported by Adobe and should be avoided to prevent potential security gaps.

## URL parameters {#url-parameters}

To ensure that personalized URLs are tracked correctly, you must use the `escapeUrl()` function or the appropriate encoding method for the parameters in your URLs.

**Example:**

```
<a href="http://myurl.com/a.php?name=<%=escapeUrl(recipient.lastName)%>">Click here</a>
```

This will ensure that the personalized parameter is correctly encoded and tracked by Adobe Campaign.

## Best practices {#best-practices}

* Always use the `escapeUrl()` function for dynamic URL parameters
* Test the tracking before sending your delivery to ensure all links work correctly
* Verify that personalized links are correctly formatted in the delivery content
* Check the tracking logs to confirm that personalized parameters are being captured correctly

## Related topics {#related-topics}

* [Learn how to configure tracked links](tracked-links.md)
* [Learn how to configure URL tracking options](url-tracking.md)
* [Learn how to add personalization fields](personalization-fields.md)

