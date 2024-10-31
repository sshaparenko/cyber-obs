---
date: 2024-10-21T14:59
tags:
  - "#cybersecurity"
  - "#gobuster"
cssclasses:
  - pen-green
  - page-grid
---

#### Gobuster DIR command
***
The DIR mod is used for finding hidden directories and files

##### Flags
There are 2 flags required to run a basic scan are `-u` and `-w`. The example uses `common.txt` from the SecList wordlist

```bash
gobuster dir -u https://example.com -w /usr/share/wordlist/Discovery/Web-Content/commin.txt
```

Example result
```bash
Example results
===============================================================
Gobuster v3.1.0
by OJ Reeves (@TheColonial) & Christian Mehlmauer (@firefart)
===============================================================
[+] Url:                     https://example.com
[+] Method:                  GET
[+] Threads:                 10
[+] Wordlist:                /wordlists/Discovery/Web-Content/common.txt
[+] Negative Status codes:   404
[+] User Agent:              gobuster/3.1.0
[+] Timeout:                 10s
===============================================================
2022/03/01 10:34:16 Starting gobuster in directory enumeration mode
===============================================================
/assets              
/css                  
/download
```

##### !!!Threads!!!
***
Gobuster is fast, with hundreds of requests being sent using the default 10 threads. This speeds can create problems with the system it is running on. It could be beneficial to drop this down to 4 with `-t` flag.

Additionally it can be helpful to use the flag `--delay`, for example `--delay 1s` in other words
### if threads is set to `-t 4` and `--delay 1s`, this will send 4 requests per second
##### Results
***
Results are shown in the terminal or use `-o` option to record result into a file
##### Other DIR flag examples
***
To exclude status codes use `-n`

Use `-x` to search for a specific file extension. For example 
```bash
gobuster dir -u http://example.com -w path/to/wordlist -x .php, .txt -t 4 --delay 1s -o results.txt
```

#### Gobuster DNS
***
Use the DNS command to discover subdomains.

DNS Example
```bash
gobuster dns -q -r 8.8.8.8 -d example.com -w /usr/share/wordlsit/Discovery/DNS/subdomains-top1million-5000.txt -t 4 --delay 1s -o results.txt
```

`-q`: quite mode, don’t print the banner and other noise
`-r`: use custom DNS server (format server.com or server.com:port)
`-d`: domain string
`-w`: path to wordlist
`-t`: threads
`--delay`: delay
`-o`: write to file

Results
```bash
Found: www.example.com
Found: nagios.example.com
Found: dev.example.com   
Found: auto.example.com
```
#### Gobuster VHOST
***
The vhost command discovers Virtual host names on target web servers. Virtual hosting is a technique for hosting multiple domain manes on a single server.

Exposing hostnames on a server may reveal supplementary web content belonging to the target. vhost checks if the subdomain exists by visiting the formed URL and cross-checking the IP address

### When performing vhost enumeration, we send request to the web server itself. While performing DNS enumeration, we communicate with DNS server only. 

## So all the requests sent while performing vhost enumeration will be logged in the web server

Script
```bash
#!/bin/bash

target='http://89.184.67.44'
base_domain='example.com'
wordlist='./subdomains-top1million-5000.txt'

gobuster vhost -k --domain $base_domain --append-domain -u $target -w $wordlist
```

Result
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
Found: minecraft.fuib.com Status: 200 [Size: 49]

```

#### LINKS TO THIS PAGE
***
- [[202410191642 Web Server Enumeration]]