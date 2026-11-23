# execCommand

> Warning: This function is available for an on-Premise environment.

Executes a command and captures the error code and standard output.

```text
execCommand (command [, bNoThrow ])
```

## Parameters

**command** The command to execute with its parameters.

**bNoThrow** true to get the output and the error code even if the command does not return zero (false by default).

## Return value

Returns a table whose first element corresponds to the return code of the command (if the return code is different from zero, there is an anomaly) and the second element is a character string containing the standard output produced.

## Remarks

Without the bNothrow option, an exception is raised if the command cannot be executed or if the command is executed with an error. If bNoThrow equals true, an exception is raised only if the command cannot be executed. The operator needs 'createProcess' rights to use this function, otherwise an exception is raised. Depending on your installation, some commands can be on the block list. For example: ln, dd, openssl, curl, wget, python, python3, perl, ruby, sh, bash, dash, zsh, base64, nlserver, node, phantomjs, java, awk, nc, telnet, ssh, scp, ftp.

## Example

```text
var result = execCommand('gpg-exec.sh gpg --no-tty --yes -r CampaignOperations@adobe.com --encrypt "file_to_encrypt"', true);
```

## Features

**Available in:**

* Content management
* Delivery properties
* Typology rule
* JSSP
* SOAP Method
* WebApp
* Workflow
