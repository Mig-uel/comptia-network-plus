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