---
product: campaign
title: Technote - Asymetric Encryption and Decryption in Adobe Campaign
description: Technical Note - Asymetric Encryption and Decryption in Adobe Campaign
hide: yes
hidefromtoc: yes
---
# Technote: Asymmetric Encryption and Decryption in Adobe Campaign {#asymetric-encryption}

Public-key cryptography, or asymmetric cryptography, is the field of cryptographic systems that use pairs of related keys. Each key pair consists of a **public key** and a corresponding **private key**.

* The **public key** is shared openly and used to encrypt data.

* The **private key** is kept secret and used to decrypt data.

This approach ensures that even if someone has the public key, they cannot decrypt the message without the private key. It provides key security features like confidentiality, authentication, and integrity.

Starting Adobe Campaign v8.8.3, two new Javascript functions are being added for encryption and decryption:

* Encryption using public key: `rsaPublicEncrypt(data, base64EncodedPublicKey, useOAEPpadding)`

* Decryption using private key: `rsaPrivateDecrypt(encryptedData, base64EncodedPrivateKey, useOAEPpadding)`


Example:

```Java

// Encryption with PKCS#1 v1.5 padding (default)
var encrypted = rsaPublicEncrypt(
    "Secret message",
    "LS0tLS1CRUdJTiBQVUJMSUMgS0VZLS0t..." // Base64 encoded public key
);
 
// Encryption with OAEP padding
var encryptedOAEP = rsaPublicEncrypt(
    "Secret message",
    "LS0tLS1CRUdJTiBQVUJMSUMgS0VZLS0t...", // Base64 encoded public key
    true
);
 
// Decryption
var decrypted = rsaPrivateDecrypt(
    encrypted,
    "LS0tLS1CRUdJTiBSU0EgUFJJVkFURSBLRVkt..." // Base64 encoded private key
);
```

