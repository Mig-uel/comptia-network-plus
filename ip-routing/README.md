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
