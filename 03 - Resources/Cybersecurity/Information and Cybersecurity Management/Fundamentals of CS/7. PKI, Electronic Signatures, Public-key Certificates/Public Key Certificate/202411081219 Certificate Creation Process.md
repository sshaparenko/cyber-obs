---
date: 2024-11-08T12:19
tags:
  - "#cybersecurity"
  - "#ICM"
  - "#PKC"
cssclasses:
  - pen-green
  - page-grid
---
#### Certificate Creation Process
***

1. After the private key is formed and the related public key gets computed, the certificate authority asks for any identifying attributes for the private key owner and vets that information.
2. The public key and identifying attributes get encoded into a Certificate Signing Request (CSR), which the key owner signs to prove possessing that private key
3. The issuing certificate authority validates the request and signs the certificate with the CA’s private key