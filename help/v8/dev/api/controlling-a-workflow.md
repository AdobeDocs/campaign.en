---
title: Controlling a workflow
description: Learn how to control a workflow with APIs.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
role: Developer
level: Experienced
exl-id: 79eacc31-d5a2-4e13-aa0b-744d7ab7004f
TQID: https://experienceleague.adobe.com/kSeE0oVVbshxTcMklIQo-aYCFtV1DwQCPinaIWbpPnE
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
feature_v2:
  - id: b12f6872-9271-4369-85e5-86969a0b99a2
    internal-label: APIs
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
---
# Controlling a workflow {#controlling-a-workflow}

You can control a workflow directly from the REST API, through a POST request containing the workflow ID and the required execution command:

`POST https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID>/commands`

>[!CAUTION]
>
>If the workflow ID is changed in Adobe Campaign, the API request will not work anymore.

Four execution commands are available to control a workflow:

* Start
* Pause
* Resume
* Stop


***Sample requests***

* Start a workflow.

  ```

  -X POST https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID>/commands \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>' \
  -i
  -d '{"method":"start"}'

  ```

  <!-- + réponse -->

* Pause a workflow.

  ```

  -X POST https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID>/commands \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>' \
  -i
  -d '{"method":"pause"}'

  ```

  <!-- + réponse -->

* Resume a workflow.

  ```

  -X POST https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID>/commands \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>' \
  -i
  -d '{"method":"resume"}'

  ```

  <!-- + réponse -->

* Stop a workflow.

    ```

    -X POST https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID>/commands \
    -H 'Content-Type: application/json' \
    -H 'Authorization: Bearer <ACCESS_TOKEN>' \
    -H 'Cache-Control: no-cache' \
    -H 'X-Api-Key: <API_KEY>' \
    -i
    -d '{"method":"stop"}'

    ```

    <!-- + réponse -->
