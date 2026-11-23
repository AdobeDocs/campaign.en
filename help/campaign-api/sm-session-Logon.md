# Logon

Opens a session

```text
[ String sessionToken, sessionInfo sessionInfo, String securityToken ] = Logon ( String login, String password, XML parameters )
```

## Parameters

**login** User account

**password** Password associated with user login

**parameters** Connection settings

## Return value(s)

**sessionToken** Session token

**sessionInfo** Session parameters

**securityToken** Security token

## Account lockout mechanism configuration

An Account lockout mechanism is available within the logon() API. It prevents any further login attempts after a certain number of consecutive failed login attempts within a specified time frame.

Four options are available to configure the lockout mechanism:

* **XtkSecurity\_max\_Unsuccessul\_Attempts\_Allowed**: max unsuccessful attempt to block a key within specified duration. The default value is 3.
* **XtkSecurity\_Initial\_Ban\_Duration**: duration for which key will be banned for the first time. The default duration is 5 minutes.
* **XtkSecurity\_Max\_Ban\_Duration**: max duration for which a key can be banned.
* **XtkSecurity\_Examine\_Window**: time Window to track number of unsuccessful login attempts to ban an invalid key. The default duration is 10 mins.

For example, if someone tries 3 unsuccessful attempts in 10 mins, his key will be blocked for 5 mins.

## Features

**Schema:** [xtk:session](s-xtk-session.md)

**Static:**

Yes
