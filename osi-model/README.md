# OSI Model

## What is a Protocol?

In the world of computer networking or IT in general, you are going to encounter one word that you are going to hear repeatedly, and that word is **protocol**.

By definition, without thinking about IT, a protocol is simply a set of rules that govern how things are done. It is a standard set of rules that you are going to follow to achieve a specific goal.

According to Cloudflare, a protocol is defined as:

> "In networking, a protocol is a set of rules for formatting and processing data. Network protocols are like a common language for computers. The computers within a network may use vastly different software and hardware; however, the use of protocols enables them to communicate with each other regardless of their differences."

In IT, protocols are used to define how data is transmitted and received over a network. They ensure that devices can communicate effectively, regardless of their underlying architecture or design.

Some common examples of protocols include:

- **HTTP (Hypertext Transfer Protocol)**: Used for transmitting web pages over the internet.
- **HTTPs (Hypertext Transfer Protocol Secure)**: A secure version of HTTP that encrypts data for secure communication.
- **SMTP (Simple Mail Transfer Protocol)**: Used for sending emails.
- **FTP (File Transfer Protocol)**: Used for transferring files between computers on a network.
- **TCP/IP (Transmission Control Protocol/Internet Protocol)**: A suite of protocols that form the foundation of the internet and most modern networks.
- **UDP (User Datagram Protocol)**: A connectionless protocol used for applications that require fast, efficient transmission, such as video streaming or online gaming.

In order for computers to communicate effectively, they need to follow the same protocols. This ensures that data is transmitted and received correctly, and that devices can understand each other regardless of their differences.

In the world of networking, we do not use just one protocol; instead, we utilize multiple protocols to transmit data effectively.

For example, in order to get a web page from Google, you need to use HTTP or HTTPS to request the web page. However, that protocol just allows the web page to be transmitted. How does a web page know where to go? How does that protocol know where to find you? There has to be a protocol that handles addressing and routing.

If I want to send you a mail, I need to use SMTP to send the mail, but how does that mail know where to go? I have to know your address, don't I? Similarly, for Google to send you a web page, it needs to know your IP address.

This is going to get complex very quickly because in order to transmit data effectively, we need multiple protocols to work together. This will eventually lead us to a layered approach to networking, which is where the OSI model comes in.

In summary, a protocol is just a language that computers use to communicate with each other. Different protocols are used for different purposes, and multiple protocols are often used together to transmit data effectively over a network.

## Introduction to a Layered Approach to Networking

In order to set up a network, you're not just going to be using one piece of gear, you are going to be using multiple pieces of gear. These pieces of gear are layered in order to create a functional network.

For example, if you want to set up a network, you are going to have the cabling, switches, routers, firewalls, etc. However, physical gear is not enough to set up a network. You also have the software side of things, which includes protocols, applications, and services which every piece of gear is going to use in order to communicate with each other.

To manage the complexity of networking, we use a layered approach. This means that we break down the networking process into smaller, more manageable layers, each with its own specific function. Each layer is responsible for a specific aspect of networking, and they work together to ensure that data is transmitted effectively.

The most common model used to describe this layered approach is the OSI (Open Systems Interconnection) model.

The OSI model is a layered approach to how computers connect.

It consists of seven layers, each with its own specific function:

1. **Layer 1 - Physical Layer**: This layer is responsible for the physical transmission of data over a network. It includes the cabling, connectors, and other physical components that make up the network.
2. **Layer 2 - Data Link Layer**: This layer is responsible for the reliable transmission of data over a physical link. It includes protocols such as Ethernet and Wi-Fi, which are used to transmit data over a local area network (LAN). We can think of this layer as the switch layer.
3. **Layer 3 - Network Layer**: This layer is responsible for routing data between different networks. It includes protocols such as IP (Internet Protocol), which is used to route data over the internet. We can think of this layer as the router layer.
4. **Layer 4 - Transport Layer**: This layer is responsible for ensuring that data is transmitted reliably and efficiently. It includes protocols such as TCP (Transmission Control Protocol) and UDP (User Datagram Protocol), which are used to manage the flow of data between devices. We can think of this layer as the firewall layer.

