# Unsubscribe

Unsubscribes a recipient from an Information Service

```text
Unsubscribe ( String serviceName, XML recipient )
```

## Parameters

**serviceName** List of Information Service names (comma separated)

**recipient** Recipient

## Return value(s)

None.

## Example

```javascript
      var recipient = {recipient: {_key: "email", email: "john.smith@example.com"}}
nms.subscription.Unsubscribe("SVC1", recipient)
        
```

## Features

**Schema:** [nms:subscription](s-nms-subscription.md)

**Static:**

Yes
