# Switching

## How Switching Works

Switches are a fundamental parts to any network, allowing devices to communicate within a local area network (LAN). Switches operate at the data link layer (Layer 2) of the OSI model and use MAC addresses to forward data to the correct destination.

Before we had switches, we used hubs to connect devices. Hubs broadcast incoming data to all connected devices, which can lead to collisions and network inefficiencies.

Hubs are dumb. They do not read MAC addresses, IP addresses, or any other information in the data packets. They simply repeat the incoming signal to all ports. This means that if two devices send data at the same time, a collision occurs, and both devices must resend their data, leading to delays and reduced network performance.

**CSMA/CD (Carrier Sense Multiple Access with Collision Detection)** is a protocol used in Ethernet networks to manage data transmission and avoid collisions. When a device wants to send data, it first listens to the network to see if it is clear. If the network is busy, the device waits for a random period before trying again. If a collision is detected, both devices stop transmitting and wait for a random backoff time before attempting to resend their data. This is not ideal for modern networks, which is why switches were developed.

Switches, on the other hand, are smart, they create a separate collision domain for each connected device. This means that each device can communicate with the switch without worrying about collisions with other devices.

When a switch receives a data packet, it reads the destination MAC address and forwards the packet only to the port associated with that address. This process is known as switching. Switches maintain a MAC address table that maps MAC addresses to specific ports, allowing them to make intelligent forwarding decisions.

Switches can operate in two modes: **store-and-forward** and **cut-through**. In store-and-forward mode, the switch receives the entire data packet, checks it for errors, and then forwards it to the appropriate port. In cut-through mode, the switch starts forwarding the packet as soon as it reads the destination MAC address, which reduces latency but may allow erroneous packets to be forwarded.

**More in-depth on how switches work compared to hubs:**

A switch maintains what is called a MAC address table (or CAM table). This table maps each MAC address to the specific port on the switch where that device is connected. When a switch receives a data packet, it looks at the destination MAC address and checks its MAC address table to determine which port to forward the packet to. If the destination MAC address is not in the table, the switch will broadcast the packet to all ports except the one it was received on, similar to how a hub operates.

This process is known as **flooding**. Once the destination device responds, the switch learns the MAC address and updates its MAC address table accordingly.

**More in-depth on how switches learn MAC addresses:**

Address learning is a fundamental function of network switches. When a switch receives a data packet, it examines the source MAC address and the port from which the packet arrived. The switch then records this information in its MAC address table, associating the source MAC address with the specific port.

This learning process allows the switch to build a comprehensive map of which devices are connected to which ports. Over time, as more packets are transmitted through the switch, the MAC address table becomes more complete, enabling the switch to make more efficient forwarding decisions.

This learning process is dynamic, meaning that the switch continuously updates its MAC address table as devices connect and disconnect from the network. If a device moves to a different port, the switch will learn the new association the next time it receives a packet from that device.

**Broadcasting** is another important concept in switching. When a switch receives a packet with a destination MAC address of `FF:FF:FF:FF:FF:FF`, it recognizes this as a broadcast address. The switch will then forward the packet to all ports except the one it was received on. This is useful for certain network functions, such as ARP requests, where a device needs to communicate with all other devices on the local network.

---

Switches also support features like VLANs (Virtual Local Area Networks), which allow network administrators to segment a physical network into multiple logical networks. This enhances security and improves network performance by reducing broadcast traffic.

## Virtual LANs (VLANs)

In large networks today, you are going to have many computers connected to pretty big switches. Switches come in various sizes, from small 5-port switches to large enterprise-grade switches with 48 or more ports.

When you have many devices connected to a single switch, all those devices are part of the same broadcast domain. This means that when one device sends a broadcast message, all other devices connected to that switch will receive it. In large networks, this can lead to excessive broadcast traffic, which can degrade network performance.

