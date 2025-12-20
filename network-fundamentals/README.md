# Network Fundamentals

## What is a Network?

A computer network is a system of interconnected computers and other devices that can communicate and share resources and information with each other.

Networks can be categorized by their size and structure.

The main purpose of all networks is to share resources and information efficiently (e.g., data, devices, applications, etc.).

A basic network consists of just two machines connected together, sharing files and resources. However, most networks are much larger and more complex.

A switch (we will cover switches in more detail later) is often used to connect multiple devices within a local area network (LAN). It allows data to be sent and received between devices on the same network.

Why do we setup networks? We setup networks so that devices can communicate with each other and share resources such as files, printers, and internet connections.

## Devices on a Network

When we are setting up a network, we will have to know all the different devices that are on the network.

### What is on a Network?

- **Host**: Hosts are devices or systems on a network that use, provide, or share resources and services, such as computers, servers, and network-enabled devices. Generally, any device with an IP address can be considered a host (e.g., computers, smartphones, tablets, printers, etc.).
- **Server**: A server is a computer or system that provides resources, data, services, or programs to other computers, known as clients, over a network. Servers can host websites, manage emails, store files, and run applications (This is a type of host).
- **Workstation**: A workstation is a high-performance computer designed for technical or scientific applications. It is typically used by professionals for tasks that require more power than a standard personal computer (This is a type of host).
- **Client**: A client is a computer or device that accesses services, applications, or resources provided by a server over a network. Clients can be desktops, laptops, smartphones, or tablets (This is a type of host).
- **Network Devices**: Network devices are hardware components that facilitate communication and connectivity within a network. They allow servers, workstations, and clients to connect and interact with each other. Such devices are switches, routers, Access Points (APs), and firewalls. (These are also types of hosts).

## Types of Networks (OB 1.6)

The types of networks that exist are limited to the geographical area they cover.

- **Local Area Network (LAN)**: A LAN is a network that connects devices within a limited geographical area, such as a home, office, or building. It covers a small geographical area like a home, office, or building. LANs are typically used for sharing resources like files, printers, and internet connections among connected devices.
- **Wide Area Network (WAN)**: A WAN is a network that spans a large geographical area, often a country or continent. The internet is the largest example of a WAN. WANs are used to connect multiple LANs together, allowing communication and resource sharing over long distances.
- **Metropolitan Area Network (MAN)**: A MAN is a network that covers a larger geographical area than a LAN but smaller than a WAN, typically spanning a city or metropolitan area. MANs are often used by organizations to connect multiple LANs within a city for resource sharing and communication.
- **Campus Area Network (CAN)**: A CAN is a network that connects multiple LANs within a limited geographical area, such as a university campus or business complex. CANs are used to facilitate communication and resource sharing among different buildings or departments within the campus.
- **Storage Area Network (SAN)**: A SAN is a specialized network designed to provide high-speed access to consolidated storage devices. SANs are primarily used to enhance storage devices, such as disk arrays, tape libraries, and optical jukeboxes, making them accessible to servers so that the devices appear as locally attached to the operating system.
- **Personal Area Network (PAN)**: A PAN is a network that connects devices within a very small area, typically within a person's immediate vicinity. Examples of PANs include Bluetooth connections between a smartphone and wireless headphones or a smartwatch.

## Peer-to-Peer vs Client-Server Networks (OB 1.6)

- **Peer-to-Peer (P2P) Network**: A P2P network is a decentralized network architecture where each device (peer) in the network can act as both a client and a server, allowing direct sharing of resources, data, and services among all connected devices without the need for a central server. P2P networks are often used for file sharing and collaborative applications.
- **Client-Server Network**: A client-server network is a network architecture where multiple client devices (computers, smartphones, etc.) connect to a central server that provides resources, services, and data to the clients. The server manages and controls access to resources, while clients request and consume those resources. Client-server networks are commonly used in business environments for applications like email, databases, and web services.

## Backbone vs Segments (OB 1.6)

When an organization sets up a network, they are going to have to decide how to structure the network. All networks are pretty much going to have what's called a backbone and a segment.

A **backbone** connected all the different segments of the network withing the organization together.

