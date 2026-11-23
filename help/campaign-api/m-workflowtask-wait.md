# wait

Awaits a signal.

```text
wait (timeout)
```

## Parameters

**timeout** Waiting time in milliseconds.

## Return value

A boolean to true if a signal is received before the expiry of waiting time.

## Remarks

The signal is issued by the [Wakeup](sm-workflow-wakeup.md) and [WakeupTask](sm-workflow-wakeuptask.md) SOAP methods. The protocol used (UDP) doesn't guarantee message reception. This signal is only useful for executing an operation faster. Warning: this signal will never be received in a sub-workflow. Example: Here is a typical example of use: a loop processes operations coming from a queue (poll()) then waits a certain amount of time between each operation. An additional delay is added to force workflow passivation.

```javascript
var lifetime = 30 * 60 * 1000 // 30 minutes
var frequency = 30 * 1000 // 30 seconds
var start = new Date().getTime()
while( new Date().getTime() - start < lifetime )
{
  poll()
  task.wait(frequency)
}
 
```

## Features

**Method of class:** [WorkflowTask](c-workflowtask.md)

**Available in:**

* Workflow
