---
date: 2024-10-07T12:09
tags:
  - cybersecurity
  - Networking
cssclasses:
  - page-grid
  - pen-blue
---
Two networking models describe the communication and transfer of data from one host to another. They are called `ISO/OSI model` and the `TCP/IP model`.

![[Pasted image 20241007145520.png]]

#### The OSI Model
***
The OSI model is a reference model that can be used to describe and define the communication between systems. The reference model has `seven` individual layers, each with clearly separated task.

The term OSI stands for Open System Interconnection model, published by the International Telecommunication Union (ITU) and International Organization for Standardization (ISO).

##### Physical Layer
***
The lowest layer of OSI Model. It’s responsible for the actual physical connection between devices. 

The Physical Layer contains information in form of bits.

**Functions of the Physical Layer:**
- **Bit Synchronization:** the physical layer provides synchronization of the bits by providing a clock. This clock controls both sender and receiver thus providing synchronization at the bit level
- **Bit Rate Control:** the physical layer also defines the transmission rate i.e. the number of bits per second
- **Physical Topologies:** Physical layer specifies how the different devices/nodes are arranged in a network i.e. Bus, Star or Mesh
- **Transmission Mode:** Physical layer also defines how the data flows between the two connected devices. The various transmission modes possible are [[Simplex]], [[Half-Duplex]] and [[Full-Duplex]] 

> - Hub, Repeater, Modem and Cables are Physical Layer devices
> - Network Layer, Data Link Layer and Physical Layer are also known as Lower Layers or Hardware Layers

##### Data Link Layer
***
The DLL is responsible for the node-to-node delivery of message. The main function of DLL is to make sure data transfer is error-free from one node to another, over the physical layer. 

When a packet arrives in a network, it’s the responsibility of the DLL to transmit it to the Host using its [[MAC Address]]

The DLL is divided into two sub-layers:
- [[Logical Link Control]] (`LLC`)
- [[Media Access Control]] (`MAC`)

The packet received from the Network layer is further divided into frames depending on the frame size of the [[NIC (Network Interface Card)]].

The [[MAC Address]] is obtained by placing an [[APR(Address Resolution Protocol)]] request onto the wire asking “Who has that IP address?“ and the destination host will reply its MAC Address

**Functions of the DLL:**
- **Framing:** Framing provides a way for a sender to transmit a set of bits that are meaningful to the receiver. This can be accomplished by attaching special bit patterns to the beginning and end of the frame
- **Physical Addressing:** After creating frames, the DLL adds physical addresses ([[MAC Address]]) of the sender and/or receiver in the header of each frame
- **Error Control:** The DLL has a mechanism of error control in which it detects and retransmits damaged or lost frames.
- **Flow Control:** The data rate must be constant on both sides else the data may get corrupted thus, flow control coordinates the amount of data that can be sent before receiving an acknowledgment
- **Address Control:** When a single communication channel is shared by multiple devices, the MAC sub-layer of the DLL helps to determine which device has control over channel at a given time

> - Packet in the DLL is referred to as `Frame`
> - DLL is handled by [[NIC (Network Interface Card)]] and device drivers of the host machine
> - Switch & Bridge are DLL devices

##### Network Layer
***
The network layer works for the transmission of the data from one host to the other located in different networks.

It also takes care of packet routing i.e. selection of the shortest path to transmit the packet from the number of routes available

The sender and receiver’s [[202409091926 IP Address]] are placed in the header by the network layer

**Functions of the Network Layer:**
- **Routing:** The Network layer protocols determine which route is suitable from source to destination
- **Logical Addressing:** To identify each device inter-network uniquely, the network layer defines an addressing scheme. The sender & receivers IP addresses are placed in the header by the network layer. Such an address distinguishes each device uniquely and universally

> - Segment in the Network layer is referred to as `Packet`
> - Network layer is implemented by networking devices such as routers and switches

##### Transport Layer
***


#### THE TCP/IP Model
***
TCP/IP (Transmission Control Protocol/Internet Protocol) is a generic term for many network protocols. The protocols are responsible for the switching and transport of data packets on the Internet. 

TCP/IP does not only refer to these two protocols but is usually used as a generic term for an entire protocol family. For example `ICMP (Internet Control Message Protocol)` or `UDP (User Datagram Protocol)` belongs to the protocol family. 

The protocol family provides the necessary functions for transporting and switching data packets in a private or public network.

#### ISO vs TCP/IP
***
`TCP/IP` is a protocol that allows hosts to connect to the Internet. In contrast to `OSI`, it allows a lightening of the rules that must be followed, provided that general guidelines are followed.

`OSI` is a communication gateway between the network and end-users. The OSI model is usually referred to as the reference model because it is newer and more widely used. It is also known for its strict protocol and limitations.

#### SEE ALSO
***
- [[202410071508 Packet Transfers]]

#### LINKS TO THIS PAGE
***