A **switch** (we will cover switches in more detail later) allows for **VLANs** (Virtual Local Area Networks) to be created on a network segment. A VLAN allows devices on different physical segments to communicate as if they were on the same physical segment. VLANs allow you to control traffic, improve security, and reduce congestion on a network.

What exactly is the **backbone** and the **segments** of a network? Generally, the backbone is the main connection point of the network. It can be a high-speed switch or router that connects all the different **segments** of the network together. Connected to the backbone are the various servers, internet devices, and all the **segments** switches.
The **segments** of the network are the smaller sections that connect to the backbone. Each segment can be a different department, floor, or building within an organization. Each segment typically has its own switch that connects all the devices within that segment together.

Here is a simple diagram to illustrate the backbone and segments of a network:

```
          [ Backbone Switch/Router ]
                    /      |      \
                   /       |       \
          [ Segment 1 ] [ Segment 2 ] [ Segment 3 ]
           (Switch)       (Switch)      (Switch)
          /   |   \     /   |   \     /   |   \
       PC1  PC2  PC3  PC4  PC5  PC6  PC7  PC8  PC9
```

In this diagram, the backbone switch/router connects all the segments together. Each segment has its own switch that connects the devices within that segment. This structure allows for efficient communication and resource sharing within the organization.

### Backbone and Segments

- **Backbone**: A **network backbone** is the main infrastructure that interconnects various segments of a computer network, providing a central pathway for data exchange. It is typically composed of high-capacity, high-speed links and core routers or switches, which handle the bulk of network traffic and ensure efficient data transmission across the network.

```
          [ Backbone Switch/Router ] -> Internet Router
                    /      |      \
                   /       |       \
           (Sales)       (Engineering)      (Servers)
          /   |   \     /   |   \     /   |   \
          { These are the segments of the network }
```

- **Network Segment**: **Network segments** are smaller sub-networks or clusters of devices that connect to the backbone. Each segment can include a variety of networked devices such as computers, servers, switches, and other networking equipment. Segments often represent different departments or areas within an organization, and they rely on rhe backbone to communicate with other segments and access shared resources.

```
          [ Backbone Switch/Router ]
                    /      |      \
                   /       |       \
          [ Segment 1 ] [ Segment 2 ] [ Segment 3 ]
           (Switch)       (Switch)      (Switch)
          /   |   \     /   |   \     /   |   \
       PC1  PC2  PC3  PC4  PC5  PC6  PC7  PC8  PC9
```

In summary, the backbone serves as the central hub for data transmission, while network segments are the smaller, localized areas that connect to the backbone, allowing for organized and efficient communication within the overall network structure.

## Topologies (OB 1.6)

A **network topology** is basically the layout or structure of the network.

In more detail, a **network topology** describes the layout or arrangement of elements (links, nodes, routers, switches, etc.) of a computer network.

There are several different types of network topologies, each with unique configurations and characteristics, influencing the network's performance, reliability, and scalability. In simpler terms, each topology has its own advantages and disadvantages.

### Common Network Topologies

- **Point-to-Point Topology**: A **point-to-point topology** is the simplest type of network topology, where two devices are directly connected to each other. This topology involves a **direct connection** between two networking devices, typically using a single cable or wireless link. It is mainly used for dedicated connections, such as those between a main office and a branch office, or between two pieces of networking equipment.
  - For example, a **site-to-site WAN** connection between two offices or a **host-to-host PAN** connection. A simpler example would be a direct connection between two computers using an Ethernet cable or a wireless link.

```
[ Device A ] <-----> [ Device B ]
```

- **Mesh Topology**: A **mesh topology** is a network configuration where each device is interconnected with multiple other devices, creating a web-like structure. This topology is a network setup where each host is connected to every other host in the network, creating a network with **no central connecting point**. This topology ensures **high availability and redundancy**, as multiple paths exist for data to travel between devices. If any on link fails, data can be rerouted through multiple alternative paths.
  - **Advantages**: High fault tolerance, redundancy, and reliability due to multiple connections between devices.
  - **Disadvantages**: Complex setup and maintenance, higher costs due to the increased number of connections required.
  - For example, the internet is a large-scale mesh network where multiple routers and servers are interconnected to ensure data can be transmitted even if some connections fail.

