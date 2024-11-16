---
date: 2024-09-22T19:04
tags:
  - Networking
cssclasses:
  - pen-blue
  - page-grid
---
A `network topology` is a typical arrangement and `physical` or `logical` connections between devices in a network. 

Computers are `hosts`, such as `clients` and `servers`, that actively use the network. They also include `network components` such as `switches`, `bridges`, and `routers`, which have a distribution function and ensure that all network hosts can establish a logical connection with each other.

### The network topology determines the components to be used and the access methods to the transmission media

The [[202409221947 Transmission Medium|transmission medium]] layout used to connect devices is the `physical topology` of the network. For conductive or glass fiber media, this refers to the cabling plan, the position of the `nodes` and the connection between the nodes and the cabling.

In contrast `logical topology` is how the signals act on the network media or how the data will be transited across the network from one device to the devices’ physical connection.

We can divide the entire network topology area into three areas:

#### 1. Connections
***

| Wired connections    | Wireless Connections |
| -------------------- | -------------------- |
| Coaxial cabling      | Wi-Fi                |
| Glass fiber cabling  | Cellular             |
| Twisted-pair cabling | Satellite            |
| and others           | and others           |

#### 2. Nodes - Network Interface Controller (NICs)
***
- Repeaters
- Hubs
- Bridges
- Switches
- Router/Modem
- Gateways
- Firewalls

Network nodes are the [[202409221947 Transmission Medium|transmission medium’s]] connection points to transmitters and receivers of electrical, optical and radio signals in the medium. A node may be connected to a computer, but certain types may have only one microcontroller on a node or may have no programmable devices at all

#### 3. Classification
***
We can imagine a topology as a virtual form or `structure of a network.` This form does not necessarily correspond to the actual physical arrangement of the devices in the network.

Therefore these topologies can be either `physical` or `logical`. For example, the computers on a LAN may be arranged in a circle in a bedroom, but it’s very unlikely to have an actual ring topology.

Network topologies are divided into the following eight basic types:
- Point-to-Point
- Bus
- Star
- Ring
- Mesh
- Tree
- Hybrid
- Daisy Chain

##### Point-to-Point
***
The simplest network topology with a dedicated connection between two hosts is the `point-to-point` topology. 

In this topology, a direct and straightforward physical link exists only between `two hosts.`

![[Pasted image 20240922195445.png]]

#### Bus
***
All hosts are connected via a [[202409221947 Transmission Medium|transmission medium]] in bus topology. Every host has access to the transmission medium and the signals that are transmitted over it.

There is no central network component that controls the processes on [[202409221947 Transmission Medium|transmission medium]] that can be, for example, a `coaxial cable.`

Since the medium is shared with all the others, `only one host can send`, and `all the others can only receive` and evaluate data and see whether it is intended for itself.

![[Pasted image 20240922200012.png]]

#### Star
***
The star topology is a network component that maintains a connection to all hosts. 

Each host is connected to a `central network component` via a separate link. This is usually a router, a hub or a switch. These handle the `forwarding function` for the data packets.

The data traffic on the central network component can be very high since all data and connections go through it

![[Pasted image 20240922200459.png]]

#### Ring
***
The `physical` ring topology is such that each host or node is connected to the ring with two cables:

- One for `incoming` signals
- One for `outgoing` signals

Ring topology typically does not require an active network component. Here’s why:

**Direct Note-to_Node Connection:** In the ring topology, each node is directly connected to it’s neighbors, so the data is passed from one node to the next without the need for centralized control on routing

**Data Handing by Each Node:** Every node in the ring has the capability to regenerate, amplify or forward the data as it travels around the ring. This allows the data to circulate efficiently without the need for an external device to control the traffic

**Single Communication Path:** The communication in a ring network follows the predefined path, either clockwise or counterclockwise, which means there’s no need for complex routing decisions, that would require an active device like router or switch.

Typically, the [[202409221947 Transmission Medium|transmission medium]] is accessed sequentially from station to station using a retrieval system for the central station or a **token**. A token is a bit pattern that continually passes through a ring network in the one direction, which works according o the **claim token process.**

![[Pasted image 20241006133659.png]]

#### Mesh
***
Many modes decide about the **connections on a physical level** and **the routing on a logical level**.

Therefore, meshed structures have no fixed topology. This means that the physical connections and logical data flows can change based on the network’s state, usage and the decisions made by the nodes themselves.

In many mesh networks nodes can automatically discover and connect to each other, allowing for self-organizing structure. If a node joins or leaves the network, the  connections can adapt, leading to a constantly evolving topology.

##### Physical vs Logical Topology
- **Physical layout** of a mesh network might not be a strict mesh; it could look more like a star or another shape, depending on how devices are interconnected. The key aspect is that devices can connect to multiple other devices, leading to redundancy and alternative paths for data transmission
- **Logically** a mesh network can behave like a full mesh because any device can communicate with any other device, regardless of the physical layout.

## Each host is connected to every other in a fully meshed structure. (primarily used in WAN or MAN)

![[Pasted image 20241006141441.png]]

#### Tree
***
A Tree topology is hierarchical structure that combines characteristics of both Star and Bus topologies. It consists of a central node (often called the root) connected to one or more nodes, which can in turn have their own nodes.

**Characteristics:**
- **Hierarchical Structure:** Nodes are organized in a parent-child relationship, where each node (except the root) has exactly one parent and potentially multiple children.
- **Single Point of Failure:** If the central node (root) fails, the entire network can become inaccessible.
- **Scalability:** Easier to add new nodes as children of existing nodes, making it relatively scalable

There are both logical tree structures according to [[spanning tree]] and physical once. Modular modern networks, based on structured cabling with a hub hierarchy, also have a tree structure. Tree topologies are also used for [[broadband networks]] and city networks ([[202409191936 Network Types|MAN]])

![[Pasted image 20241006143628.png]]

#### Hybrid
***
Hybrid networks combine two or more topologies so that the resulting network does not present any standard topologies. For example, a tree network can represent a hybrid topology in which star networks are connected via interconnected Bus networks.

However, a tree network that is linked to another tree network is still topologically a tree network.

![[Pasted image 20241006144235.png]]

#### Daisy chain
***
In Daisy Chain topology, multiple hosts are connected by placing a cable from one node to another.

Since this creates a chain of connections, it’s also known as Daisy-Chain configuration in which multiple hardware components are connected in a series. This type of networking is often found in automation technology (CAN).

Daisy Chain is based on the physical arrangement of the nodes, in contrast to token procedures, which are structural but can be made independent on the physical layout. The signal is sent to and from a component via its previous nodes to the computer system.

![[Pasted image 20241006151419.png]]

#### LINKS TO THIS PAGE
***
