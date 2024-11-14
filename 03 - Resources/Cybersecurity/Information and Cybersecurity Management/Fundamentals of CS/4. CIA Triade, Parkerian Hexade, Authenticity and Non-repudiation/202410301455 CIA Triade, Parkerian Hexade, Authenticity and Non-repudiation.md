---
date: 2024-10-30T14:55
tags:
  - "#cybersecurity"
  - "#SET"
  - "#ICM"
cssclasses:
  - pen-green
  - page-grid
---
#### Terminology
***
**Authenticity:** a security measure that was designed to verify an individual’s authorization to receive specific information. 

Authentication prevents impersonation and requires users to confirm their identities before access to systems and resources. This includes usernames, passwords, emails, biometrics 

**Non-repudiation:** a characteristics that guarantees that your data delivery is done to the sender only

The receiver of the information can also verify the sender. It should be indisputable that the sender sent the message, and there should be no denial that the receiver received it.

## Authenticity and Non-repudiation confirm the legality and integrity of data transmission

#### CIA Triade
***

| Requirement                                                                                                       | Impact and Potential Consequences                                                                                                                                                                                         | Methods of Control                                                                                 |
| ----------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- |
| **Confidentiality:** <br>the protection <br>of information<br>from unauthorized<br>disclosure                     | - Disclosure of information protected by privacy laws<br><br>- Loss of public confidence<br><br>- Loss of competitive advantage<br><br>- Legal action against the enterprise<br><br>- Interference with national security | - Access Controls<br><br>- File Permissions<br><br>- Encription                                    |
| **Integrity:**<br>the accuracy and completeness of<br>information by <br>business values<br>and expectations      | - Inaccuracy<br><br>- Erroneous decisions<br><br>- Fraud                                                                                                                                                                  | - Access Controls<br><br>- Logging<br><br>- Digital Signatures<br><br>- Hashes<br><br>- Encryption |
| **Availability:**<br>the ability to<br>access information<br>and resources<br>required by<br>the business process | - Loss of functionality and operational effectiveness<br><br>- Loss of productive time<br><br>- Interference with the enterprise’s objectives                                                                             | - Redundancy<br><br>- Backups<br><br>- Access Controls                                             |

#### The Parkerian Hexad
***
This is an alternative model to the CIA Triad, since the Triad was too insufficient to describe the totality of what needed to be considered in cybersecurity field

The Parkerian Hexad model adds three new entities to the CIA triade. Those are <u>Possession</u>, <u>Authenticity</u> and <u>Utility</u>

**Possession:** or control, was added to protect against the idea that sensitive data could be in the possession and control of an unauthorized party without violating privacy.

This component also deals with protecting public data, which can be proprietary and copyrighted.


**Authenticity:** refers to the assurance that a message, transition or other exchange of information is from the source if claims to be from. Authenticity involves proof of identity.



**Utility:** refers to the usefulness of data. It focuses on much-overlooked concept when it comes to data. It is often confused or assumed with availability, but the two are distinct. 

Suppose a customer sends an email to a retail company in a language that the retail company does not recognize. In that case the message may meet the requirements of five of the six Parkerian Hexad components except for utility.

#### Safety, Security and Privacy
***
An organization’s data is one of its most valuable assets and must be protected accordingly. There are so many ways an organization’s data could potentially be lost or compromised and organizations must take a multifaceted approach to ensure the well-being of their data

This means, focusing on three key areas:

**Safety:** data safety is protecting critical information from corruption, compromise or loss. An organization must identify the data that must be protected and design policies to ensure that the data can be recovered

**Security:** data security is the defense of digital information against internal and external; malicious and accidental threats.

**Privacy:** data privacy determines what data in a computer system can be shared with third parties


