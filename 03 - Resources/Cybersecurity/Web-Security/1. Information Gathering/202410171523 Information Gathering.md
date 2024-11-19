---
date: 2024-10-17T15:23
tags:
  - "#cybersecurity"
  - web-security
cssclasses:
  - pen-green
  - page-grid
---
#### Terminology
***
**AS** - Autonomous System

**MX Record** - DNS mail exchange (MX) record directs email to a mail server. The MX record indicates how email messages should be routed in accordance with the [[202410172025 SMTP|SMTP]] 

**SPF Record** - sender policy framework record is a type of [[DNS TXT]] record that lists all the servers authorized to send emails from a particular domain

[[202410172025 SMTP|SMTP]] - Simple Mail Transfer Protocol is a technical standard for transmitting mail over a network

DNS Round Robin - 

DNS PTR - DNS pointer record provides the domain name associated with an IP address. It’s opposite to A record, which provides the IP address associated with the domain name. 

DNS Zone Transfer
#### Web Application Information Gathering
***
Gathering information about the web application is the **initial phase** of any security testing/assessment/penetration test

The wealth of information will become useful in both <u>understanding the application logic</u> and <u>creating attack surface</u> 

#### Information types
***
- Application environment
	- Host type
	- Hosting provider
	- Lifetime
	- DNS: domain
	- IP addresses
- Application Infrastructure
	- OS
	- Web server
	- CMS/Framework
	- Database
- Application logic
	- Internal data flows
	- External Communications
#### IP Address detection
***

1. **Whois** service
	- Console commands
	- Web services
		- https://whois.net/
		- https://who.is/
2. **[[202409191958 BGP|BGP]]** - https://bgp.he.net/ 
3. **Tools:** `ping`, `dig`, `nslookup`
#### Search Engines and Tools
***
**Search engines:**
- **Bing:** *ip:142.250.186.206*
- **DuckDuckGo:** *ip:142.250.186.206*

**Special Tools:**
- [Shodan](https://www.shodan.io/about/products)
	- Web Sites
	- IP Addresses
- **Censys**
	- Web Sites
	- Certificates
	- IP addresses
- **Pentest-Tools**

**Companion checking**:
- **[[202410172017 SPF|SPF]]**
	- [Mxtoolbox](https://mxtoolbox.com)

#### Horizontal DNS Discovery (Mxtoolbox, Dig)
***
##### Goal: Find domains tied to the same entity

For example if you’re targeting `google.com` you want to find all [[A records]] (IPv4 addresses) or [[AAAA records]] (IPv6 addresses) that correspond to `google.com`

This can include:
- multiple IPs for `google.com` due to load balancing or geo-distributed servers
- different record types like [[CNAME]] (canonical names) or [[MX records]]

#### Vertical DNS Search (theHarvester)
***
##### Goal: Find subdomains of a given top level domain

For example, for `google.com` you would attempt to discover subdomains like:
- `mail.google.com`
- `docs.google.com`
- `maps.google.com`
- `drive.google.com`

**!theHarvester**

### Insights
***
1. You can use [2ip.ip](https://2ip.io) to look for <u>web sites on the same IP</u> and <u>CMS used to build them</u>
2. `theHarvester` can be too aggressive and that can lead to your IP being blocked. To use this tool, it’s necessary to use [[Proxy vs VPN|Proxy and VPN]]
3. You can look up resources by their certificate signatures and this can help on discovering resources on the cloud

#### Questions?
***
1. Cloudflare and Incapsula can block horizontal DNS Discovery?
2. 