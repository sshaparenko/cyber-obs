---
date: 2024-11-01T13:46
tags:
  - "#cybersecurity"
  - "#SET"
  - "#ICM"
cssclasses:
  - pen-green
  - page-grid
  - recolor-images
  - center-images
  - center-titles
---
### Security Controls: Safeguards and Countermeasures
***
**Cybersecurity Controls** are instruments used to prevent, detect and mitigate cyber threats and attacks. 

Controls revolve around four essentials:
- People
- Technology
- Processes
- Strategy

#### Cybersecurity Controls Types
***

**The basic cybersecurity controls** dived into three types:

1. **Administrative:** include policies, procedures, or guidelines that define individual or business practices following the org security goals
2. **Physical:** implement security measures in a defined structure to prevent unauthorized access to sensitive data
3. **Technical Controls:** sue technology to decrease hardware and software vulnerabilities. Installation of automated software tools protects the assets

#### Security Controls Functions
***
The practical use of a specific security control is the purpose or the reason of choosing and implementing this countermeasure

In this context, security controls could be classified into the following types:

1. **Preventive Controls:** attempt to prevent an incident from occurring
2. **Detective Controls:** attempt to detect incidents after they have occurred
3. **Corrective Controls:** attempt to reverse the impact of an incident
4. **Deterrent controls:** attempt to discourage individuals from causing an incident
5. **Compensating controls:** are alternative controls used when a primary control is not feasible

##### Example

|                         | Preventive                                                                         | Detective                                               | Corrective                                                               | Deterrent                               | Compensating                                                      |
| ----------------------- | ---------------------------------------------------------------------------------- | ------------------------------------------------------- | ------------------------------------------------------------------------ | --------------------------------------- | ----------------------------------------------------------------- |
| Physical Controls       | \|`Picture IDs;` \|`Biometrics;`<br>\|`Monitor and alarm systems;`<br>\|`Cameras;` | \|Log monitoring;<br>\|Surveillance cameras;<br>\|CCTV; | \|Backups and system recovery;<br>\|Repair physical damage               | \|Cable locks;<br>\|Guards;             | \|Multi factor authentication;                                    |
| Technical Controls      | \|Firewalls<br>\|Antivirus and Anti-malware software<br>\|IPS                      | \|SIEM<br>\|IDS                                         | \|Vulnerability patching;<br>\|Reboot a system;<br>\|Quarantine a virus; | \|Hardware lock;                        | \|One-time password;<br>\|Encryption;                             |
| Administrative Controls | \|Policies;<br>\|Procedures;<br>\|Trainings;<br>\|Standards;                       | \|Security Audits;<br>\|Trend Analysis;                 | \|Have an IRP<br>\|Implement BCP                                         | \|Guidelines<br>\|Regulations<br>\|Laws | \|Monthly reports<br>\|Employee awareness training<br>\|Insurance |

#### Antivirus vs Anti-Malware
***
**Antivirus** software is designed to detect and remove viruses and other malicious software from a system. It protects the digital environment against more established threats, such as viruses, worms and Trojans.

**Anti-malware** is a program that safeguards the system from all sorts of malware, including Trojans, worms and adware. Note that anti-malware typically defends the system against newer and more complex programs to strengthen system security.

#### Firewalls, IDS and IPS
***
**Firewall** is a web security device installed on a corporate network. The primary function of the firewall is to inspect all packets entering, leaving and passing through the network to prevent unauthorized access between two or more computers

**Intrusion Detection System** detects and monitors traffic for illegal packets or suspicious activity and alerts you if it detects any. An IDS is a software that scans the network and transmits the data for further analysis so that you can take appropriate action

**Intrusion Prevention System** detects malicious packets, sends a report and blocks the packet. Unlike IDS, which only detects are reports packets, IPS also tries to block them.

#### Layering Security Controls
***

**Defense-in-Depth (DiD)** is an approach to cybersecurity in which a series of defensive mechanisms are layered in order to protect valuable data and information

The number of layers is a function of asset value, criticality, the reliability of each control and the degree of exposure. Excessive reliance on a single control is likely to create a false sense of confidence.

When developing DiD, consider the following questions:
1. What vulnerabilities are addressed by each layer or control?
2. How does the layer mitigate the vulnerability
3. How does each control interact with another?

There are several ways of the implementation:

![[Pasted image 20241101144226.png]]
![[Pasted image 20241101144559.png]] 
![[Pasted image 20241101144822.png]]