The rest of the layers (Layers 5-7) are more focused on the software side of things:

5. **Layer 5 - Session Layer**: This layer is responsible for establishing, managing, and terminating sessions between applications. It ensures that data is properly synchronized and organized during communication.
6. **Layer 6 - Presentation Layer**: This layer is responsible for translating data between different formats. It ensures that data is presented in a way that is understandable to the receiving application, including data encryption and compression.
7. **Layer 7 - Application Layer**: This layer is responsible for providing services to end-users. It includes protocols such as HTTP, FTP, and SMTP, which are used to access web pages, transfer files, and send emails.

The point of all this is that we are going to be using a layered approach. In particular, we are going to be using the OSI model to help us understand how data is transmitted over a network. It is a seven-layer model that breaks down the networking process into smaller, more manageable layers, each with its own specific function.

## What is the OSI Model? (OB 1.1)

In today's world, we enjoy interoperability. What is interoperability? It is where different systems can talk to each other regardless of their underlying architecture or design. Windows can talk to Mac, Mac can talk to Unix, Unix can talk to Linux, and so on.

However, if you go back to the 1970s and 1980s, this was not the case. Different vendors had their own proprietary systems that could not talk to each other. This created a lot of problems for businesses and organizations that needed to connect different systems together.
There was no common language aka protocol for these systems to communicate with each other.

How did we get here? The International Organization for Standardization (ISO) created a model called the OSI model to help solve this problem.

### OSI Model Layers

The OSI model is called an internetworking model, which are used to organize and describe network functions. Each layers describes a different set of unique functions that work together to enable communication between devices on a network.

OSI stands for Open Systems Interconnection, which means that the model is designed to be open and flexible, allowing different systems to communicate with each other regardless of their underlying architecture or design.

Any system that follows the OSI model can communicate with any other system that also follows the OSI model. This is because the OSI model provides a common framework for communication, which allows different systems to understand each other.

The **Open System Interconnection (OSI) model** is made up of **seven layers** containing various types of hardware and software components that work together to enable communication between devices on a network.

- Created to achieve interoperability of diverse vendor devices and software systems
- Partitions communication systems into abstraction layers
- **Protocols** are the standard terms that computers use to understand each other
- Each layer serves the layer above it and is served by the layer below it

### Mnemonics

To remember the OSI model layers, you can use the following mnemonics:

**From Top to Bottom (Layer 7 to Layer 1):**

- **A**ll **P**eople **S**eem **T**o **N**eed **D**ata **P**rocessing

**From Bottom to Top (Layer 1 to Layer 7):**

- **P**lease **D**o **N**ot **T**hrow **S**ausage **P**izza **A**way

Remember, the OSI model is as follows:

1. **Physical Layer** (Layer 1)
2. **Data Link Layer** (Layer 2)
3. **Network Layer** (Layer 3)
4. **Transport Layer** (Layer 4)
5. **Session Layer** (Layer 5)
6. **Presentation Layer** (Layer 6)
7. **Application Layer** (Layer 7)

Remember, layer 1 is at the bottom, and layer 7 is at the top!

## Introduction to the Layers (OB 1.1)

When it comes to the OSI model, keep in mind that every machine in the network is going to be running this model.

Here's a brief overview of what each layer does:

