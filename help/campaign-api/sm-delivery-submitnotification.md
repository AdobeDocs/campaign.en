# SubmitNotification

Create and submit a notification from a scenario.

```text
Number notificationId = SubmitNotification ( String scenarioName, XML target )
```

## Parameters

**scenarioName** Internal name of the template

**target** Delivery target population replacing the one in the scenario

## Return value(s)

**notificationId** Notification identifier

## Remarks

Warning: this API is not built to manage large volumes of data or work in real-time. It is developed to process a maximum of several calls per minute. SubmitNotification blocks the thread during delivery analysis. This may take a few seconds. The "target" parameter specifies the delivery target. It will override a target specified in the template. To deliver to a target in the database the target element will use the following syntax:

```xml
<delivery>
  <targets>
    <deliveryTarget>
      <targetPart type='query' exclusion='false' ignoreDeleteStatus='false'>
        <where>
          <condition expr='[@folder-id] = 1050'/>
        </where>
      </targetPart>
    </deliveryTarget>
  </targets>
</delivery>
```

To deliver to a target in a file:

```xml
<delivery>
  <targets>
    <deliveryFile upload='false'>
      <name>c:/tmp/myFile.csv</name>
    </deliveryFile>
  </targets>
</delivery>
```

It is possible to explicity define the target (in reality the content of the file used as the target):

```xml
<delivery>
  <targets fromExternalSource='true'>
    <externalSource>MsgId|ClientId|Title|Name|FirstName|Mobile|Email|Market_segment|Product_propensity1|Product_propensity2|Product_propensity3|Product_propensity4|Support_Number|Amount|Threshold1|
                    000001234|M.|Martin|Peter|0650201020|pmartin@neolane.com|1|A1|A2|A3|A4|E12|120000|100000
    </externalSource>
  </targets>
</delivery>
```

It is also possible to keep the target defined in the template with the attribute "\_keepTemplateTarget"

```xml
<delivery>
  <targets _keepScenarioTarget='true'/>
</delivery>
```

## Features

**Schema:** [nms:delivery](s-nms-delivery.md)

**Static:**

Yes