```
       [ Device A ]
       /    |     \
   [ Device B ]--[ Device C ]
       \    |     /
       [ Device D ]
```

- **Star or Hub-and-Spoke Topology**: A **star or hub-and-spoke topology** is a network configuration where all devices are connected to a central hub or switch. In this topology, **all nodes are connected to a central node such as hubs/switches/wireless access points**. This setup simplifies network management and troubleshooting, as all data passes through the central hub. However, it **creates a single point of failure**; if the central hub fails, the entire network becomes inoperable.
  - **Advantages**: Easy to manage and troubleshoot, scalable, and allows for easy addition or removal of devices.
  - **Disadvantages**: Single point of failure at the central hub, potential bottleneck if the hub is overloaded.
  - For example, most home and office networks use a star topology where all devices connect to a central router or switch.

```
            [ Central Hub ]
           /      |      \
      [ Device A ][ Device B ][ Device C ]
```

- **Hybrid Topology**: A **hybrid topology** is a network configuration that combines two or more different types of topologies to leverage the advantages of each. This topology combines **two or more different topologies** to form a resultant topology that leverages the advantages and mitigates the disadvantages of the individual topologies used. Hybrid topologies offer flexibility in network design and can be tailored to meet specific organizational needs or constraints.
  - **Advantages**: Flexibility, scalability, and the ability to optimize network performance by combining different topologies.
  - **Disadvantages**: Complexity in design and management, potential for increased costs due to the combination of different topologies.
  - For example, a large organization might use a star topology within individual departments and connect those departments using a mesh topology for inter-departmental communication.

```
        [ Central Hub ]
       /      |      \
  [ Dept A ] [ Dept B ] [ Dept C ]
     / | \      |        / | \
[ D1][D2][D3] [ D4 ] [ D5][D6][D7 ]
```

## Three-Tier Model (OB 1.6)

The **three-tier hierarchy network model** is a widely adopted structured approach to network design that organizes network architecture into three distinct layers or tiers.

**Each layer is designed to serve a specific purpose**, optimizing scalability, performance, and manageability of the network.

A quick diagram of the three-tier model looks like this:

```
        [ Core Layer ]                      [Core Layer ]
              |                                  |
        [ Distribution Layer ]         [ Distribution Layer ]
              /  \                                /   \
             /    \                              /     \
[ Access Layer ]  [Access Layer ]   [ Access Layer ]     [ Access Layer ]
        |                |                  |                   |
   [ End Devices ]  [End Devices]     [End Devices]        [ End Devices ]
```

### The Three Tiers

There are three layers or tiers in the three-tier hierarchy network model: the Core Layer, the Distribution Layer, and the Access Layer.

- **Core Layer**: The **core layer** is the topmost layer of the three-tier hierarchy network model. It serves as the backbone of the network, providing high-speed and reliable connectivity between different distribution layers. The core layer is responsible for fast and efficient data transport across the network, ensuring minimal latency and high availability. It typically consists of high-capacity routers and switches that can handle large volumes of traffic.
- **Distribution Layer**: The **distribution layer** is the middle layer of the three-tier hierarchy network model. It acts as an intermediary between the core layer and the access layer, aggregating data from multiple access layer devices and forwarding it to the core layer. The distribution layer is responsible for implementing policies, routing, and filtering traffic between different segments of the network. It often includes routers and multilayer switches that provide advanced features such as Quality of Service (QoS) and security.
- **Access Layer**: The **access layer** is the bottommost layer of the three-tier hierarchy network model. It is the layer where end devices, such as computers, printers, and other network-enabled devices, connect to the network. The access layer provides connectivity to these end devices and manages their access to network resources. It typically consists of switches and wireless access points that facilitate communication between end devices and the rest of the network.

### Core Layer

The **core layer** is the backbone of the network, handling high-speed packet switching across the entire network. It is **responsible for fast and reliable data routing** and sho;d have high redundancy and fault tolerance to prevent network downtime.

Imagine the core layer as the highway system of a city, where major roads connect different parts of the city efficiently.

