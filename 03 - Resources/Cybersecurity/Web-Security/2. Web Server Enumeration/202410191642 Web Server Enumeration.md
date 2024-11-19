---
date: 2024-10-19T16:42
tags:
  - "#cybersecurity"
  - "#SET"
cssclasses:
  - pen-green
  - page-grid
---
#### Terminology
***

#### DNS Enumeration
***
DNS Enumeration is the process of gathering detailed information about a target domain’s DNS records and structure. 

The primary goal is to extract as much as possible about the DNS infrastructure associated with a domain

**Key techniques:**
1. <u>Zone Transfers(AXFR):</u> Attempting to retrieve the entire DNS zone file which contains all DNS records for a domain.
2. <u>DNS Record Lookups:</u> Querying a specific type of DNS Records such as:
	1. [[A record]]
	2. [[MX records]]
	3. [[CNAME records]]
	4. [[DNS TXT]]
3. <u>Brute-forcing Subdomains</u>: Attempting to guess subdomains using a list of common names
4. <u>Reverse DNS Lookups</u>: Discovering domain names associated with a specific IP address

Here is an example of `dnsenum` enumeration

```bash
dnsenum fuib.com

acg.fuib.com.                 3600     IN    A        194.44.66.6              
autodiscover.fuib.com.        3483     IN    A        194.44.66.146
ext.fuib.com.                 3600     IN    A        194.44.66.6
ftp.fuib.com.                 3600     IN    CNAME    eftp-001.fuib.com.
eftp-001.fuib.com.            3600     IN    A        194.44.66.54
ftps.fuib.com.                3600     IN    A        194.44.66.60
mail.fuib.com.                3600     IN    A        194.44.66.48
mail.fuib.com.                3600     IN    A        194.44.66.47
news.fuib.com.                3600     IN    A        194.44.66.39
ns.fuib.com.                  2316     IN    A        194.44.66.49
ns2.fuib.com.                 2316     IN    A        194.44.66.50
owa.fuib.com.                 3600     IN    A        194.44.66.146
projects.fuib.com.            3600     IN    CNAME    prj-002-vs.fuib.com.
prj-002-vs.fuib.com.          3600     IN    A        10.55.25.99

```
##### Tools
- `dnsrecon`
- `subbrute`
- `fierce`
- `nmap`
- `dnsenum`
- `recon-ng`

#### Virtual Host Enumeration
***
**Goal:** enumerate possible old subdomains with removed A record; internal subdomains

In case, if a subdomain is internal (not accessible through Internet), we can try to find it by creating a HOST header with a wordlist

Here is an example of vhost enumeration with `gobuster`. See [[202410211459 Gobuster enumeration|Gobuster enumeration]] for more info

```bash
#!/bin/bash

target='http://89.184.67.44'
base_domain='fuib.com'
wordlist='./subdomains-top1million-5000.txt'

gobuster vhost -k --domain $base_domain --append-domain -u $target -w $wordlist -z
```

```bash
Found: beta2.fuib.com Status: 200 [Size: 49]
Found: sky.fuib.com Status: 200 [Size: 49]
Found: portal2.fuib.com Status: 200 [Size: 49]
Found: kids.fuib.com Status: 200 [Size: 49]
Found: vmail.fuib.com Status: 200 [Size: 49]
Found: messenger.fuib.com Status: 200 [Size: 49]
Found: ns51.fuib.com Status: 200 [Size: 49]
Found: website.fuib.com Status: 200 [Size: 49]
Found: lb2.fuib.com Status: 200 [Size: 49]
Found: weather.fuib.com Status: 200 [Size: 49]
Found: max.fuib.com Status: 200 [Size: 49]
Found: webapps.fuib.com Status: 200 [Size: 49]
Found: white.fuib.com Status: 200 [Size: 49]
Found: gps.fuib.com Status: 200 [Size: 49]
Found: listas.fuib.com Status: 200 [Size: 49]
```

##### Tools
- `wfuzz`
- `gobuster`
#### Port scanning
***
**Goal:** enumerate open ports and services that could be running on those ports

##### Tools
- `nmap`

#### Web Application Crawling
***
Crawling a website is a process of browsing a website in a methodical or automated manner to enumerate  all the resources encountered along the way

##### Tools
- `Burp Suite`
- `HTTrack`
- `wget`
- `WebCopier`
- `TeleportPro`