| Layer | Name               | Function                                                                                                                                                               |
| ----- | ------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 7     | Application Layer  | Generates data to be sent over the network, processes data that is received from the network, and provides services to applications. Examples include HTTP, FTP, SMTP. |
| 6     | Presentation Layer | Gets the data ready for the application layer by converting, translating, encoding, compressing, and encrypting data.                                                  |
| 5     | Session Layer      | Manages sessions between applications, including establishing, maintaining, and terminating connections.                                                               |
| 4     | Transport Layer    | Handles end-to-end communication either via connection-oriented (TCP) or connectionless (UDP) protocols, ensuring data is delivered reliably and in order.             |
| 3     | Network Layer      | Responsible for logical addressing and routing of data packets across networks using protocols like IP.                                                                |
| 2     | Data Link Layer    | Manages physical addressing (MAC addresses), error detection, and access to the physical medium. Examples include Ethernet and Wi-Fi.                                  |
| 1     | Physical Layer     | Deals with the physical connection between devices, including cables, switches, and other hardware components that transmit raw bitstreams over a physical medium.     |

Here's another brief overview of the OSI model layers and their functions:

- **Layer 1 - Physical Layer**: This layers is predominantly about converting bits into electrical, radio, or optical signals. It is concerned with the physical connection between devices, including cables, switches, and other hardware components that transmit raw bitstreams over a physical medium.
- **Layer 2 - Data Link Layer**: This layer provides communication between devices on the same network. It is responsible for managing physical addressing (MAC addresses), error detection, and access to the physical medium. Examples of protocols used in this layer include Ethernet and Wi-Fi.
- **Layer 3 - Network Layer**: This layer is responsible for logical addressing and routing of data packets across networks. It uses protocols like IP (Internet Protocol) to determine the best path for data to travel from the source to the destination.
- **Layer 4 - Transport Layer**: This layer handles end-to-end communication between devices. It can use connection-oriented protocols like TCP (Transmission Control Protocol) or connectionless protocols like UDP (User Datagram Protocol) to ensure that data is delivered reliably and in order.
- **Layer 5 - Session Layer**: This layer setup the initial connection between the machines. It manages sessions between applications, including establishing, maintaining, and terminating connections.
- **Layer 6 - Presentation Layer**: This layer is responsible for formatting data for the application layer. It converts, translates, encodes, compresses, and encrypts data to ensure that it is in a format that the application layer can understand.
- **Layer 7 - Application Layer**: This layer is where applications interact with the network. It generates data to be sent over the network, processes data that is received from the network, and provides services to applications. Examples of protocols used in this layer include HTTP, FTP, and SMTP.

## Encapsulation (OB 1.1)

Encapsulation is the process of wrapping data with the necessary protocol information before transmission over a network. As data moves down the OSI model layers, each layer adds its own header (and sometimes a trailer) to the data, creating a new data unit at each layer.

Here's a brief overview of how encapsulation works in the OSI model:

1. **Application Layer (Layer 7)**: The data is generated by an application and is referred to as "data."
2. **Presentation Layer (Layer 6)**: The data is formatted and may be encrypted or compressed. It is still referred to as "data."
3. **Session Layer (Layer 5)**: The session layer manages the connection and adds session information. The data is still referred to as "data."
4. **Transport Layer (Layer 4)**: The transport layer adds a transport header (e.g., TCP or UDP header) to the data, creating a "segment" (for TCP) or "datagram" (for UDP).
5. **Network Layer (Layer 3)**: The network layer adds a network header (e.g., IP header) to the segment/datagram, creating a "packet."
6. **Data Link Layer (Layer 2)**: The data link layer adds a data link header (e.g., Ethernet header) and a trailer (e.g., Frame Check Sequence) to the packet, creating a "frame."
7. **Physical Layer (Layer 1)**: The physical layer converts the frame into bits and transmits them over the physical medium.

As the data moves back up the OSI model layers at the receiving end, each layer removes its respective header/trailer, a process known as decapsulation, until the original data is delivered to the application.

Here's a simple diagram to illustrate encapsulation in the OSI model:

```
Application Data
        ↓
Presentation Data
        ↓
Session Data
        ↓
Transport Segment/Datagram
        ↓
Network Packet
        ↓
Data Link Frame
        ↓
Physical Bits
```

When data is at each layer, it is referred to by different names:

