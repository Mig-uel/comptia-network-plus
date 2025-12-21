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
