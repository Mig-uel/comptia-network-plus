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
