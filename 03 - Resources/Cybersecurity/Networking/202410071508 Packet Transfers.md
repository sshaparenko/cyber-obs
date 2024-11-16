---
date: 2024-10-07T15:08
tags:
  - cybersecurity
  - Networking
cssclasses:
  - pen-blue
  - page-grid
---
##### Terminology
***
- `Data encapsulation` - process of adding additional information when data is traveling in an OSI or TCP/IP model. The information is added on the sender’s side, from the Application to the Physical layer

- `Packet` - an encapsulated data in the network layer.

- `Segments` / `datagram` - encapsulated data in the transport layer. If the transmission uses TCP, then it called `segments`. If it uses UDP, its called `datagram`

- `frames` - encapsulated data in Data Link layer

#### OSI Model and Working of Encapsulation
***
1. No additional data will be added in **Application Layer** in the **TCP/IP Model** or the **Application**, **Presentation** and **Session** layers in the **OSI Model**
2. The Session layer sends data to the Transport layer
3. In the Transport layer, data is broken up into different pieces. It adds header in each of the broken data, which contains information like source port, destination port, sequence number, etc. Encapsulated data is called `segments` or `datagrams`
4. Data from **Transport** layer travels down to **Network** layer. Here the **layer 3 header** is added. It contains information like source IP destination IP and so on. The encapsulated data is called `packets`
5. Data from Network layer travels down to Data Link layer. here the new layer 2 header is added + trailer. it contains information like source MAC address, destination MAC address and so on. The trailer is used for error checking. The encapsulated data is called `frames`
6. Physical layer takes `frames` from Data Link layer. The encapsulated data in the physical layer is called `bits`

#### Protocol Data Unit (PDU)
***

| OSI layers         | PDU               |
| ------------------ | ----------------- |
| Application layer  | Data              |
| Presentation layer | Data              |
| Session layer      | Data              |
| Transport layer    | Segments/Datagram |
| Network layer      | Packets           |
| Data-Link layer    | Frames            |
| Physical layer     | Bits              |

#### LINKS TO THIS PAGE
***
- [[202410071209 Networking Models]]