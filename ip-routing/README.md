# IP Routing

## Routing Process

Routing is the process of **selecting paths** in a network along which to send network traffic.

Routing is performed by devices known as routers, which use **routing tables** and algorithms to determine the most efficient path for data packets to travel from the source to the destination.

Keep in mind that this is within its own network not between different networks.

Your default gateway is the IP address of the router that your device uses to access other networks, including the internet.

When a device wants to communicate with another device on a different network, it sends the data packets to its default gateway. The router then examines the destination IP address and consults its routing table to determine the best path for the packets to reach their destination.

More in-depth, when a host want to reach another host, it first checks if the destination IP address is within its own subnet by comparing the destination IP address with its own IP address and subnet mask. If the destination is within the same subnet, the host can communicate directly with the destination host using ARP (Address Resolution Protocol) to resolve the MAC address. If the destination is outside the subnet, the host sends the packets to its default gateway (router). However, the packet coming from the host will have the MAC address of the default gateway as the destination MAC address, not the MAC address of the final destination host. The router will then forward the packet to the next hop based on its routing table until it reaches the destination network. When the packet arrives at the destination network, the router on that network will use ARP to resolve the MAC address of the final destination host and deliver the packet accordingly. The source MAC address in the packet will be the MAC address of the last router that forwarded the packet, not the original host's MAC address. And like mentioned, ARP is used to map IP addresses to MAC addresses within a local network segment.

## Static Routing

When it comes to routing, the question you have to ask yourself is how do routers know where and what path to send packets to?

Static routing is a method of routing where network routes are manually configured and maintained by a network administrator. In static routing, the routes are fixed and do not change unless manually updated.

Static routing is typically used in smaller networks or in situations where the network topology is relatively simple and does not change frequently. It provides a straightforward and predictable way to manage network traffic, as the routes are explicitly defined by the administrator. However, static routing can become cumbersome and difficult to manage in larger networks with complex topologies, as any changes to the network require manual updates to the routing tables on each router.

---

**Static routing** involved manually configuring routers with specific paths to reach certain networks. This is done by adding static routes to the router's routing table.

It is simple to implement in small networks but **lacks the flexibility and scalability** of dynamic routing protocols, as it does not automatically adapt to changes in the network topology.

## Dynamic Routing

Dynamic routing is a method of routing where routers automatically discover and maintain routes to different networks using routing protocols. In dynamic routing, routers exchange information about network topology and adjust their routing tables based on changes in the network.

In other words, **Dynamic routing** automatically adjusts the paths used to send data through the network.

Routers communicate with each other using **dynamic routing protocols**, sharing information about network topology and traffic conditions. This allows routers to adapt to changes, such as link failures or congestion, ensuring data packets are always sent via the most efficient path.

Dynamic routing protocols come in different types, including: Interior Gateway Protocols (IGPs) or Exterior Gateway Protocols (EGPs).

Interior Gateway Protocols (IGPs) are used for routing within a single autonomous system (AS), such as a corporate network or an ISP's network. Examples of IGPs include OSPF (Open Shortest Path First), EIGRP (Enhanced Interior Gateway Routing Protocol), and RIP (Routing Information Protocol).

### Routing Protocols Categories

**Interior Gateway Protocols (IGPs)** are used by organizations to router their LAN in one location to their LAN in another location.

Example: NY branch router to LA branch router.

**Exterior Gateway Protocols (EGPs)** are used to route between different organizations, such as between different ISPs.

Example: The internet, every organization has a connection to many other organizations.

Border Gateway Protocol (BGP) is the only and main EGP used on the internet.

Every organization has an Autonomous System which is comprised of all the networks that the organization owns. Each AS is assigned a unique AS number (ASN) for identification.

### Interior Gateway Protocols (IGPs)

When it comes to IGPs, there are two main categories:

1. **Distance Vector Protocols**: These protocols determine the best path to a destination based on distance metrics, such as hop count. Each router shares its routing table with its immediate neighbors, and routers update their tables based on the information received.

2. **Link State Protocols**: These protocols maintain a complete map of the network topology. Each router shares information about the state of its links with all other routers in the network, allowing each router to independently calculate the best path to each destination using algorithms like Dijkstra's.

| Protocol Type   | Metric    | Max Hops  | Routing Protocols |
| --------------- | --------- | --------- | ----------------- |
| Distance Vector | Hop Count | 15 hops   | RIP, IGRP         |
| Link State      | Bandwidth | Unlimited | OSPF, IS-IS       |

## Routing Protocols

### Routing Information Protocol (RIP)

**Routing Information Protocol (RIP)** is one of the oldest distance-vector routing protocols. It uses hop count as its primary metric for determining the best path to a destination network. RIP has a maximum hop count limit of 15, meaning that any destination beyond 15 hops is considered unreachable.

