---
title: SMPP external account parameters
description: Learn how to configure the SMPP external account
feature: SMS
role: User
level: Intermediate
---

# SMPP external account parameters {#smpp-external-account}

Adobe Campaign uses the SMPP protocol to send SMS to a service provider.

>[!IMPORTANT]
>
>Adobe Campaign supports the SMPP protocol version 3.4.


The SMS connector in Adobe Campaign provides many options to adapt its behavior in order to be compatible with most SMPP providers, who tend to deviate a bit from the official specification.

>[!IMPORTANT]
>
>Setting up a connection to a new provider may require some technical skills, knowledge of TCP, binary, hexadecimal representation and text encodings. It will also require active cooperation with the provider.

The network equipment on the SMS service provider side is often called the SMSC.

## Connection settings {#smpp-connection-settings}

Here are the parameters and their role needed to set up the connection : 

* **SMSC implementation name** : sets the name of the SMSC implementation. It should be set to the name of your provider. The role of this field is described in the SMPP error management section.
* **Server** : The DNS name or IP address of the server to connect to.
* **Port** : The TCP port to connect to.
* **Account** : The login of the connection. Passed in the system_id field of the BIND PDU.
* **Password** : Password of the SMPP connection. Passed in the password field of the BIND PDU.
* **System type** : Value passed in the system_type field of the BIND PDU. Some providers need a specific value here.
* **Number of MTA child connections** : This defines how many connections are opened per sending thread.
The total number of connections can be computed using this formula:
*Total connections = Number of SMS processes * number of sending threads * number of MTA child connections*

    * Number of SMS processes is normally 1. On some very high performance instances, multiple SMS processes might be started in parallel.
    * Number of sending threads is set in serverConf (sendingThreads setting). It defaults to 1.
    * Number of MTA child connections is this setting in the external account.
    
    With default values, this setting directly sets the number of connections.

    >[!NOTE]
    >
    >In **transceiver mode**, this is the total number of connections.
    In **transmitter+receiver mode**, this defines the number of transmitter+receiver pairs (one pair = one transmitter + one receiver). 
    There is no way to change the balance between transmitters and receivers.
* **Send messages through a dedicated process** :
For Adobe Campaign v8.7.2 and later, this option should be always enabled. It has many impacts on how messages are processed.
* **SMPP connection mode** :
Set the connection in transceiver mode or in separated transmitter+receiver mode. 
    * Transmitter+receiver (or TX+RX): two separate TCP connections are used for transmitting and receiving messages.
    * Transceiver (or TRX): a single TCP connection is used for transmitting and receiving messages.