In more technical imagination, imagine the core layer as a high-speed switch or router that connects multiple distribution layers together, ensuring that data can travel quickly and reliably across the network.

Coming from a programming background, you can think of the core layer as the main application server that handles all the requests and responses between different modules of an application, ensuring smooth and efficient communication.

### Distribution Layer

The **distribution layer** acts as the intermediary between the core layer and the access layer, managing routing, filtering, and WAN access. It **aggregates data** received from the access layer before it is transmitted to the core layer for routing to the final destination.

Think of the distribution layer as the main roads that connect neighborhoods to the highway system in a city.

In more technical imagination, imagine the distribution layer as a switch or router that connects multiple access layers together, managing traffic and ensuring that data is properly routed to the core layer.

Coming from a programming background, you can think of the distribution layer as the controller in an MVC (Model-View-Controller) architecture, managing the flow of data between the model (core layer) and the view (access layer).

### Access Layer

The **access layer** is the network's point of entry for devices and end users, connecting them to the network. This layer includes switches and access points that **provide connectivity** to desktops, laptops, and other network-enabled devices.

Think of the access layer as the local streets in a neighborhood that connect homes and businesses to the main roads.

In more technical imagination, imagine the access layer as a switch or access point that connects end devices to the network, allowing them to communicate with other devices and access network resources.

Coming from a programming background, you can think of the access layer as the user interface of an application, where users interact with the system and access its features.

## Spine-and-Leaf Architecture and Collapsed Core Architecture (OB 1.6)

As you start designing networks, one architectural design you could use is the **spine-and-leaf architecture**.

### Spine-and-Leaf Architecture

The **spine-and-leaf architecture** is a network topology commonly used in data centers and large-scale enterprise networks. It is a **two-tier or two-layer** network topology that is highly scalable and **minimizes latency** by ensuring that every leaf (access layer) switch is separated by no more than two switches from any other leaf switch.

In this topology, leaf switches form the access layer where devices are connected, while spine switches serve as the core or backbone of the network, interconnecting all leaf switches without any direct connections between them.

In simpler terms, spine switches connect to all leaf switches, but leaf switches do not connect to each other directly. For example, consider an enterprise CISCO switch for the spine layer and multiple smaller switches for the leaf layer. All leaf switches connect to spine switches, but leaf switches do not connect to each other at all.

```
        [ Spine Switch 1 ]   [ Spine Switch 2 ]
               |                    |
       -------------------------------
       |        |        |        |
 [ Leaf Switch 1 ][ Leaf Switch 2 ][ Leaf Switch 3 ]
       |                |                |
   [ End Devices ]  [ End Devices ]  [ End Devices ]
```

The reason why this design is fast and low latency is that its only two layers, and any device on the network is only two hops away from any other device.

A **hop** is a term used to describe the journey of a data packet from one network device (like a router or switch) to another as it travels across a network. Each time a packet passes through a device, it is considered one hop. The number of hops can affect the latency and speed of data transmission, with fewer hops generally resulting in faster communication.
For example, if a data packet travels from your computer to a web server and passes through three routers along the way, that would be considered three hops.

### Collapsed Core Architecture

Another architectural design you could use is the **collapsed core architecture**.

The **collapsed core architecture** is a network design that combines the core and distribution layers into a single layer, effectively "collapsing" the traditional three-tier model into a two-tier model.

Collapse core architecture merges the **core** and **distribution** layers into a single layer, simplifying the network design and reducing hardware costs.

This approach is ideal for **small to medium-sized networks** where managing several layers may not be necessary.

The architecture facilitates easier management and maintenance, while enhancing performance by reducing latency between the network's core and distribution functions.

---

The only time you are going to be dealing with a 3-tier model is when you are working with large enterprise networks. Most small to medium-sized networks are going to be using either a spine-and-leaf architecture or a collapsed core architecture.

## North South vs East West Traffic (OB 1.6)

When discussing designing networks, you have to understand how data flows through the network. There are two main types of data flow: **North-South traffic** and **East-West traffic**.

In its simplest form, **North-South traffic** refers to network traffic that literally flows up and down the data center and outside the data center. If the traffic is going from a user to a server or from a server to the internet, that is considered North-South traffic.

