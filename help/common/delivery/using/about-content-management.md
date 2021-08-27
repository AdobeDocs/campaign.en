---
product: campaign
title: Get started with content management
description: Learn what is the Content Manager add-on
audience: delivery
content-type: reference
topic-tags: content-management
exl-id: 87434cc2-1636-4558-ab60-255b7f873c0c
---
# Get started with Content management{#about-content-management}

![](../../assets/common.svg)

Adobe Campaign Content Manager module is a specific Campaign add-on which you can install to create recurrent newsletters or website. It can assist you to create, validate, and publish your messages.

>[!NOTE]
>
>This section refers to the Content Management module. For more information on how to design email deliveries content, refer to [this section](email/defining-the-email-content.md).

The Content management module incorporates working group, workflow and content aggregation functionality. This allows a message to be formatted automatically: email, mail, SMS, web, etc.

Using content manager in a delivery lets you offer input or selection fields to the operators in charge of content creation. The layout and display of this content as well as any changes made are managed automatically using the stylesheet.

![](assets/s_ncs_content_create_content_sample.png)

>[!CAUTION]
>
>All changes made to the stylesheet are implemented at delivery level based on the content templates used.

Content management provides the following advantages:

* Structured message editing via input interfaces,
* Separation of data content and how it is presented (generated in XML format),
* Document generation in multiple formats (html, txt, XML, etc.) based on stylesheets to guarantee compliance with graphical charters,
* Recovery and automatic aggregation of external content flows,
* Collaboration with workflow for data validation and checking.

This mode of content creation does however involve a few constraints; including in particular:

* Restricted freedom concerning the final document design,
* The analysis of requirements must be rigorous so that end users will not be inconvenienced by a missing function.

## Resources and principles{#content-manager-resources-and-principles}

You need to define a publication template, which contains transformation templates for each content.

A content block is structured in an XML document for data storage. An edit interface is used to input the content from the Adobe Campaign client console or via a web browser. The content can also be entered automatically via the capture of XML flow or data aggregated in a database.

Combining the XML document and the XSL or JavaScript Template stylesheets automatically generates the projection of the publication template in the various formats (HTML, text).

![](assets/d_ncs_content_process.png)

The following resources are required for content configuration:

* Data schemas: description of the XML content structure. For more on this, refer to [Data schemas](data-schemas.md).
* Data entry forms: construction of data entry screens. For more on this, refer to [Input forms](input-forms.md).
* Images: images used in data entry forms. For more on this, refer to [Image management](formatting.md#image-management).
* Stylesheets: formatting of output documents using XSLT language. For more on this, refer to [Formatting](formatting.md).
* JavaScript templates: formatting of output documents using JavaScript language. For more on this, refer to [Publication templates](publication-templates.md).
* JavaScript codes: JavaScript codes for data aggregation. For more on this, refer to [Aggregator](publication-templates.md#aggregator).
* Publication templates: definition of publication templates. For more on this, refer to [Publication templates](publication-templates.md).
* Content: content instances to be created and published. For more on this, refer to [Using a content template](using-a-content-template.md).
