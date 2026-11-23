# generateRegisterHookScript

Generates the extension script to be called during the "register" event of "appSubscriptionRcp".

```text
String JSScriptStr = generateRegisterHookScript ( XML additionalXmlNodes )
```

## Parameters

**additionalXmlNodes** XML nodes that contain the link between additional parameters and the target mapping field.

## Return value(s)

**JSScriptStr** JS script that enables you to link additional parameters to fields in the target mapping.

## Features

**Schema:** [nms:mobileApp](s-nms-mobileApp.md)

**Static:**

Yes
