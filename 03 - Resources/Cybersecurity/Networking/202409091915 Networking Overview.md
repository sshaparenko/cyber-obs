---
date: 2024-09-09T19:15
tags:
  - Networking
cssclasses:
  - page-grid
  - pen-blue
---
#### Networking Overview
***
A network enables two computers to communicate with each other. There is a wide array of <u>topologies</u> (mesh / tree / star), <u>mediums</u> (ethernet / fiber / coax / wireless), and <u>protocols</u> (TCP / UDP / IPX) that can be used to facilitate the network.

It is important as security professionals to understand networking because when the network fails, the error may be silent, causing us to miss something.

#### How networking works?
***
![[Pasted image 20240909213318.png]]

We can imagine networking as the delivery of mail or packages sent by one computer and received by other.


Imagine a scenario where we want to visit a company’s website from out `Home Network`. In that case we exchange data with website located on `Company Network`. As we send mail or packets, we know the address where the packets should go. The website address or `Uniform Resource Locator` (URL) which we enter into the browser is also known as `Fully Qualified Domain Name` (FQDN).

FQDN: `www.hackthebox.eu`
URL: `https://www.hackthebox.eu/example?floor=2&office=dev`

As soon as we send our packets through the `router`, the packet is forwarded to `Internet Service Provider` (ISP). ISP looks for the address of this service (via `DNS`) and returns IP address.

When the web server receives our request, it sends packets in response via `Company Network` `router` to `ISP` and then to our IP address.

#### Extra Points
***
In that diagram it’s better to have five separate networks for the Company Network

1. The Web Server should be in DMZ (Demilitarized Zone) because clients on the internet can initiate communications with the website, making it more likely to become compromised. Placing it in a separate network allows the administrators to put networking protections between the web server and other devices

2. Workstations should be on their own network and, in perfect world, each workstation should have a Self-Hosted Firewall rule preventing it from talking to other workstations. If a Workstation is on the same network as a Server, networking attack like [[spoofing]] or [[man in the middle]] become more of an issue.

3. The Switch and Router should be on an “Administration Network”. This prevents workstations from snooping in on any communication between these devices.

	> I have often performed a Penetration Test and saw OSPF (Open Shortest Path First) advertisements. Since the router did not have a `trusted network` anyone on the internal network could have sent a malicious advertisement and performed a [[man in the middle]] attack against any network

4. IP Phones should be on their own network. Security-wise this is to prevent computers from being able to eavesdrop on communication. In addition to security, phones are unique in the sense that latency/lag is significant. Placing them on their own network can allow network administrators to prioritize their traffic to prevent high latency more easily

5. Printers should be on their own network. This may sound weird, but it is next to impossible to secure a printer. Due to how Windows works. If a printer tells a computer authentication is required during a print job, that computer will attempt an [[NTLMv2]] authentication, which can lead to passwords being stolen. Additionally, these devices are great for persistence and in general, have tons of sensitive information sent to them

### [More on NTLMv2 Attack](https://0xdf.gitlab.io/2019/01/13/getting-net-ntlm-hases-from-windows.html)

#### LINKS TO THIS PAGE
***
