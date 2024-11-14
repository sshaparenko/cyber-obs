---
date: 2024-10-27T00:31
tags:
  - "#cybersecurity"
  - "#SET"
cssclasses:
  - pen-green
---
#### Directory Traversal Attack
***

Using the term “../../” to access directories outside web application folder.

Attacker can user trial and error method to navigate outside the web site root folder and obtain sensitive information

```
http://bad.com?file=../../../../../../../../../../etc/passwd
```

**To protect from path traversal, filter input parameters:**
```
/
../
..\
%00 (NULL BYTE)
```

#### Access Attack
***

**Targets:** SSH, FTP, SMTP, Telnet, Server web console (web form), Hosting panel web console, MySQL/PostgreSQL

**Reasons:** system users for all services, opened services, default credentials, default configurations

**Tools:** THC Hydra, Medusa, wfuzz, Burp Suite

#### Shellshock / Bushbug
***