On the other hand, **East-West traffic** refers to network traffic that flows laterally within the data center. If the traffic is going from one server to another server within the same data center, that is considered East-West traffic.

### North-South Traffic

**North-South traffic** describes the flow of network traffic between the **data center** and the **outside world** (e.g., users, clients, external networks), focusing on inbound and outbound traffic patterns.

It typically involves client-to-server communications, where clients access services hosted within the data center.

For example, when a user accesses a web application hosted in a data center, the request travels from the user's device (outside the data center) to the web server (inside the data center), and the response travels back to the user's device. This flow of traffic is considered North-South traffic.

### East-West Traffic

**East-West traffic** describes the flow of network traffic **within the data center itself**, focusing on lateral communications between servers, applications, and services hosted within the same environment.

This includes server-to-server, server-to-storage, and VM-to-VM communications, highlighting the importance of efficient internal networking to support high volumes of internal data exchange.

For example, when a web server communicates with a database server within the same data center to retrieve information for a user request, this interaction generates East-West traffic. The data exchanged between these servers remains within the data center, making it an example of East-West traffic.

## Traffic Flow (OB 1.6)

On a network, traffic can flow in certain directions. For example, traffic can flow from one-to-one (device to device), one-to-many (device to multiple devices), and many-to-many (multiple devices to multiple devices). The technical terms for these types of traffic flows are unicast, multicast, and broadcast.

### Unicast

The most common type of traffic flow on a network is **unicast**. **Unicast** is a one-to-one form of communication where data is **sent from one source to one specific destination** identified by a unique IP address.

It is the most common form of **IP communication**, used for most internet traffic, such as web browsing, email, and file transfers.

Unicast communication ensures that data packets are delivered to a single, specific recipient over a network.

For example, when you send an email to a specific person, the email is sent using unicast communication, where the email server sends the message directly to the recipient's email server using their unique IP address.

```
[ Sender ] ----unicast----> [ Receiver ]
```

### Multicast

**Multicast** is a method of communication where data is sent **from one or more sources to multiple destinations simultaneously** over a network, using a specific multicast group address.

Multicast is efficient for applications like streaming video or audio, **where the same data needs to be delivered to multiple recipients**, reducing the bandwidth consumption compared to sending individual unicast messages to each recipient.

This approach is used in both IPv4 and IPv6 networks to optimize the delivery of packets to multiple destinations.

For example, when a live video stream is broadcasted to multiple viewers, multicast communication is used to send the video data to all viewers who have joined the multicast group.

```
          [ Sender ]
              |
       -----------------
       |       |       |
   [ Receiver1 ][ Receiver2 ][ Receiver3 ]
```

### Anycast

Anycast is a network addressing and routing method where data is sent to the **nearest or best destination as determined by the routing protocol**, from among multiple potential destinations that share the same IP address.

It is used in IPv6 (and to a lesser extent in IPv4) to provide fast and efficient delivery of services by directing users to the closest server, **commonly used in DNS and CDN (Content Delivery Network) services**.

Anycast can improve network performance and availability by **automatically routing traffic to the nearest or most optimal server** based on network conditions.

For example, when a user requests a website that is hosted on multiple servers around the world, anycast routing directs the user's request to the nearest server, reducing latency and improving load times.

```
          [ Anycast Address ]
              /      |      \
       [ Server1 ] [ Server2 ] [ Server3 ]
              \      |      /
           [ User Request ]
```

### Broadcast

**Broadcast** is a method of communication where a message is sent from **one sender to all potential receivers** within a specific network segment.

In IPv4 networks, the broadcast address is used to **send data to all devices on a local network** simultaneously, such as when a device requests an IP address via DHCP.

Broadcast is not supported in IPv6 networks, instead, IPv6 uses multicast to achieve similar functionality.

For example, when a device sends an ARP request to find the MAC address of another device on the same local network, it uses broadcast communication to send the request to all devices on that network segment.

```
          [ Sender ]
              |
       -----------------
       |       |       |
   [ Receiver1 ][ Receiver2 ][ Receiver3 ]
```