Let's say we have a 24-port switch and we divide it into three sections of 8 ports each. We can the Sales department to the first 8 ports, the Engineering department to the next 8 ports, and the HR department to the last 8 ports. Even though we separated them physically, they are still part of the same broadcast domain. We do not want them being able to talk to each other. Basically, we want to connect everybody to the switch, but we want to control the communication between different groups.

This is where VLANs come in. A VLAN allows us to create separate logical networks within a single physical switch. We can configure the switch to assign specific ports to different VLANs. In our example, we can create three VLANs: VLAN 10 for Sales, VLAN 20 for Engineering, and VLAN 30 for HR. Each VLAN will act as its own separate broadcast domain.

**Virtual LANs (VLANs)** are used to logically segment a switch into multiple broadcast domains. This allows network administrators to group devices based on function, department, or project team, regardless of their physical location.

When a switch is configured with VLANs, it tags the data packets with a VLAN identifier (VID) as they enter the switch. This tagging allows the switch to determine which VLAN the packet belongs to and ensures that it is only forwarded to ports that are part of that VLAN.

For example, if a device in VLAN 10 sends a broadcast message, the switch will only forward that message to other devices in VLAN 10. Devices in VLAN 20 and VLAN 30 will not receive the broadcast, effectively isolating the traffic between different VLANs.

To enable communication between different VLANs, a router or a Layer 3 switch is required. This process is known as inter-VLAN routing. The router will receive packets from one VLAN, examine the destination IP address, and forward the packet to the appropriate VLAN.

**VLAN Benefits:**

- **Broadcast Control:**
  - Each VLAN is its own broadcast domain, reducing unnecessary traffic.
  - Broadcast is contained within the VLAN, improving overall network performance.
- **Improved Security:**
  - Host can only communicate within their VLAN unless explicitly allowed.
  - Inter-VLAN communication requires routing, allowing for better control and monitoring.
- **Flexibility and Scalability:**
  - Host in the same VLAN can always communicate with each other, even if they are connected on different switches in the same network.
  - VLANs can be easily reconfigured without changing physical connections.
- **Simplified Network Management:**
  - Logical grouping of devices makes it easier to manage and troubleshoot the network.
  - Changes can be made through software configurations rather than physical rewiring.

Going back to bullet point three, VLANs can span multiple switches. Let's say we have two **backbone switches** connected together, and each backbone switch has multiple **access switches (the smaller switches that connect end devices)** connected to it. We can configure the access switches to assign specific ports to VLANs, and then connect the access switches to the backbone switches using **trunk links**. Trunk links carry traffic for multiple VLANs between switches, allowing devices in the same VLAN but connected to different switches to communicate with each other. This setup allows for greater flexibility and scalability in network design, as VLANs can be extended across multiple switches and locations.

Trunk links use a tagging protocol, such as IEEE 802.1Q, to identify which VLAN each data packet belongs to as it travels between switches. This ensures that the VLAN information is preserved across the network.

Overall, VLANs are a powerful tool for network segmentation, providing improved performance, security, and manageability in modern networks.

### VLAN Database

In every switch, there is a special area of memory called the VLAN database. This is where all the VLAN configurations are stored. When you create a new VLAN on a switch, the switch adds an entry to the VLAN database with the VLAN ID and any associated settings. This database is essential for the switch to keep track of which ports belong to which VLANs and how to handle traffic for each VLAN.

The **VLAN database** is where VLAN configurations are stored on a network device, such as a switch.

This database includes information like **VLAN IDs**, and associated properties such as VLAN names and port assignments, enabling the switch to organize and manage network traffic effectively.

When a switch receives a data packet, it consults the VLAN database to determine how to handle the packet based on its VLAN ID. This ensures that packets are forwarded only to the appropriate ports associated with the correct VLAN, maintaining network segmentation and security.

### Port Tagging/802.1Q

**Port tagging**, based on the **IEEE 802.1Q** standard, is a method used of inserting **VLAN identifiers (VLAN IDs)** into Ethernet frames to indicate which VLAN the frame belongs to. This is essential for managing traffic in networks that utilize VLANs, especially when multiple VLANs are carried over a single physical link, known as a **trunk link**.