* **Use different parameters for receiver** :
Available only in transmitter+receiver mode.
When the box is unchecked, the same settings are used for transmitter and receiver. When the box is checked, standard settings will apply only to the transmitter, while receiver settings will apply only to the receiver.
* **Receiver server, port, account, password, system type**
These settings apply to the receiver when in transmitter+receiver mode. They work like the transmitter part, see above for [more details](#smpp-connection-settings).
* **Enable verbose SMPP traces in the log file**
When enabled, extra logs will be output to the log file. This is very useful for troubleshooting, but should be kept disabled on high throughput instances if no troubleshooting is required.

## SMPP channel settings {#smpp-channel-settings}

### Allow character transliteration

Transliteration is the process of finding equivalent characters to missing ones. For example, the French "ê" (e with circumflex accent) character is missing from GSM encoding, but it can be replaced by "e" without impairing readability too much.

When this box is unchecked, text encoding will fail if it cannot encode the string exactly as-is.

When this box is checked, text encoding will try to convert the string to an approximate version instead of failing. If some characters have no equivalent in the target encoding, text encoding will fail.

See the Define a specific mapping of encodings setting for a more general explanation of the encoding process.

### Source number

Defines the default source address for messages. This setting only applies if the source number has been left empty in the delivery. By default, the source number field is not passed, so the provider will substitute it for the short code.

This enables the sender address / oADC override feature.

### Source TON/NPI, Destination TON/NPI

TON (Type Of Number) and NPI (Numbering Plan Indicator) (described in section 5.2.5 of the SMPP 3.4 specification). These values should be set to whatever the provider needs.

They are transmitted as-is in source_addr_ton, source_addr_npi, dest_addr_ton and dest_addr_npi fields of the SUBMIT_SM PDU.

### Service type

This field is transmitted as-is in the service_type field of the SUBMIT_SM PDU. Set this to whatever the provider needs.

## Throughput and delays {#smpp-delays}

These settings control all the timing aspects of the SMPP channel. Some providers require very precise control of the message rate, window and retry timings, so these settings should be set to values that match the capacity of the provider and the conditions indicated in their contract.

### Sending window

The window is the number of SUBMIT_SM PDUs that can be sent without waiting for a matching SUBMIT_SM_RESP.

Example of a transmission with a maximum window of 4:

![](assets/sms_sending_window.png){zoomable="yes"}

The window helps increasing throughput when the network link has a high latency. The value of the window must be at least the number of SMS/s multiplied by the latency of the link (in seconds) so the connector is never waiting for a SUBMIT_SM_RESP before sending the next message.

If the window is too big, you may send more duplicate messages in case of connection problems (rare case). Also, most providers have a very strict limit for the window and refuse messages that go over the limit.

How to calculate the optimal sending window formula:

Measure the maximum latency between SUBMIT_SM and SUBMIT_SM_RESP.
Multiply this value (in seconds) to the max MT throughput: this will give the optimal sending window value.
Example: If you have 300 SMS/s set in max MT throughput and there is 100ms latency between SUBMIT_SM and SUBMIT_SM_RESP on average, the optimal value would be 300×0.1 = 30.

When in doubt, prefer a bigger window to avoid performance problems.

### Max MT throughput

Maximum number of MT per second and per connection. This setting is strictly enforced, the MTA will never push messages faster than this limit. It is useful for providers that require precise throttling.

To know the total throughput limit, multiply this number by the total number of connections (see the formula above).

0 means no limit, the MTA will send MT as fast as possible.

It is generally recommended to keep this setting under 1000, as it is impossible to guarantee precise throughput above this number, unless properly benchmarked on the final architecture and specifically requested SMPP provider. It may be better to increase the number of connections to go above 1000 MT/s.

### Time before reconnection

When the TCP connection is lost, the connector will wait this number of seconds before trying to make a connection.

### Expiration period of the MT

This is the timeout between SUBMIT_SM and its matching SUBMIT_SM_RESP. If the RESP is not received on time, the message will be considered as failed and global retry policy of the MTA will apply.

### Bind timeout

Timeout between the TCP connect attempt and the BIND_*_RESP reply. When it times out, the connection is closed by the Campaign connector and it will wait Time before reconnection before trying again.

### enquire_link period

enquire_link is a special kind of PDU sent to keep the connection alive. This period is in seconds. The campaign connector only sends enquire_link when the connection is idle in order to conserve bandwidth. If no RESP is received after twice this period, the connection will be considered dead and a reconnection process will be triggered.

## Mapping of encodings {#mapping-encodings}

Please see the SMS text encoding section below for details about text encoding.

This setting allows to define a custom encoding mapping, different from the specification. You will be able to declare a list of encodings, along with their data_coding value. The MTA will try to encode using the first encoding in the list; if it fails, it tries to use the next encoding on the list, etc... If no encoding can be used to encode the message, an error will happen. Once the encoding is found, the MTA will create the SUBMIT_SM PDU with the encoded text and the data_coding field set with the value specified in the table.

The order of items in the table is important: encodings are tries from top to bottom. You should put the cheapest or most recommended encoding at the top of the list, then followed by more and more expensive (or less desirable) encodings.

Note that UCS-2 will never fail as it can encode all characters supported in Campaign. Please note that the maximum length of an UCS-2 SMS is much smaller (70 characters only).

You can also use this setting to force a specific encoding to be always used by declaring only 1 line in the mapping table.

The default mapping used when the checkbox is not checked is equivalent to the following table:

| data_coding | Encoding  |
|:-:|:-:|
| 0 | GSM |
| 8 | UCS-2 |

This means that the MTA will try to encode the message in GSM, if it succeeds it sends it with data_coding set to 0.

If the message cannot be encoded in GSM, it will be encoded in UCS-2 and will set data_coding to 8.

## SMSC specificities {#smsc-specificities}

### Activate message_payload

When unchecked, long SMS will be split by the MTA and sent in multiple SUBMIT_SM PDUs with UDH. The message will be recomposed by the mobile phone following UDH data.

When checked, long SMS will be sent in one SUBMIT_SM PDU, putting the text in the message_payload optional field (see the SMPP specification for details about this).

If this feature is enabled, Campaign will be unable to count SMS parts individually: all messages will be counted as sent in one part.

### Send the full phone number

When this checkbox is not checked, only digits of the phone number are sent to the provider (destination_addr field of the SUBMIT_SM field). This is the default behavior because the international number indicator (usually a + prefix) is replaced by TON and NPI fields in SMPP.

When the checkbox is checked, the phone number is sent as-is, with no preprocessing (and potential spaces, + prefix or pound/hash/star signs).

This feature also has an effect on the behavior of auto reply quarantine feature: when the checkbox is not checked, a + prefix will be added to phone numbers inserted into the quarantine table in order to compensate for the + prefix being removed from the phone number by the SMPP protocol itself.

### Bind TON/NPI

TON (Type Of Number) and NPI (Numbering Plan Indicator) (described in section 5.2.5 of the SMPP 3.4 specification). These values should be set to whatever the provider needs.

They are transmitted as-is in addr_ton and addr_npi fields of the BIND PDU.

### Address range

Sent as-is in the address_range field of the BIND PDU. This value should be set to whatever the provider needs.

### Invalid ID acknowledge count

Limits the number of "Messsage ID invalid" DELIVER_SM_RESP that can be sent for a single SR. **This should be only used for troubleshooting purpose as a workaround** and set to 0 in normal conditions.

Detailed explanation: say you set this setting to 2:

* The provider sends a SR (DELIVER_SM) with ID "1234"
* The ID "1234" could not be found in the database
* The connector counts 1 "Invalid ID" error for that ID, so it sends DELIVER_SM_RESP with the "Message ID invalid" error code (normal behavior).
* The provider retries the same SR with ID "1234"
* The ID "1234" still could not be found in the database
* The connector counts 2 "Invalid ID" error for that ID, so it sends DELIVER_SM_RESP "OK", even if it was not processed correctly.

This feature is meant to flush SR buffers on the provider side when invalid SR block legitimate messages that cannot be processed.

Setting this field to 0 disables the mechanism so "Message ID invalid" is always returned, this is normal behavior.

Setting this field to 1 makes the connector always respond "OK" even if the ID is invalid. This should be set to 1 only used under supervision for troubleshooting and for the minimum amount of time, e.g. to recover from a provider-side issue.

### Extraction regex of the ID in the SR

SR format is not strictly enforced by the SMPP protocol specification. It is only a recommendation described in appendix B of the spec. Because of this, some SMPP implementors format this field differently, so Campaign needs a way to extract the correct field.

By default, it captures up to 10 alphanumeric characters after "id:".

The regex must have exactly one capture group (a part that is contained within parentheses). Parentheses must surround the part that correspond to the ID. The regex format is PCRE.

When adjusting this setting, be sure to include as much context as possible to avoid false triggers. If there are specific prefixes (such as "id:" in the standard), include them in the regex. Also use word delimiters (\b) as much as possible, to avoid capturing text in the middle of a word.

Not including enough context in the regex can introduce a small security flaw: the actual content of the message can be included in the SR, so if you just match a specific ID format with no context (e.g. a UUID), it may be parsing the actual text content (e.g. a UUID embedded in the text field) instead of the ID.

### Extraction regex of the status in the SR

This regex captures the status from the text field of SR messages.

By default, it captures between 5 and 15 characters after "stat:".

The regex must have **exactly one capture group** (a part that is contained within parentheses). Parentheses must surround the part that correspond to the status. The regex format is PCRE.

### Regex applied to determine successful status

This regex is applied on the result of the previous regex ("Extraction regex of the status"). If the regex matches, the message is considered as successful.

By default, it matches everything that starts with "DELIV". It matches the standard value "DELIVRD".

### Regex applied to determine error status

This regex is applied on the result of the previous regex ("Extraction regex of the status"). If the regex matches, the message is considered in error.

By default, it matches all various error status described in the specification.

### Extraction regex of the error code in the SR

This regex captures the error code from the text field of SR messages.

Error codes can be qualified in delivery log qualification.

By default, it captures 3 characters after "err:".

### ID format in MT acknowledgement

This indicates the format of the ID returned in the message_id field of the SUBMIT_SM_RESP PDU.

* **Do not modify**: The ID is stored as-is in the database, as ASCII-encoded text. No pre-processing nor filtering occurs.
* **Decimal number**: The ID is expected to be a decimal number in ASCII form. Leading and trailing spaces and leading zeroes are removed when this setting is used.
* **Hexadecimal number**: The ID is expected to be a hexadecimal number in ASCII form, with no leading 0x nor trailing h. The ID is then converted to a decimal number before being stored in the database.
* **Hexadecimal string**: The ID is expected to be an ASCII-encoded text that is itself a string of bytes encoded as hexadecimal. For example, in the PDU you will find 0x34 0x31 0x34 0x32 0x34 0x33, which translates to ASCII "414243"; then this string is decoded as a hexadecimal string of bytes, and you obtain "ABC" as a result: you will store the ID "ABC" in the database.

### ID format in the SR

This indicates the format of the ID captured by the Extraction regex of the ID in the SR. Values have the same meaning and the same behavior as the format in MT above.

### SR ID or error code in optional field

If checked, the content of optional fields will be appended to the text processed by regexes above. The text will have the format " 0xTAG:VALUE", 0xTAG being the 4-digit hexadecimal value of the tag in upper case (e.g. 0x002E).

For example, you might want to capture the ID in the receipted_message_id field. For this, enable this checkbox and the following text will be added to the status:

 0x001E:05e3299e-8d37-49d0-97c6-8e4fe60c7739

In this example, 0x001E is the tag of the optional field and the UUID is the value of the field.

In order to capture this value, you may now set the following regex in the Extraction regex of the ID in the SR field:

\b0x001E:([0-9a-f]{8}-[0-9a-f]{4}-[0-9a-f]{4}-[0-9a-f]{4}-[0-9a-f]{12})\b

>[!IMPORTANT]
>
>You can only capture optional fields that have 8-bit text (ASCII/UTF-8) values. Specifically, binary fields cannot be captured reliably with the current regex system.

### SR ID or error code in text field

If checked, the Text: field will be kept during processing of the status text of the SR. This is useful if the provider places important data in this field like the ID or the status. Usually this field can be safely discarded since it may contain text with a non-ASCII encoding and disrupt regex processing.

Enabling this option may introduce a very small security flaw if the Extraction regex of the ID in the SR field is not specific enough: the content of the Text field may be parsed as an ID and an attacker may use it to inject forged IDs, which may lead to a partial denial of service situation.

### Service ID tag

Allows to add a custom TLV. This field sets the tag, passed as a hexadecimal value in the format **0x1234**.

The value of the custom TLV must be set in the delivery in the "Service or program ID" field in the advanced parameters of the delivery. The value is sent as UTF-8 encoded text.

This setting only allows adding one TLV option per message.

>[!NOTE]
>
>This option is superseded by the much more powerful **Optional SMPP parameters (TLV)** setting in delivery parameters. These features are mutually exclusive and cannot be used at the same time.

### Enable TLS over SMPP

If enabled, all connections to the SMSC will be encrypted using TLS.

### Certificate verification

* **Full certificate verification**: Check the TLS certificate and remote host name when connecting. This value gives the highest level of security.
* **Skip the hostname verification**: Check the remote TLS certificate, but do not check if the remote host name matches. Decreases security slightly.
* **Skip the certificate verification**: Do not check the TLS certificate at all. The connection is still encrypted, but it is vulnerable to man-in-the-middle attacks. Decreases security a lot.


## Incoming traffic {#incoming-traffic}

### Optional SMPP parameters (TLV) in MO

Campaign allows receiving 3 extra fields in MO (nms:inSms table): Linked SMS, alias and large account. With the SMPP connector, these fields can be filled with data coming from any optional SMPP parameter (TLV), with any common format.

For each field, you can set the associated tag as well as its format. Ask the SMPP service provider to have this information.

* Tag: the tag value, either in decimal format (e.g. 12345) or hexadecimal with 0x prefix (e.g. 0x12ab). Tags can go between 0 and 65535.
* Format: format used for value. Binary values are all big-endian signed binary values. For text fields, choose the encoding used by the SMPP provider.

### Automatic reply sent to the MO 

This feature allows to quickly reply text to MO and handle per-shortcode blacklists.

The *Keyword* and *Short code* columns define conditions to trigger the auto reply: if both fields match, the MO is sent and the additional action is triggered. To specify a wildcard, just leave the field empty. Keyword matches against the first alphanumeric word in the MO text, ignoring punctuation and leading spaces. It means that the Keyword field cannot contain spaces and must be a single word.

Also, the *Keyword* setting is a prefix. e.g. if you specify "AD", it will match "AD", "ADAPT" and "ADOBE". If you have multiple keywords with a common prefix, pay attention to the order, keywords are processed top to bottom.

The *Reply* column is the text to reply. No personalization is available in this field, the reply text is always the same. If you leave this field empty, no message will be replied but the additional action will be triggered anyway.

The *Additional* action column provides an extra action to do when both keyword and short code match (empty short code matches all short codes). Currently, you can send to quarantine or remove from quarantine. If you specify an additional action but leave the reply field empty, the action will be executed but no reply will be sent. Quarantine is applied only for the specified short code, or all short codes if the field is left empty.

All entries in the table are processed in the specified order, until one rule matches. If multiple rules match a MO, only the topmost rule will be applied.

>[!NOTE]
>
>The **send full phone number** setting has an impact on the behavior of automatic reply quarantine mechanism: if send full phone number is not checked, the phone number put in quarantine will be prefixed by a plus sign ("+") to make it compatible with the international phone number format.

>[!NOTE]
>
>In a mid-sourcing architecture, applying auto-reply for the extended SMPP connector requires to add write access for the mid operator on the external account folder.

>[!IMPORTANT]
>
>Be careful with encodings in automatic replies, especially when copy-pasting. Word processing software tend to add extra formatting, such as adding non-breaking spaces or changing quotes to apostrophes.