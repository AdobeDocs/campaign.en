# ExecuteQuery

Retrieve data from a query

```text
XML output = queryDef.ExecuteQuery () const
```

## Parameters

None.

## Return value(s)

**output** Output XML document

## Remarks

The query supports four types of operations:

* select
* get
* getIfExists
* count

## Example

```javascript
var query = NLWS.xtkQueryDef.create(
  {queryDef: {schema: "xtk:workflow", operation: "select", 
    select: {
        node: [{expr: "@id"},
               {expr: "@label"},
               {expr: "@internalName"}] 
    }, 
    where: {
      condition: [{expr: "[folder/@name]='nmsTechnicalWorkflow'"},
                  {expr: "@production = 1"}]
    }, 
    orderBy: {
      node: {expr: "@internalName", sortDesc: "false"}
    }
  }})

var res = query.ExecuteQuery()

var workflows = res.getElementsByTagName("workflow")
for each (var w in workflows)
  logInfo(w.getAttribute("internalName"))
        
```

## Features

**Schema:** [xtk:queryDef](s-xtk-queryDef.md)

**Static:**

No

**Const:**

Yes

**Key only:**

No
