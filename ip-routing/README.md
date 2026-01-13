# IP Routing

## Routing Process

Routing is the process of **selecting paths** in a network along which to send network traffic.

Routing is performed by devices known as routers, which use **routing tables** and algorithms to determine the most efficient path for data packets to travel from the source to the destination.

Keep in mind that this is within its own network not between different networks.

Your default gateway is the IP address of the router that your device uses to access other networks, including the internet.

When a device wants to communicate with another device on a different network, it sends the data packets to its default gateway. The router then examines the destination IP address and consults its routing table to determine the best path for the packets to reach their destination.

More in-depth, when a host want to reach another host, it first checks if the destination IP address is within its own subnet by comparing the destination IP address with its own IP address and subnet mask. If the destination is within the same subnet, the host can communicate directly with the destination host using ARP (Address Resolution Protocol) to resolve the MAC address. If the destination is outside the subnet, the host sends the packets to its default gateway (router). However, the packet coming from the host will have the MAC address of the default gateway as the destination MAC address, not the MAC address of the final destination host. The router will then forward the packet to the next hop based on its routing table until it reaches the destination network. When the packet arrives at the destination network, the router on that network will use ARP to resolve the MAC address of the final destination host and deliver the packet accordingly. The source MAC address in the packet will be the MAC address of the last router that forwarded the packet, not the original host's MAC address. And like mentioned, ARP is used to map IP addresses to MAC addresses within a local network segment.