- **Layer 7 (Application Layer)**: Data Stream
- **Layer 6 (Presentation Layer)**: Data Stream
- **Layer 5 (Session Layer)**: Data Stream
- **Layer 4 (Transport Layer)**: Segment (TCP) / Datagram (UDP)
- **Layer 3 (Network Layer)**: Packet
- **Layer 2 (Data Link Layer)**: Frame
- **Layer 1 (Physical Layer)**: Bits

A mnemonic to remember the data unit names at each layer is:

- **D**on't **S**top **P**ouring **F**ree **B**eer

Where:

- D = Data (Layers 5, 6, 7)
- S = Segment/Datagram (Layer 4)
- P = Packet (Layer 3)
- F = Frame (Layer 2)
- B = Bits (Layer 1)

This encapsulation process is crucial for ensuring that data is transmitted accurately and efficiently across networks, allowing different systems to communicate effectively.

In summary, when you are sending data over a network, it goes through the OSI model layers, from layer 7 down to layer 1, with each layer adding its own header/trailer to the data. This process is called encapsulation. When the data reaches its destination, it goes back up the layers from layer 1 to layer 7, with each layer removing its respective header/trailer in a process called decapsulation.

Each layer encapsulates the data from the layer above it by adding its own header (and sometimes a trailer) to the data. This process is essential for ensuring that data is transmitted accurately and efficiently across networks. Different protocols operate at different layers of the OSI model, and understanding how encapsulation works is crucial for network professionals to troubleshoot and manage networks effectively.

## Application Layer (OB 1.1)

The **Application Layer** is the seventh layer of the OSI model and is the closest layer to the end user.

Layer 7 is the **Application Layer**. This is the entry door to network services at a lower level.

- Apps use this layer to get services when they TX (transmit) or RX (receive) data over a network
- Applications sit on top of this layer and use it to communicate with other applications over a network
- Responsible for interfacing user applications, network management services, remote access, etc.
- This is the playground for hackers because this is where users interact with the network
- Examples of protocols used in this layer include:
  - Simple Mail Transfer Protocol (SMTP)
    - Port 25
  - Simple Network Management Protocol (SNMP)
    - Port 161
  - Hypertext Transfer Protocol (HTTP)
    - Port 80
  - Hypertext Transfer Protocol Secure (HTTPS)
    - Port 443
  - Line Printer Daemon (LPD)
    - Port 515
  - File Transfer Protocol (FTP)
    - Ports 20 and 21
  - Telnet
    - Port 23
  - Trivial File Transfer Protocol (TFTP)
    - Port 69
  - Electronic Data Interchange (EDI)
  - Post Office Protocol Version 3 (POP3)
    - Port 110
  - Internet Message Access Protocol (IMAP)
    - Port 143
  - Network News Transfer Protocol (NNTP)
    - Port 119
  - Secure Remote Procedure Call (SRPC)
    - Port 135
  - Secure Electronic Transaction (SET)

Keep in mind that the Application Layer is not the application itself; rather, it provides services to the application. The application uses the services provided by the Application Layer to communicate over the network. And the application protocols mentioned above operate at this layer to facilitate communication between applications over a network.

## Presentation Layer (OB 1.1)

When data is transferred across the network, it needs to be in a format that the receiving application can understand. This is where the **Presentation Layer** comes in.

As the data works its way down from the Application Layer (Layer 7) to the Presentation Layer (Layer 6), the Presentation Layer is responsible for translating the data into a format that the receiving application can understand.

- Concerned about the format of the data being transmitted
- Apps must use a common data format to communicate effectively
- The main functions of this layer include:
  - Data conversion: Converts data from one format to another (e.g., EBCDIC to ASCII)
  - Character Code Translation: Translates character codes between different systems (e.g., Unicode to ASCII)
  - Data Compression: Reduces the size of data to optimize transmission (e.g., ZIP compression)
  - Data Encryption and Decryption: Secures data by converting it into an unreadable format and back (e.g., SSL/TLS encryption)
