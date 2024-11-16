---
date: 2024-09-07T21:55
tags:
  - cybersecurity
  - Nmap
cssclasses:
  - page-grid
  - pen-green
---
#### Host Discovery
***
When we need to conduct a penetration testing for the entire network of a company, then we should, first of all, get an overview of which systems are online that we can work with.

To actively discover such systems on the network we can use various [[202409062122 Intro to Nmap|Nmap]] host discovery options. The most effective host discovery method is to use [[202409121900 ICMP|ICMP]] echo request.

It’s always recommended to store every single scan. This can later be used for comparison, documentation and reporting.

```bash
sudo nmap 10.129.2.0/24 -sn -oA tnet | grep for | cut -d" " -f5
```

```shell
10.129.2.4
10.129.2.10
10.129.2.11
10.129.2.18
10.129.2.19
10.129.2.20
10.129.2.28
```

| Scanning Options | Description                                                     |
| ---------------- | --------------------------------------------------------------- |
| 10.129.2.0/24    | Target network range                                            |
| -sn              | Disables port scanning                                          |
| -oA tnet         | Stores the result in all formats starting with the name ‘tnent’ |

##### This scanning method works only if the firewalls of the host allow it. Otherwise, we can use other techniques to find our the hosts are active or not. We will take a closer look at there techniques in [Firewall and IDS Evasion]()

#### Scan IP List