**Versions**:

- **RIP v1**: Classful routing protocol that does not support subnetting or variable-length subnet masks (VLSM).
- **RIP v2**: Classless routing protocol that supports subnetting and VLSM, allowing for more efficient use of IP address space. Multicast updates (224.0.0.9) are used for routing information exchange. Simple authentication is also supported.

**Use Cases**:

- Suitable for small to medium-sized networks with simple topologies.
- Limited scalability and slower convergence (the time it takes for routers to update their routing tables after a change in the network) time compared to modern like OSPF or EIGRP.

### Open Shortest Path First (OSPF)

**Open Shortest Path First (OSPF)** is a widely used link-state routing protocol that operates within an autonomous system (AS). OSPF uses the Dijkstra algorithm to calculate the shortest path to each destination network based on various metrics, primarily bandwidth.

**Key Features**:

- **Hierarchical Design**: OSPF supports a hierarchical network design using areas, which helps reduce routing overhead and improves scalability.
- Updates are sent only when there is a change in the network topology, leading to faster convergence times compared to distance-vector protocols.
- Supports Variable Length Subnet Masking (VLSM) and Classless Inter-Domain Routing (CIDR).

**Advantages**:

- Efficient, scalable, and flexible.
- Provides load balancing and fault tolerance through multiple equal-cost paths.
- Suitable for large and complex networks.

### Enhanced Interior Gateway Routing Protocol (EIGRP)

**Enhanced Interior Gateway Routing Protocol (EIGRP)** is an advanced distance-vector routing protocol developed by Cisco Systems. It combines the features of both distance-vector and link-state protocols, making it a hybrid routing protocol.

**Key Features**:

- Supports VLSM and CIDR.
- Sends partial updates only when there are changes in the network, reducing bandwidth usage.
- Uses metrics like bandwidth, delay, load, and reliability to determine the best path to a destination.
- Rapid convergence and loop-free routing through the use of the Diffusing Update Algorithm (DUAL).

**Advantages**:

- Highly efficient, scalable, and quick converging.
- Provides loop-free routing and supports unequal-cost load balancing.
- Suitable for medium to large-sized networks, especially those using Cisco equipment.

### Metric

The metric is a value used by routing protocols to determine the best path to a destination network. Different routing protocols use different metrics based on various factors, such as hop count, bandwidth, delay, load, and reliability.

**Lower metric values typically indicate more desirable paths.**

| Routing Protocol | Metric Used                                            |
| ---------------- | ------------------------------------------------------ |
| RIP              | Hop Count                                              |
| OSPF             | Cost (based on bandwidth)                              |
| EIGRP            | Composite metric (bandwidth, delay, load, reliability) |

### Border Gateway Protocol (BGP)

**Border Gateway Protocol (BGP)** is the primary exterior gateway protocol (EGP) used to route traffic between different autonomous systems (AS) on the internet. It is essential for inter-domain routing on the global internet and uses path attributes to determine the best path for data packets.

**Key Features**:

- Supports CIDR for efficient IP address allocation.
- Employs policies for route selection and advertisement, allowing network administrators to control routing behavior.
- Uses TCP as its transport protocol, ensuring reliable communication between BGP peers.

**Advantages**:

- Highly scalable and flexible, making it suitable for the vast and complex nature of the internet.
- Manages large routing tables and complex routing policies effectively.
- Crucial for ISPs and large organizations that connect to multiple networks.

## Route Selection (OB 2.1)

**Route selection** is a critical process in network routing that **determines the best path** for data packets to travel from the source to the destination. Routers use various criteria and metrics to evaluate and select the most efficient route among multiple available paths.

It uses specific criteria such as administrative distance, prefix length (specificity), and metric values to make informed decisions about which route to prioritize.

### Administrative Distance (AD)

**Administrative Distance (AD)** is a metric used by routers to **rank the trustworthiness** of different routing protocols. It is a value assigned to each routing protocol, indicating its reliability and preference when multiple routes to the same destination are available.

**Lower values indicate higher trustworthiness**, helping routers decide which routes to use when multiple paths to the same destination exist from different routing protocols.

| Routing Protocol                                   | Default Administrative Distance |
| -------------------------------------------------- | ------------------------------- |
| Directly connected interface                       | 0                               |
| Static route                                       | 1                               |
| Enhanced Interior Gateway Routing Protocol (EIGRP) | 5                               |
| External Border Gateway Protocol (eBGP)            | 20                              |
| Open Shortest Path First (OSPF)                    | 110                             |
| Routing Information Protocol (RIP)                 | 120                             |
| Unknown/Untrusted                                  | 255                             |

