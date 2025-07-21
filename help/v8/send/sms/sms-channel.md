---
title: SMS channel characteristics
description: Learn the characteristics of SMS channel
feature: SMS
role: User
level: Intermediate
exl-id: abab6f15-43ea-42fc-817b-8dbd88df82f7
---
# SMS channel characteristics {#sms-channel}

>[!IMPORTANT]
>
>This capability is available to all Campaign FDA environments. It is **not** available for Campaign FFDA deployments. This documentation applies to Adobe Campaign v8.7.2 and later. To switch from the legacy to the new SMS connector, refer to this [technote](https://experienceleague.adobe.com/docs/campaign/technotes-ac/tn-new/sms-migration){target="_blank"}
>
>For older versions, please read the [Campaign Classic v7 documentation](https://experienceleague.adobe.com/en/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up/sms-set-up){target="_blank"}.

## SMS types {#sms-types}

When sending SMS through an SMS provider, you will encounter 3 different kinds of SMS:

* **SMS MT (Mobile Terminated)**: This is an SMS that is emitted by Adobe Campaign toward mobile phones through the SMPP provider.
* **SMS MO (Mobile Originated)**: This is an SMS that is sent by a mobile toward Adobe Campaign through the SMPP provider.
* **SMS SR (Status Report) or DR or DLR (Delivery Receipt)**: This is a return receipt sent by the mobile to Adobe Campaign through the SMPP provider indicating that the SMS has been received successfully. Adobe Campaign may also receive SR indicating that the message could not be delivered, often with a description of the error.

You need to distinguish between acknowledgments (RESP PDU, part of the SMPP protocol) and SR. A SR is a kind of SMS that is sent through the network end-to-end, whereas an acknowledgement is only a confirmation that one transfer has been successful. 

Both acknowledgements and SR can trigger errors, distinguishing between the two will help troubleshooting.

### Information carried by an SMS  {#sms-info}

An SMS carries more information than text. Here a list of what you can expect to find in an SMS:

* The text, which is limited to 140 bytes, which means between 70 and 160 characters depending on the encoding. See [SMS text encoding](#sms-text-encoding) below for details and limitations.
* A recipient address, sometimes called ADC or MSISDN (the technical name for "phone number"). That's the number of the mobile that will receive the SMS.
* A sender address, that can be called oADC or sometimes sender id. That can be a phone number (in day to day use), a short code (when sent through a provider) or a name (this is an optional feature, in that case you cannot reply to the SMS).
* A flag to indicate if the message is a flash message (a flash message is a pop-up that is not stored in memory)
* A flag to indicate whether a SR is expected or not.
* A validity date, after which no network equipment is allowed to retry (not always present or respected).
* A data_coding field, which indicates the encoding of the text.

## SMS text encoding {#sms-text-encoding}

>[!IMPORTANT]
>
>Encoding of SMS is a vast, complex subject with many traps and non-conforming implementations!

The first rule is **always contact the SMPP provider in case of encoding problems**. Only they, have precise knowledge of the encoding they support and special rules that may apply due to limitations in their technical platform. Make them check what you send them and what they send back to you, it is the only path to a successful and stable interconnection.

SMS messages use a special 7 bits encoding, often called the GSM7 encoding.  Wikipedia has [a good article about it (GSM 03.38 in English)](https://en.wikipedia.org/wiki/GSM_03.38).

In the SMPP protocol, GSM7 text will be expanded to 8 bits per character for easier troubleshooting. The SMSC will pack it into 7 bits per character before it is sent to the mobile. This means that the short_message field of the SMS may be up to 160 bytes long in the SMPP frame whereas it is limited to 140 bytes when sent on the mobile network (the most significant bit is simply discarded).

In case of encoding problems, here are some important things to check:
* First, make sure that you know which characters belong to which encoding. GSM7 is infamous for its partial support of diacritical marks (accents). Especially in French, where é and è are part of GSM7, but ê, â or ï are not. The same applies to Spanish.
* The C with cedilla (ç) is present only in upper case in the GSM7 alphabet, but some phones render it in lower case or "smart" case: the general recommendation is to completely avoid it and remove the cedilla (it is still very readable in French) or switch to UCS-2.
* **Do not use ASCII in SMS!** unless explicitly requested by the SMPP provider: This encoding wastes space because it has 8-bit characters and less coverage than GSM7. This encoding may be required for CDMA networks (used in Northern America).
* Latin-1 is not always supported. Check the compatibility with your SMPP provider before attempting to use Latin-1.
* National language shift tables are not supported by the Adobe Campaign connector. You must use UCS-2 or other data_coding instead.
* UCS-2 and UTF-16 are often mixed by phones. This is a problem for people sending emojis and other rarely used characters not present in UCS-2.
* Sole older phones don't have font glyphs for all UCS-2 characters. Latest smartphones tend to be able to display rare characters rather easily, older smartphones often lack many emojis, and very old feature phones generally have support limited to what's useful in the native tongue of the country they were bought in. If you want to use emoji or ASCII-art of some sort, test it on a wide variety of phones before sending. Campaign preview does not simulate missing glyphs and will display whatever symbols are available on the web browser displaying the preview.

The *data_coding* field tells which encoding is used. A major problem is that the value 0 means *default SMSC encoding* in the specification, in general it means GSM7, but that's not always the case. Check with the SMPP provider which encoding is associated with data_coding = 0. Other data_coding values tend to follow the specification, but the only way to be sure is to check with the SMPP provider.

The maximum size of a message depends on its encoding. This table sums up all the relevant information:

| Encoding | Usual data_coding | Message size (characters) | Part size for multipart SMS | Available characters | 
|:-:|:-:|:-:|:-:|:-:|  
| GSM7 | 0 | 160 | 152 | GSM7 basic character set + extension (extended characters take 2 characters) | 
| Latin-1 | 3 | 140| 134 | ISO-8859-1 | 
| UCS-2 UTF-16 | 8 | 70 | 67 | Unicode (varies from phone to phone) | 

## Multipart SMS (long SMS) {#multipart-sms}

Multipart SMS (often called long SMS) are SMS that are sent in multiple parts. Due to technical limitations in the mobile network protocol, a SMS cannot be larger than 140 bytes (see the SMS text encoding section below for the number of characters that can fit in a SMS) so longer messages need to be split.

Each part of a long message is an individual SMS. These parts travel independently on the network and are assembled by the receiving mobile phone. In order to handle retries and connectivity problems gracefully, Campaign sends parts in reverse order and asks for a SR only on the first part of the message (the one that is sent last); as the mobile phone only displays a message when it received its first part, retries on additional parts won't produce duplicates on the mobile phone.

The maximum number of SMS per message can be set per delivery using the Maximum number of SMS per message setting in the delivery template. Messages that go above this limit will fail during sending with a SMS too long failure reason.

There are 2 ways to send long SMS:

* UDH
* message_payload

UDH is the default and recommended way to send long messages. In this mode the connector splits the message in multiple SUBMIT_SM PDUs with UDH information in them. This protocol is the one used by mobile phones themselves, meaning that Campaign has the most control over the message generation, making it capable to compute exactly how many parts were sent and how they were split.

*message_payload* is a way to send the whole long message in a single SUBMIT_SM PDU. The provider will have to split it, which means that it's impossible for Campaign to know exactly how many parts have been sent. Some providers require this mode, only use it if they don't support UDH.

See the description of the esm_class, short_message and message_payload fields of the SUBMIT_SM PDU above for more details about the protocol and formats.

>[!NOTE]
>
>While Adobe Campaign supports both UDH and message_payload for sending, only message_payload is supported for incoming SMS (MO).
