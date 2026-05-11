---
title: GET / POST / PATCH / DELETE verbs
description: Learn more about the verbs used in Campaign Standard APIs.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
role: Developer
level: Experienced
exl-id: de97a194-d497-4665-906e-53178fd3b119
TQID: https://experienceleague.adobe.com/S8WC9Y9aqkSodleg6QasdSL4XvV8S6BFCZtyPi3l4II
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
feature_v2:
  - id: b12f6872-9271-4369-85e5-86969a0b99a2
    internal-label: APIs
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
    internal-label: Metadata
---
# GET / POST / PATCH / DELETE verbs {#verbs}

Available verbs to perform operations on the resources are:

* `GET`: retrieves one element or a collection of elements
* `POST`: creates a resource with parameters.
* `PATCH`: updates a resource with parameters.
* `DELETE`: deletes a resource.

<!-- ajouter codes retour -->

<br/>

***Sample requests***

* Sample GET request on the profile collection.


    ```

    $curl  
    -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile \
    -H 'Content-Type: application/json' \
    -H 'Authorization: Bearer <ACCESS_TOKEN>' \
    -H 'Cache-Control: no-cache' \
    -H 'X-Api-Key: <API_KEY>'

    ```

    It returns an array of profiles.


    ```

    {
        "content": [
            {
                "PKey": "<PKEY>",
                "firstName": "Olivia",
                "lastName": "Varney",
                "birthDate": "1977-09-°4",
                "email": "o.varney@mail.com",
            },
            {
                "PKey": "<PKEY>",
                "firstName": "John",
                "lastName": "Doe",
                "birthDate": "1985-08-17",
                "email": "johndoe@mail.com",
            }
        ],
    }

    ```

* Sample GET request on a specific profile.


    ```

    $curl  
    -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY> \
    -H 'Content-Type: application/json' \
    -H 'Authorization: Bearer <ACCESS_TOKEN>' \
    -H 'Cache-Control: no-cache' \
    -H 'X-Api-Key: <API_KEY>'

    ```

    It returns the requested profile.


    ```

    {
        "PKey": "<PKEY>",
        "firstName": "John",
        "lastName": "Doe",
        "birthDate": "1985-08-17",
        "email": "johndoe@mail.com",
        ...
    }

    ```

* Sample POST request to create a profile.


    ```

    -X POST https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile \
    -H 'Content-Type: application/json' \
    -H 'Authorization: Bearer <ACCESS_TOKEN>' \
    -H 'Cache-Control: no-cache' \
    -H 'X-Api-Key: <API_KEY>' \
    -d '{"lastName":"Doe"}'

    ```

    It returns the profile with the default fields.

    ```

    {
        "PKey": "<PKEY>",
        "firstName": "John",
        "lastName": "Doe",
        "birthDate": "1985-08-17",
        "email": "johndoe@mail.com",
    }

    ```

* Sample PATCH request to update a profile.

    ```

    -X PATCH https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY> \
    -H 'Content-Type: application/json' \
    -H 'Authorization: Bearer <ACCESS_TOKEN>' \
    -H 'Cache-Control: no-cache' \
    -H 'X-Api-Key: <API_KEY>' \
    -d '{"firstName":"Mark"',"lastName":"Smith"}'

    ```

    It returns the PKEY and URL to retrieve the updated profile.

    ```

    {
        "PKey": "<PKEY>",
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY>"
    }

    ```

* Sample DELETE request to delete a profile.

    ```

    -X DELETE https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY> \
    -H 'Content-Type: application/json' \
    -H 'Authorization: Bearer <ACCESS_TOKEN>' \
    -H 'Cache-Control: no-cache' \
    -H 'X-Api-Key: <API_KEY>'

    ```

    The request returns a 200 response, confirming that the profile has been deleted.
