---
date: 2024-11-02T15:02
tags:
  - "#cybersecurity"
  - "#web-security"
cssclasses:
  - pen-green
  - page-grid
---
**Denial of Service (DoS)** is the act of performing an attack which prevents the system from providing services to legitimate users

### Remediation
***
- enable IDS/IPS protection
- check open_basedir permission
- Enable SELinux extension
- use W3C recommended logs format
- apply restricted ACI and block remote administration
- remove unnecessary modules and ISAPI filters
- remove unnecessary files and folders
- relocate sites to non-system partition
- enable auditing
- establish regular patching
- limit functionality
- conduct periodic vulnerability scanning

#### DoS Vectors
***
**Application crashing:**
- Memory access violation (Buffer Overflow)
- Various Exceptions

**Data Destruction**
**Resource Depletion**
- Memory
- CPU
- Bandwidth
- Disk Space

#### Tools
***
- slowloris
- sparta

#### Reason
***
- Unnecessary services launched
- Default configuration
- Improper configuration
- Improper maintenance

