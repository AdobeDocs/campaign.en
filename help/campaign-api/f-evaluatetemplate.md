# evaluateTemplate

Evaluates a JavaScript template (&lt;%= ... %&gt;).

```text
evaluateTemplate (template)
```

## Parameters

**template** The template to evaluate.

## Return value

The string after substituting the expressions between &lt;% and %&gt;.

## Remarks

Example:

```javascript
      vars.filename = evaluateTemplate(activity.filename)
```

## Features

**Available in:**

* Workflow
