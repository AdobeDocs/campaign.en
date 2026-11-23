# RegisterGroup

Add selected recipients to a list

```text
RegisterGroup ( XML groupList, XML recipientList, Boolean register )
```

## Parameters

**groupList** Lists

**recipientList** Recipient list

**register** Subscribe/Unsubscribe recipients

## Return value(s)

None.

## Example

```javascript
//List
var entity = <entityList><key value="24447964"/>
              <where>
                <condition enabledIf="" expr="@id = 24447964"/>
              </where>
            </entityList>
 
//Recipient
var choice = <choiceList><key value="18995462"/>
              <where>
                <condition enabledIf="" expr="@id = 18995462"/>
              </where>
            </choiceList>
nms.recipient.RegisterGroup(entity,choice,true)
        
```

## Features

**Schema:** [nms:recipient](s-nms-recipient.md)

**Static:**

Yes
