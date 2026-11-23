# CreateRequestByName

Create a new privacy Request using namespace internal name

```text
Number id = CreateRequestByName ( String namespaceName, String reconciliationValue, Number type, Boolean confirmDeletePending Number regulation )
```

## Parameters

**namespaceName** Namespace internal name

**reconciliationValue** Reconciliation value

**type** Reconciliation value

**confirmDeletePending** Request confirm before deleting data

**regulation** Regulation type with the following values:

```xml
           
               <value label="GDPR" name="gdpr" value="1"/>
            <value label="CCPA" name="ccpa" value="2"/>
            <value label="PDPA" name="pdpa" value="3"/>
            <value label="LGPD" name="lgpd" value="4"/>
           
           
```

## Return value(s)

**id** ID of newly created request

## Features

**Schema:** [nms:privacyRequest](s-nms-privacyrequest.md)

**Static:**

Yes
