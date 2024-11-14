---
date: 2024-11-08T12:20
tags:
  - "#cybersecurity"
  - "#ICM"
  - "#PKC"
cssclasses:
  - pen-green
  - page-grid
---
#### How Public Key Certificate Work
***

When a secure connection is established, the server presents its public key certificate to the client. The client checks:

1. If the certificate is valid (e.g., not expired and properly signed by a trusted CA)
2. The identity information in the certificate (such as domain name) matches the entity it’s trying to connect to

Once verified, the client can use the public key in the certificate to encrypt information or check the server’s digital signatures