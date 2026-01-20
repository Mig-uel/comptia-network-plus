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