When a switch receives an Ethernet frame on a port that is configured as a trunk port, it adds a VLAN tag to the frame. This tag includes the VLAN ID, which allows the receiving switch to determine which VLAN the frame belongs to when it arrives. The VLAN tag is inserted into the Ethernet frame between the source MAC address and the EtherType/length fields.

When the frame reaches its destination switch, the switch reads the VLAN tag to identify the appropriate VLAN and forwards the frame to the correct ports associated with that VLAN. If the frame is destined for a device within the same VLAN, it is forwarded accordingly. If it needs to be sent to another VLAN, it will be routed through a Layer 3 device, such as a router or Layer 3 switch.

### Switch Virtual Interfaces (SVIs)

Now that we have our three VLANs set up on our switch, we need a way for devices in different VLANs to communicate with each other. To make them talk to each other, we need to do some type of routing. One way to do this is by using a router. However, when it comes to massive amount of traffic, the best thing to do is to use a Layer 3 switch.

A layer 3 switch is a switch that has routing capabilities built into it. This means that it can perform the functions of both a switch and a router. To enable inter-VLAN routing on a Layer 3 switch, we need to create **Switch Virtual Interfaces (SVIs)** for each VLAN.

A **Switch Virtual Interface (SVI)** is a **virtual interface** on a switch that provides Layer 3 routing capabilities for a specific VLAN.

It allows the switch to route traffic between different VLANs without the need for an external router. An IP address is assigned VLAN interfaces, enabling inter-VLAN routing on layer 2 switches that have layer 3 capabilities.

## Advanced Switch Configurations

### Interface Configuration

**Interface configuration** involves **setting up and managing the individual ports** on a network switch to control how they handle data traffic. Remember, an interface is just another word for a port on a switch. Each port can be configured with specific settings to optimize network performance, enhance security, and ensure proper communication between devices.

For example, you can configure a port to operate in access mode (for end devices) or trunk mode (for connecting to other switches). You can also set speed and duplex settings, enable or disable ports, and apply security features like port security.

More settings like VLAN assignments, link aggregation (bonding multiple ports together for increased bandwidth), physical properties like speed and duplex settings, and security features such as port security can also be configured on switch interfaces.

### Native VLAN

The **Native VLAN** is the default VLAN on a **trunk port** (a port that carries traffic for multiple VLANs) that **carries untagged traffic** (traffic without a VLAN tag). By default, the native VLAN is VLAN 1, but it can be changed to any other VLAN as needed.

When a switch receives an untagged frame on a trunk port, it assigns that frame to the native VLAN. This is important for compatibility with devices that do not support VLAN tagging, as they will send and receive untagged frames.

It's a good practice to change the native VLAN to a different VLAN than the default (VLAN 1) for security reasons, as VLAN 1 is often targeted in network attacks. By using a different native VLAN, you can help protect your network from potential vulnerabilities associated with the default VLAN.

### Voice VLAN

A **Voice VLAN** is a special type of VLAN that is specifically designed to carry voice traffic, such as VoIP (Voice over Internet Protocol) calls. Voice VLANs are used to separate voice traffic from regular data traffic on a network, ensuring that voice communications receive the necessary quality of service (QoS) for clear and uninterrupted conversations.

When a device, such as an IP phone, connects to a switch port configured for a voice VLAN, the switch can prioritize voice traffic over other types of traffic. This is important because voice traffic is sensitive to delays and interruptions, which can lead to poor call quality.

By using a voice VLAN, network administrators can ensure that voice traffic is given higher priority, reducing latency and jitter, and improving the overall quality of voice communications on the network. Additionally, separating voice traffic into its own VLAN can enhance security by isolating it from other types of data traffic.

### Speed

When you are configuring a switch port, you may need to set the **speed** of the ports.
**Speed** refers to the **data transfer rate** of a network connection, typically measured in megabits per second (Mbps) or gigabits per second (Gbps).

