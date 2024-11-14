---
date: 2024-11-08T12:59
tags:
  - "#cybersecurity"
  - "#ICM"
  - "#Digital-signature"
cssclasses:
  - pen-green
  - page-grid
---
### How Digital Signature Works?
***

#### 1. Hashing the Data

First, the original document or message is processed through a hash function. A hash function takes any input and generates a fixed-size output called **hash value** or **digest**

The hash function is sensitive to any changes to the original document, which means that it will produce different results with different data. This ensures the **integrity** of the data 
#### 2. Encrypting the Hash (Signing)

The sender then **encrypts this digest** using their private key. The encrypted digest becomes **a digital signature**

Only the senders private key can create this digital signature (sign the data). This step is what provides **authenticity** and **non-repudiation** (meaning the sender cannot deny having signed the document)

#### 3. Sending the Document and Digital Signature


The sender transmits both the original document and the digital signature to the recipient

The document itself is sent in plaintext while the digital signature is attached to it

#### 4. Verification by the Recipient

The recipient uses the sender’s public key to decrypt the digital signature and retrieve the original hash value

The recipient also hashes the received document independently using the same hash function as the sender.

#### 5. Comparing the Hashes

The recipient compares the decrypted hash value from the digital signature with the hash value they computed

If the two hash values match, the document is verified as **authentic** and **untampered**