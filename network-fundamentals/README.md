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