Configuring the speed of a switch port ensures compatibility between connected devices and optimizes network performance. Common speed settings for switch ports include 10 Mbps, 100 Mbps, 1 Gbps (1000 Mbps), and 10 Gbps.

When configuring a switch port, you can set the speed to either a specific value (e.g., 100 Mbps) or to "auto" mode, which allows the switch and the connected device to negotiate the best possible speed automatically. It's important to ensure that both the switch port and the connected device support the same speed settings to avoid connectivity issues.

### Duplex

**Duplex** refers to the ability of a network device to send and receive data simultaneously. There are two types of duplex settings: **half-duplex** and **full-duplex**.

**Full-duplex** allows for **simultaneous two-way communication**, meaning that data can be sent and received at the same time without any collisions. This is the preferred mode for most modern network devices, as it maximizes network efficiency and performance.

**Half-duplex**, on the other hand, allows for **one-way communication at a time**. In half-duplex mode, a device can either send or receive data, but not both simultaneously. This can lead to collisions if two devices attempt to communicate at the same time, which can degrade network performance. Half-duplex is typically used in older network technologies, such as traditional Ethernet hubs.

When configuring switch ports, it's important to set the duplex mode correctly to match the capabilities of the connected devices. Mismatched duplex settings (e.g., one device set to full-duplex and the other to half-duplex) can lead to performance issues, such as collisions and reduced throughput. Most modern switches and devices support auto-negotiation, which allows them to automatically determine the best duplex setting for optimal communication.

### Spanning Tree Protocol (STP)

Let's talk about when you take a switch and start connecting multiple switches together and have redundant links between them. This is a common practice in network design to ensure high availability and fault tolerance. However, having multiple switches connected with redundant links can create loops in the network.

These loops can cause broadcast storms, where broadcast packets are continuously circulated in the network, leading to network congestion and degraded performance.

Why you would want to create redundant links? Well, if one link fails, the other link can take over, ensuring that network connectivity is maintained. However, without a mechanism to manage these loops, the network can become unstable.

There is a protocol used to prevent switching loops called the **Spanning Tree Protocol (STP)**. STP helps prevent network loops in a network's Ethernet topology by creating a spanning tree that selectively blocks redundant paths while allowing a single active path between any two network devices.

STP works by electing a root bridge (the central switch in the network) and then determining the shortest path from the root bridge to all other switches in the network. It then blocks any redundant paths that could create loops, ensuring that there is only one active path between any two devices.

If a network link fails, STP recalculates the spanning tree and unblocks the necessary paths to restore connectivity. This process helps maintain network stability and prevents broadcast storms caused by switching loops.

### Link Aggregation

**Link/Port Aggregation** is a technique used to combine multiple physical network links into a single logical link. This provides increased bandwidth and redundancy between network devices, such as switches, servers, or routers. It involves combining multiple network ports to function as a single connection, increasing the bandwidth and providing redundancy for higher data throughput and reliability.

It allows for the consolidation of multiple links between switches or between a switch and a server into a single logical link. This logical link can provide higher bandwidth than a single physical link and can also offer redundancy in case one of the physical links fails.

Link aggregation can be configured using protocols such as **LACP (Link Aggregation Control Protocol)**, which is part of the IEEE 802.3ad standard. LACP allows devices to automatically negotiate and manage the aggregation of links, ensuring that the aggregated link operates efficiently and effectively.

By using link aggregation, network administrators can improve network performance, increase fault tolerance, and optimize resource utilization in their networks.

### Port Security

**Port Security** is a feature available on network switches that allows administrators to control access to individual switch ports based on MAC addresses. This helps enhance network security by restricting which devices can connect to specific ports on the switch.

Port security allows us to control which devices can be connected to a switch port based on their MAC addresses. By configuring port security, we can specify a list of allowed MAC addresses for each port. If a device with a MAC address that is not on the allowed list attempts to connect to the port, the switch can take various actions, such as shutting down the port, sending an alert, or simply dropping the unauthorized traffic.