- This layer is generally where data encryption occurs to ensure secure communication over the network
- Examples of encoding formats used in this layer include:
  - ASCII (American Standard Code for Information Interchange)
  - EBCDIC (Extended Binary Coded Decimal Interchange Code)
  - TIFF (Tagged Image File Format)
  - JPEG (Joint Photographic Experts Group)
  - Motion Picture Experts Group (MPEG)
  - MIDI (Musical Instrument Digital Interface)

So far, we have received data from the Application Layer through protocols such as HTTP or FTP. The Presentation Layer takes this data and ensures that it is in a format that the receiving application can understand. This may involve converting character codes, compressing data, or encrypting data for secure transmission. Once the data is properly formatted, it is passed down to the Session Layer (Layer 5) for further processing.

## Session Layer (OB 1.1)

When computers are communicating with each other, one of the things we have to do is to ensure that they know when they should be talking, are they still talking, and when they should stop talking. This is where the **Session Layer** comes in.

Layer 5 is the **Session Layer**. This layer is responsible for establishing, managing, and terminating sessions between applications.

- Provides logical persistent connection between peer hosts
- Manages conversation between applications exchanging data
- Creates, monitors, tears down sessions
- Full-duplex (data flows both ways simultaneously), half-duplex (data flows both ways, but not at the same time), or simplex (data flows in only one direction) communication
- Examples of communication modes:
  - Full-duplex: Both devices can send and receive data simultaneously (e.g., a phone call, switches)
  - Half-duplex: Devices can send and receive data, but not at the same time (e.g., walkie-talkies)
  - Simplex: Data flows in only one direction (e.g., television broadcast, keyboard to computer)
- Synchronization: Inserts checkpoints into data streams to allow for recovery in case of failure
- This layer has protocols that deal with session establishment, maintenance, and termination
- Examples of protocols used in this layer include:
  - NFS (Network File System)
  - SQL (Structured Query Language)
  - NetBIOS (Network Basic Input/Output System)
  - SAP (Session Announcement Protocol)
  - PPTP (Point-to-Point Tunneling Protocol)
  - RPC (Remote Procedure Call)

So far, the Application Layer (Layer 7) has generated data to be sent over the network, and the Presentation Layer (Layer 6) has formatted the data for transmission. The Session Layer (Layer 5) now takes over to establish a session between the communicating applications. It manages the conversation, ensuring that both applications are synchronized and can communicate effectively. Once the session is established, the data is passed down to the Transport Layer (Layer 4) for further processing.

## Transport Layer (OB 1.1)

Before we talk about the Transport Layer, keep in mind that layers 5-7 are all done in software. Layers 1-3 are responsible for movement of data across the network.

The **Transport Layer** is the fourth layer of the OSI model and is responsible for ensuring that data is transmitted reliably and efficiently between devices on a network.

The Transport Layer (Layer 4) has a lot do with check-in. When the data arrives at the host, the Transport Layer is going to check to make sure that all the data arrived and that it is in the correct order.

- One of the busier layers of the OSI model
- Creates an end-to-end transport between peer hosts
- UDP and TCP protocols operate at this layer
  - UDP (User Datagram Protocol): Connectionless protocol that provides fast, but unreliable delivery of data. Used for applications that require speed over reliability, such as video streaming or online gaming. (Simplex communication)
  - TCP (Transmission Control Protocol): Connection-oriented protocol that provides reliable delivery of data. Used for applications that require accuracy over speed, such as web browsing or email. (Full-duplex communication)
- Additional protocols that operate at this layer include:
  - SPX (Sequenced Packet Exchange)
  - SSL (Secure Sockets Layer)
  - TLS (Transport Layer Security)
