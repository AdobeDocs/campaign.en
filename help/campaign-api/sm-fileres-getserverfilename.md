# GetServerFileName

Returns the name of the file on the server after copying it, if necessary, in the upload folder.

```text
String serverFileName = fileRes.GetServerFileName ()
```

## Parameters

None.

## Return value(s)

**serverFileName** Full name of file on server (empty if file not found).

## Example

```javascript
var query = xtk.queryDef.create(
  {queryDef: {schema: "xtk:fileRes", operation: "get", 
    select: {
      node: [
      {expr: "@label"}, 
      {expr: "@originalName"}, 
      {expr: "@storageType"}, 
      {expr: "@fileName"}, 
      {expr: "@md5"}]
    }, 
    where: {
      condition: {expr: "@id = 4216"}
    }
  }})

var fileRes = xtk.fileRes.create(query.ExecuteQuery())
var sFileName = fileRes.GetServerFileName();
        
```

## Features

**Schema:** [xtk:fileRes](s-xtk-fileres.md)

**Static:**

No

**Const:**

No

**Key only:**

No