This feature is particularly useful in environments where physical access to network ports is possible, such as in offices or public spaces. By limiting access to known devices, port security helps prevent unauthorized access to the network and mitigates the risk of attacks such as MAC flooding or unauthorized device connections.

Port security can be configured with different modes, such as:

- **Static MAC Addressing:** Manually specifying allowed MAC addresses for a port.
- **Dynamic MAC Addressing:** Allowing the switch to learn and store MAC addresses dynamically, up to a specified limit.
- **Sticky MAC Addressing:** Allowing the switch to learn MAC addresses dynamically and then save them to the running configuration, making them persistent across reboots.

By implementing port security, network administrators can enhance the overall security posture of their networks and protect against unauthorized access.

### Port Mirroring/Spanning

**Port Mirroring**, also known as **SPAN (Switched Port Analyzer)**, is a feature on network switches that allows the copying of network traffic from one or more source ports to a designated destination port. This is commonly used for network monitoring and analysis.

When port mirroring is configured, the switch duplicates the traffic from the specified source ports and sends it to the destination port, where a network analyzer or monitoring device can capture and analyze the data. This is useful for troubleshooting network issues, monitoring performance, and detecting security threats.

Allows you to redistribute traffic from one port to another for monitoring purposes. For example, you can configure a switch to mirror all traffic from a specific port (source port) to another port (destination port) where a network analyzer or intrusion detection system is connected. This allows you to monitor and analyze the traffic without interrupting the normal flow of data on the network.

- SPAN (Switch Port Analyzer)/RSPAN (Remote SPAN) are protocols used for port mirroring.
- This feature is commonly used to monitor network traffic for troubleshooting, performance analysis, and security monitoring.
- Commonly used to monitor network traffic with a packet sniffer or an intrusion detection system (IDS).

By using port mirroring, network administrators can gain valuable insights into network behavior and performance, helping them to maintain a secure and efficient network environment.

### Maximum Transmission Unit (MTU)

The **Maximum Transmission Unit (MTU)** is the largest size of a data packet that can be transmitted over a network medium. It is typically measured in bytes. The MTU size can vary depending on the type of network technology being used.

MTU sizes are variable, dependent on the physical medium and network protocol, with a common default of 1500 bytes for Ethernet networks. Configuring the MTU size appropriately is important for optimizing network performance and avoiding fragmentation of packets.

When a data packet exceeds the MTU size of the network, it may need to be fragmented into smaller packets for transmission. Fragmentation can lead to increased overhead and reduced performance, so it is generally desirable to set the MTU size to accommodate the largest expected packet size without fragmentation.

Network administrators may need to adjust the MTU size on network devices, such as switches and routers, to optimize performance for specific applications or network conditions. For example, certain applications, such as video streaming or large file transfers, may benefit from a larger MTU size to reduce overhead and improve throughput.

By understanding and configuring the MTU size appropriately, network administrators can help ensure efficient data transmission and optimal network performance.

### Jumbo Frames

**Jumbo Frames** are Ethernet frames that exceed the standard maximum transmission unit (MTU) size of 1500 bytes. Jumbo frames can typically carry up to 9000 bytes of payload, although the exact size can vary depending on the network equipment and configuration.

Using jumbo frames can improve network performance by reducing the overhead associated with processing a large number of smaller frames. When larger frames are used, fewer frames need to be processed, which can lead to lower CPU utilization on network devices and improved throughput.

However, all devices on the network path must support jumbo frames for them to be used effectively. If a device that does not support jumbo frames is encountered, it may lead to fragmentation or dropped packets.

When configuring jumbo frames, it is important to ensure that the MTU settings on all network devices, including switches, routers, and end devices, are consistent. Mismatched MTU settings can lead to connectivity issues and degraded performance.

By utilizing jumbo frames in a network environment where supported, administrators can achieve better performance for applications that require high bandwidth, such as video streaming, large file transfers, and data backups.