- Port numbers are also assigned at this layer to identify specific applications or services on a device
  - Well-known ports (0-1023): Reserved for common services and applications (e.g., HTTP uses port 80, HTTPS uses port 443)
  - Registered ports (1024-49151): Assigned to specific applications or services by the IANA (Internet Assigned Numbers Authority)
  - Dynamic or private ports (49152-65535): Used for temporary connections and are not assigned to any specific application or service
- Responsible for segmentation, flow control, error control, and connection management
  - Segmentation: Breaks down large data streams into smaller segments for transmission
  - Flow Control: Manages the rate of data transmission to prevent congestion and ensure efficient use of network resources
  - Error Control: Detects and corrects errors that may occur during transmission
  - Connection Management: Establishes, maintains, and terminates connections between devices

So far, the Application Layer (Layer 7) has generated data to be sent over the network, the Presentation Layer (Layer 6) has formatted the data for transmission, and the Session Layer (Layer 5) has established a session between the communicating applications. The Transport Layer (Layer 4) now takes over to ensure that the data is transmitted reliably and efficiently. It breaks down large data streams into smaller segments, manages the flow of data, detects and corrects errors, and establishes connections between devices. Once the data is properly prepared, it is passed down to the Network Layer (Layer 3) for further processing.

## Network Layer (OB 1.1)

The **Network Layer** is the third layer of the OSI model and is responsible for routing data packets between different networks.

This layer is where routers operate at. The Network Layer is responsible for determining the best path for data to travel from the source to the destination.

The main protocol that operates at this layer is the Internet Protocol (IP).

- Moves data between two hosts that are not physically connected
- Uses logical addressing (IP addresses) to identify devices on a network
- Internet Protocol (IP) is the primary protocol used at this layer
- IP does not guarantee delivery of packets; it is a best-effort delivery system
- Finds the best path for data to travel from source to destination using routing protocols
- Uses routing tables to deliver packets to the correct destination
- Devices that operate at this layer include routers and layer 3 switches
- Additional network routing protocols that operate at this layer include:
  - Connectionless protocols:
    - ICMP (Internet Control Message Protocol)
    - RIP (Routing Information Protocol)
    - OSPF (Open Shortest Path First)
    - BGP (Border Gateway Protocol)
    - IGMP (Internet Group Management Protocol)
  - Supports multicast:
    - IPX (Internetwork Packet Exchange)
    - IPSec (Internet Protocol Security)
    - NAT (Network Address Translation)
    - SKIP (Simple Key Management for Internet Protocols)

So far, the Application Layer (Layer 7) has generated data to be sent over the network, the Presentation Layer (Layer 6) has formatted the data for transmission, the Session Layer (Layer 5) has established a session between the communicating applications, and the Transport Layer (Layer 4) has ensured that the data is transmitted reliably and efficiently. The Network Layer (Layer 3) now takes over to route the data packets between different networks. It uses logical addressing (IP addresses) to identify devices on a network and determines the best path for data to travel from the source to the destination. Once the data packets are properly routed, they are passed down to the Data Link Layer (Layer 2) for further processing.

## Data Link Layer (OB 1.1)

The **Data Link Layer** is the second layer of the OSI model and is responsible for providing reliable communication between devices on the same network.

One of the main functions of the Data Link Layer is to manage physical addressing using MAC (Media Access Control) addresses. Each device on a network has a unique MAC address that is used to identify it on the network.

- Gets packets from the Network Layer and encapsulates them into frames for transmission over the physical medium (assuming the data is going down the layers)
- Transmits frames between devices on the same network
- Detects and corrects errors that may occur during transmission
- Converts information into bits for transmission over the Physical Layer (assuming the data is going down the layers)
- Uses MAC/Hardware addresses to identify and communicate with devices on the same network
- Moves data to the next physically connected device
- Devices that operate at this layer include switches and bridges
- Divided into two sublayers:
  - Logical Link Control (LLC) Sublayer: Responsible for managing communication between devices on the same network and providing error detection and flow control.
  - Media Access Control (MAC) Sublayer: Responsible for managing access to the physical medium and providing physical addressing using MAC addresses.
