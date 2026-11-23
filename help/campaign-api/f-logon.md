# logon

Changes the script execution context to the current login.

```text
logon (sessionToken)
```

```text
logon (login, password)
```

```text
logon (context)
```

## Parameters

**sessionToken** The session token to be used.

**login** The operator login to be used.

**password** The operator password. The password can be an empty string if the current login has "administrator" rights.

**context** An object that represents a login, returned by a previous call to logon.

## Return value

Returns an object that matches the previous login. This makes it possible to restore the previous login by passing this parameter to the logon function.

## Remarks

Example:

```javascript
var oldContext = logon("jdoe", "")

// ...

logon(oldContext)
```

## Features

**Available in:**

* Content management
* Delivery properties
* Delivery message
* Typology rule
* Import
* JSSP
* SOAP Method
* WebApp
* Workflow
