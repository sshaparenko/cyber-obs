---
date: 2024-11-03T08:08
tags:
  - "#cybersecurity"
  - "#reporting"
cssclasses:
  - pen-green
  - page-grid
---
### Penetration Testing

A penetration testing goes beyond automated scans and can leverage vulnerability scan data to help guide exploitation. Like vulnerability scans, these can be performed from an internal or external perspective. 

Depending on the type of pentest, we may not perform any kind of vulnerability scanning at all.

<u>“black box“ penetration test</u> - a type of pentest where we have no more information then the name of the company during an external or a network connection for an internal pentest

<u>”grey box” penetration test</u> - a type of pentest where we are given just in-scope IP addresses/CIDR network ranges

<u>“white box” penetration test</u> - a type of pentest where we may be given credentials, source code, configurations and more.

The pentest can be performed with **zero evasion** to attempt to uncover as many vulnerabilities as possible. In this type of test, we are not trying to hide ourselves. 

From a **hybrid evasive** standpoint to test the customer defenses by starting out evasive to see at what level internal security teams/monitoring tools detect and block us. Typically once we are detected, the client will ask us to move to non-evasive testing for the remainder of the assessment.

Finally, we may be asked to perform **evasive testing** through the assessment. In this type of assessment, we will try to remain undetected for as long as possible and see what kind of access, if any, we can obtain while working stealthy.

#### Internal vs External
***

Similar to [[202411030942 Vulnerability assessment|vulnerability scanning]] perspectives, external pentest will typically be conducted from the perspective of an anonymous attacker on the internet. It may leverage OSINT data/publicly available information to gain access to sensitive data via applications or the internal network by attacking internet-facing hosts

Internal pentest may be conducted as an anonymous user on the internal network or as an authenticated user. IT’s typically conducted to find as many flaws as possible to obtain a foothold, perform horizontal and vertical privilege escalation, move laterally and compromise the internal network (typically the client’s Active Directory)

