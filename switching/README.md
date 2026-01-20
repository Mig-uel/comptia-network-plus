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
