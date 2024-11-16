---
date: 2024-11-15T15:58
tags:
  - cybersecurity
  - ICM
cssclasses:
  - pen-green
  - page-grid
---
### System Hardening checklist
***

- [ ] **Manage access:** set strong passwords and user roles, remove unnecessary OS users. <u>You should have only one super administrator or root account.</u>
    
- [ ] **Patch vulnerabilities**

- [ ] **Control network traffic:** install security systems behind a firewall. Isolate systems from public network. Use VPN to connect to a network. Encrypt all communications
    
- [ ] **Remove unnecessary software applications:** remove all unnecessary OS components, disable services that you don’t need, disable app feature that is not required
    
- [ ] **Secure communications**: use the best encryption methods, only important ports should work, disable all insecure ports like Telnet and SMBv1
    
- [ ] **Ongoing monitoring:** review logs, attention to elevating privileges, user access and authentication. Mirror logs to another location. Scan regularly for vulnerabilities
    
- [ ] **Harden remote sessions:** if you enable SSH, make sure to use robust certificate or password. Don’t use the default port
    
- [ ] **Regular backups** following the 3-2-1 rule to protect data