### Prefix Length (Specificity)

The **prefix length**, also known as **specificity**, specifies the **number of contiguous bits** of the network portion of an IP address in a subnet mask. It is represented in CIDR notation as a slash (/) followed by the number of bits.

This notation is an integral part of CIDR (Classless Inter-Domain Routing) and helps in defining network boundaries and available hosts within those networks, enabling both routing efficiency and IP address allocation.

When multiple routes to the same destination exist, routers prioritize the route with the **longest prefix length** (most specific match). This means that a route with a longer subnet mask (more bits in the network portion) is preferred over a route with a shorter subnet mask.

For example, consider the following two routes to the same destination network:
Route 1: 192.168.1.0/24
Route 2: 192.168.1.0/25

In this case, Route 2 (/25) is more specific than Route 1 (/24) because it has a longer prefix length. Therefore, the router will choose Route 2 for routing traffic to the destination network

### VRRP/FHRP

When dealing with multiple routers, protocols like **VRRP (Virtual Router Redundancy Protocol)** and **FHRP (First Hop Redundancy Protocol)** are used to ensure high availability and redundancy for the default gateway.

**First Hop Redundancy Protocols (FHRP)** are used to achieve high availability with multiple physical redundant routers by creating a virtual router that acts as the default gateway for hosts on a LAN.

- **HSRP (Hot Standby Router Protocol)**: A Cisco proprietary protocol that allows multiple routers to work together to present the appearance of a single virtual router to the hosts on the LAN. One router is elected as the active router, while others remain in standby mode, ready to take over if the active router fails.
- **VRRP (Virtual Router Redundancy Protocol)**: An open standard protocol similar to HSRP that allows multiple routers to form a virtual router. One router is elected as the master, while others are backups, ready to take over if the master fails.

### Virtual IP (VIP)

A **Virtual IP (VIP)** address is an IP address that is **not tied to a specific physical network interface** on a device. Instead, it is shared among multiple devices, such as routers or servers, to provide redundancy and load balancing.

It is used to **provide redundancy and load balancing for services hosted on multiple servers or devices**, allowing servers to share the same IP address while distributing incoming traffic among them.

VIPs are **commonly used in network load balancers and failover configurations** to ensure continuous availability and scalability of critical applications and services.

When a client sends a request to the VIP, the load balancer or failover mechanism directs the traffic to one of the available servers or devices associated with that VIP, based on predefined rules or algorithms.

### Subinterface

A **subinterface** in networking is a virtual interface created by **dividing** a single physical interface into multiple logical interfaces. Each subinterface can be assigned its own IP address, VLAN (Virtual Local Area Network) ID, and other configuration parameters.

This is commonly used in scenarios where multiple VLANs exist on a **single router or switch port** to manage traffic segregation and support various services or protocols over a single physical link.

Subinterfaces are often used in **router-on-a-stick** configurations, where a single physical interface on a router is connected to a switch port that carries traffic for multiple VLANs. Each subinterface is configured to handle traffic for a specific VLAN, allowing the router to route traffic between different VLANs while using only one physical interface.

## Network Address Translation (NAT) (OB 2.1)

**Network Address Translation (NAT)** translates on IP address to another IP address.
It is commonly used to allow multiple devices on a private network to share a single public IP address when accessing the internet.

NAT works by modifying the source or destination IP addresses in the IP packet headers as they pass through a router or firewall. This allows devices on a private network to communicate with external networks while hiding their internal IP addresses.

**Advantages**:

- Conserves public IP addresses by allowing multiple devices to share a single public IP.
- Eliminates address overlap events with other LANs.
- Makes it easier to connect to the internet from a private network.
- Eliminates address renumbering if your network changes.

**Disadvantages**:

- Translation delays the forwarding of packets as in some cases the router has to keep track of many translations.
- Causes loss of end-to-end IP traceability since the original IP addresses are hidden.
- Certain application will not function properly with NAT, especially those that embed IP address information within the payload of the packet.

### Types of NAT

1. **Static NAT (One-to-One)**: Maps a single private IP address to a single public IP address. This is useful for hosting services that need to be accessible from the internet.

- Only required if an internal device needs to be accessed from the outside.

2. **Dynamic NAT (Many-to-Many)**: Maps a private IP address to a public IP address from a pool of available public IP addresses. The mapping is temporary and changes over time.

- Not commonly used since it can limit internet access if the pool of public IPs is exhausted.

3. **Port Address Translation (PAT) (Many-to-One)**: Also known as NAT overload, PAT maps multiple private IP addresses to a single public IP address by using different port numbers. This is the most common form of NAT used in home and small business networks.

- Allows multiple devices to share a single public IP address by differentiating them using port numbers.
