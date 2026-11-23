# Subscribe

Create or update a recipient subscription to an Information Service

```text
Subscribe ( String serviceName, XML recipient, Boolean create )
```

## Parameters

**serviceName** List of Information Service names (comma separated)

**recipient** Recipient to register and optionally to create

**create** Create recipient if it does not exist

## Return value(s)

None.

## Example

```javascript
      var recipient = {recipient: {_key: "email", email: "john.smith@example.com"}}
nms.subscription.Subscribe("SVC1", recipient, false)
        
```

## Features

**Schema:** [nms:subscription](s-nms-subscription.md)

**Static:**

Yes
