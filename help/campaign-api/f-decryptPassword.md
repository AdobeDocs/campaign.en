# decryptPassword

> Warning:
>
> This documentation has been updated. For more details, please refer to this [page](https://experienceleague.adobe.com/en/docs/campaign-classic/using/technotes/gcm-functions#decryptpassword-headding-anchor-decryptpassword-javascript).

Decrypts a password stored in an external account.

```text
decryptPassword (str)
```

## Parameters

**str** The encrypted character string.

## Return value

Returns the plain-text password.

## Remarks

This function cannot be called in workflows, web applications, reports or deliveries. It can be called in JSSP or SOAP call implementations. Example:

```javascript
      	function nms_extAccount_LogonToRemoteInstance(remoteInstanceUrl, login, encryptedPassword) {
      	var cnx = null, sessionService = null;
      	try
	      	{
		      	var cnx = new HttpSoapConnection(remoteInstanceUrl + '/nl/jsp/soaprouter.jsp', 'utf-8', 0);
		      	sessionService = new SoapService(cnx, 'xtk:session');
		      	sessionService.addMethod("Logon", "xtk:session#Logon",
			      	["token", "string", "login", "string", "password", "string", "parameters", "NLElement"],
			      	["sessionToken", "string", "sessionInfo", "NLElement", "securityToken", "string"]);
		      	return sessionService.Logon("", login, decryptPassword(encryptedPassword), <parameters/>);
	      	}
      	catch( e ) {
      	logError(e);
      	}
      	finally {
      	if( sessionService ) sessionService.dispose();
      	if( cnx ) cnx.dispose();
      	}
      	})
      
```

## Features

**Available in:**

* SOAP Method