- Examples of protocols used in this layer include:
  - Ethernet
  - Wi-Fi (IEEE 802.11)
  - ARP (Address Resolution Protocol): resolves IP addresses to MAC addresses
  - RARP (Reverse Address Resolution Protocol): resolves MAC addresses to IP addresses
  - PPP (Point-to-Point Protocol)
  - SLIP (Serial Line Internet Protocol)
  - L2F (Layer 2 Forwarding)
  - L2TP (Layer 2 Tunneling Protocol)
  - PPTP (Point-to-Point Tunneling Protocol)
  - Token Ring
  - FDDI (Fiber Distributed Data Interface)
  - ATM (Asynchronous Transfer Mode)
  - CDDI (Copper Distributed Data Interface)

**Media Access Control Sublayer (MAC)**

The MAC sublayer is a sublayer of the OSI model's Data Link Layer (Layer 2) that is responsible for managing access to the physical medium and providing physical addressing using MAC addresses.
It is responsible for the addressing and channel access control mechanisms that enable several nodes to communicate within a network, typically using a MAC address.

**Logical Link Control Sublayer (LLC)**

The LLC sublayer is the upper sublayer of the OSI model's Data Link Layer (Layer 2) that is responsible for managing communication between devices on the same network and providing error detection and flow control.

So far, the Application Layer (Layer 7) has generated data to be sent over the network, the Presentation Layer (Layer 6) has formatted the data for transmission, the Session Layer (Layer 5) has established a session between the communicating applications, the Transport Layer (Layer 4) has ensured that the data is transmitted reliably and efficiently, and the Network Layer (Layer 3) has routed the data packets between different networks. The Data Link Layer (Layer 2) now takes over to provide reliable communication between devices on the same network. It manages physical addressing using MAC addresses, encapsulates packets into frames for transmission, detects and corrects errors, and converts information into bits for transmission over the Physical Layer (Layer 1). Once the data frames are properly prepared, they are passed down to the Physical Layer (Layer 1) for further processing.

## Physical Layer (OB 1.1)

At the Data Link Layer (Layer 2), data is encapsulated into frames for transmission over the physical medium. The frames were converted into bits for transmission over the Physical Layer (Layer 1).

We are going to take the bits and convert them into electrical, radio, or optical signals that can be transmitted over the physical medium.

The **Physical Layer** is the first layer of the OSI model and is responsible for the physical transmission of data over a network.

- Receives bits from the Data Link Layer and converts them into electrical, radio, or optical signals for transmission over the physical medium (assuming the data is going down the layers)
  - Photons or beam of light for fiber optic cables
- Devices that operate at this layer include hubs, repeaters, network interface cards (NICs), and cables
- Defines the physical characteristics of the network, including:
  - Cables (e.g., twisted pair, coaxial, fiber optic)
  - Connectors (e.g., RJ45, LC, SC)
  - Signaling methods (e.g., voltage levels, modulation techniques)
  - Data rates (e.g., 10 Mbps, 100 Mbps, 1 Gbps)
  - Physical topology (e.g., star, bus, ring)
- Responsible for transmitting raw bitstreams over a physical medium

So far, the Application Layer (Layer 7) has generated data to be sent over the network, the Presentation Layer (Layer 6) has formatted the data for transmission, the Session Layer (Layer 5) has established a session between the communicating applications, the Transport Layer (Layer 4) has ensured that the data is transmitted reliably and efficiently, the Network Layer (Layer 3) has routed the data packets between different networks, and the Data Link Layer (Layer 2) has provided reliable communication between devices on the same network. The Physical Layer (Layer 1) now takes over to physically transmit the data over the network. It converts bits into electrical, radio, or optical signals and transmits them over the physical medium using cables and connectors. Once the data is transmitted, it can be received by another device on the network, where it will go back up through the OSI model layers for processing.
