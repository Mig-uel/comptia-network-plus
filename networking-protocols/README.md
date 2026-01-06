# Networking Protocols

## FTP and SFTP (OB 1.4)

> Review: What exactly is a protocol? A protocol is a set of rules that govern how data is transmitted and received over a network. It ensures that devices can communicate effectively by establishing standards for data formatting, transmission speed, error handling, and more.
>
> Different functions or different things that we want to send over a network may require different protocols. For example, FTP (File Transfer Protocol) is specifically designed for transferring files between computers, while SFTP (Secure File Transfer Protocol) adds a layer of security by encrypting the data during transfer.

### FTP (File Transfer Protocol)

**File Transfer Protocol (FTP)** is a standard network protocol used to **transfer files between a client and a server** over a TCP/IP network.

FTP uses two ports:

- **Port 21**: Control connection for sending commands.
- **Port 20**: Data connection for transferring files.

It allows users to upload, download, delete, and manage files on a remote server. However, FTP does not encrypt data, making it vulnerable to interception.

### SFTP (Secure File Transfer Protocol)

**Secure File Transfer Protocol (SFTP)** is a secure version of FTP that uses **SSH (Secure Shell)** to encrypt the data being transferred.

It utilizes SSH's **Port 22** for both control and data connections, providing a secure channel for file transfers. SFTP ensures that all data and commands are encrypted and secure from eavesdropping and tampering.

SFTP offers advanced features like file access, file transfer, and file management over any reliable data stream (not just TCP/IP).

---

Remember, FTP is suitable for non-sensitive file transfers, while SFTP is the preferred choice for secure file transfers due to its encryption capabilities.

## Telnet and SSH (OB 1.4)

When you want to configure devices such as a switch or a router, or particular things like Unix servers, these devices are best configured using a command-line interface (CLI).

You basically have to connect to them and type in commands to configure them.

You have two options for connecting to these devices either serially (directly using a console cable) or over the network using protocols like **Telnet** or **SSH**.

### Telnet

**Telnet** is an older network protocol used on the Internet or local area networks to provide a bidirectional (two-way) interactive text-oriented communication facility using a **virtual terminal connection** (VTY) (a software emulation of a physical terminal).

It operates on **Port 23** and is **known for being insecure** because it transmits data, including login credentials, in plain text without encryption. This makes it vulnerable to interception and eavesdropping.

Telnet is great. It allows you to remotely access and manage devices without being in the actual console of the device. However, due to its **lack of security**, it is generally not recommended for use over untrusted networks.

### SSH

Instead of using Telnet, a more secure option is **SSH (Secure Shell)**.

**Secure Shell (SSH)** is a **cryptographic** network protocol that provides a secure way to access a remote computer over an unsecured network.

Port 22 is used for SSH connections.

SSH provides a secure channel over an unsecured network in **client-server architecture**, allowing users to log into another computer over a network, execute commands, and transfer files securely (via SFTP or SCP), and port forwarding (tunneling).

**SSH encrypts all traffic**, including login credentials, to effectively eliminate eavesdropping, connection hijacking, and network-level attacks.

---

In summary, while Telnet allows for remote device management, SSH is the preferred choice due to its robust security features.

## DNS (OB 1.4)

When you want to visit a website, you usually type in a domain name like `www.example.com` into your web browser. However, computers and servers communicate using IP addresses, which are numerical labels assigned to each device connected to a network.

We as humans find it easier to remember domain names than IP addresses. This is where the **Domain Name System (DNS)** comes into play.

**Domain Name System (DNS)** is a hierarchical and decentralized naming system for computers, services, or other resources connected to the Internet or a private network.

It **associates various information with domain names** assigned to each of the participating entities and **uses port 53 queries**, which are typically transmitted over UDP (User Datagram Protocol) or TCP (Transmission Control Protocol).

When you enter a domain name into your web browser, the DNS translates that domain name into its corresponding IP address through a process called **DNS resolution**. This allows your browser to locate and connect to the web server hosting the website.

DNS operates through a distributed database system, with multiple DNS servers around the world that work together to resolve domain names. The main types of DNS servers include:

- **Recursive Resolvers**: These servers receive DNS queries from clients and perform the necessary lookups to resolve the domain name.
- **Root Name Servers**: These servers are at the top of the DNS hierarchy and direct queries to the appropriate top-level domain (TLD) name servers.
- **TLD Name Servers**: These servers manage the top-level domains (like .com, .org, .net) and direct queries to the authoritative name servers.
- **Authoritative Name Servers**: These servers hold the actual DNS records for domain names and provide the final answer to DNS queries.

Overall, DNS is a crucial component of the Internet infrastructure, enabling users to access websites and services using human-friendly domain names instead of complex IP addresses.

---

Remember, DNS is like the phone book of the Internet, translating domain names into IP addresses so that computers can communicate effectively.

## DHCP (OB 1.4)

When a device connects to a network, it needs an IP address to communicate with other devices. Manually assigning IP addresses can be time-consuming and prone to errors, especially in large networks. This is where **Dynamic Host Configuration Protocol (DHCP)** comes in.

**Dynamic Host Configuration Protocol (DHCP)** is a network management protocol used on IP networks to automatically assign IP addresses and other network configuration parameters to devices (clients) on the network.

DHCP operates on **Port 67** for the server and **Port 68** for the client, using UDP (User Datagram Protocol) for communication. It is automatic and centralized management of IP addresses.

It allows devices to join a network and obtain valid IP addresses, subnet masks, default gateways, and DNS server information **without manual configuration**.

When a device connects to a network, it sends a DHCPDISCOVER message to locate a DHCP server. The DHCP server responds with a DHCPOFFER message, offering an IP address and configuration parameters. The client then sends a DHCPREQUEST message to accept the offer, and the server responds with a DHCPACK message to confirm the assignment.

DHCP also supports lease times, which define how long a device can use an assigned IP address before it must renew the lease or obtain a new one.

Overall, DHCP simplifies network management by automating the process of IP address assignment, reducing configuration errors, and ensuring efficient use of IP address space.

---

In summary, DHCP is like a dynamic address book for networks, automatically assigning IP addresses and configuration settings to devices as they connect.

## TFTP (OB 1.4)

When you need to transfer files within a local network, especially for tasks like updating firmware on network devices, **Trivial File Transfer Protocol (TFTP)** is often used.

**Trivial File Transfer Protocol (TFTP)** is a simple, lightweight, lock-step (one operation at a time) file transfer protocol with **no authentication** used to transfer small files between devices on a local network.

It uses **Port 69** and operates over UDP (User Datagram Protocol). TFTP is typically used for **transferring boot files or configuration files** to network devices like routers, switches, and IP phones.

Due to its simplicity, TFTP does not provide advanced features like directory listing, file deletion, or authentication. This makes it less secure and less reliable than more robust protocols like FTP or SFTP. TFTP is generally used in controlled environments where security is not a primary concern.

Overall, TFTP is a straightforward protocol for transferring files in specific scenarios, particularly in local networks where simplicity and speed are prioritized over security.

---

In summary, TFTP is a basic file transfer protocol used for simple file transfers within local networks, often for device configuration and firmware updates.

## HTTP and HTTPS (OB 1.4)

When you browse the web, you typically use **HTTP (Hypertext Transfer Protocol)** or **HTTPS (Hypertext Transfer Protocol Secure)** to access websites.

### HTTP

**Hypertext Transfer Protocol (HTTP)** is the foundation of data communication on the World Wide Web. It provides a **standard way for web browsers and servers to communicate** and exchange information.

HTTP operates on TCP **Port 80** and is used to transfer **hypertext documents**, such as HTML pages, images, and videos. It follows a request-response model, where a client (web browser) sends a request to a server, and the server responds with the requested resource.

HTTP is a **stateless protocol**, meaning that each request is independent, and the server does not retain any information about previous requests.

One of the main drawbacks of HTTP is that it does not provide any security features, making it vulnerable to eavesdropping and man-in-the-middle attacks. It transmits data in plain text, which can be intercepted by malicious actors.

### HTTPS

**Hypertext Transfer Protocol Secure (HTTPS)** is an extension of HTTP that adds a layer of security by using **SSL/TLS (Secure Sockets Layer/Transport Layer Security)** to encrypt the data being transmitted.

HTTPS operates on TCP **Port 443** and ensures that the communication between the client and server is secure and private. It does this by encrypting the data and ensuring the integrity and security of the data being exchanged.

**TLS is the standard security technology for establishing an encrypted between web browsers and servers.**

When you visit a website using HTTPS, you will often see a padlock icon in the address bar, indicating that the connection is secure.

Overall, HTTPS is the preferred choice for secure web communication, especially for websites that handle sensitive information such as login credentials, financial transactions, and personal data.

---

In summary, while HTTP is used for general web communication, HTTPS provides a secure and encrypted way to access websites, ensuring the privacy and integrity of the data being transmitted.

## Email Protocols (OB 1.4)

When you send and receive emails, several protocols work together to ensure that your messages are delivered correctly.

### SMTP

**Simple Mail Transfer Protocol (SMTP)** is the standard protocol used for sending emails across the Internet.

SMTP operates on **Port 25** (and sometimes Port 587 for secure submission) to transfer email messages from a client (email sender application) to a mail server or between mail servers. It is responsible for the **outgoing** email delivery process.

It is used primarily for sending emails, not for receiving them. SMTP works in conjunction with other protocols like POP3 or IMAP that handle email retrieval and storage.

SMTP is insecure by default, as it transmits data in plain text. However, it can be secured using TLS (Transport Layer Security) to encrypt the communication between email clients and servers.

### SMTP Secure (SMTPS)

**Simple Mail Transfer Protocol Over Transport Layer Security (SMTPS)** is a secure version of SMTP that uses TCP **Port 587** to encrypt email transmissions between email clients and servers.

This protocol enhances the security of SMTP by encrypting the data transferred, protecting sensitive information such as login credentials and email content from interception and eavesdropping.

Port 587 is the preferred port for secure email submission, as it supports the use of TLS for encryption.

Overall, SMTPS is the recommended choice for sending emails securely, ensuring that your messages are protected during transmission.

### POP3

**Post Office Protocol version 3 (POP3)** is a standard mail protocol used to **retrieve emails from a remote server** to a local email client over a TCP/IP connection.

POP3 operates on **Port 110** (and Port 995 for secure connections) and allows emails to be downloaded and stored locally on the user's device. Once emails are downloaded, they are typically deleted from the server, making them accessible only on the device where they were retrieved.

It is designed for situations where the email client accesses the mail server infrequently, allowing users to read their emails offline.

POP3 is a simple and efficient protocol but lacks advanced features like folder management and synchronization across multiple devices.

POP3 does lack security by default, as it transmits data in plain text. However, it can be secured using SSL/TLS to encrypt the communication between the email client and server.

### POP3 Secure (POP3S)

**Post Office Protocol version 3 Over SSL/TLS (POP3S)** is a secure version of POP3 that uses TCP **Port 995** to securely retrieve emails from a remote server to a local email client over an SSL/TLS encrypted connection.

This protocol ensures that email messages and authentication credentials are secure during transmission, protecting them from interception and eavesdropping.

Port 995 is the designated port for secure POP3 connections, providing an added layer of security for email retrieval.

### IMAP

**Internet Message Access Protocol (IMAP)** is another standard mail protocol used to **retrieve emails from a remote server**, but it offers more advanced features compared to POP3.

IMAP operates on **Port 143** (and Port 993 for secure connections) and allows users to access and manage their emails directly on the mail server. Unlike POP3, IMAP keeps the emails on the server, enabling users to synchronize their email across multiple devices.
This means that actions such as reading, deleting, or organizing emails are reflected on all devices connected to the same email account.

IMAP is ideal for users who need to access their emails from various locations and devices, providing greater flexibility and convenience.

Overall, IMAP is the preferred choice for email retrieval when users require synchronization and access from multiple devices.

However, like POP3, IMAP does not provide security by default, as it transmits data in plain text. It can be secured using SSL/TLS to encrypt the communication between the email client and server.

### IMAP Secure (IMAPS)

**Internet Message Access Protocol Over SSL/TLS (IMAPS)** is a secure version of IMAP that uses TCP **Port 993** to securely retrieve and manage emails from a remote server to a local email client over an SSL/TLS encrypted connection.

This secure version of IMAP ensures that email messages and authentication credentials are protected during transmission, preventing interception and eavesdropping.

Port 993 is the designated port for secure IMAP connections, providing an added layer of security for email retrieval and management.

---

In summary, SMTP is used for sending emails, while POP3 and IMAP are used for retrieving emails, with their secure versions (SMTPS, POP3S, and IMAPS) providing encryption to protect email communications.

## NTP (OB 1.4)

One of the most functions across the network is timestamping. Timestamping is basically when protocols or data left the device or arrived at the device. Event logging, error reporting, and many other functions rely on accurate timestamps.

When you connect to a network, it's important that your device's clock is synchronized with other devices on the network. This is where the **Network Time Protocol (NTP)** comes into play.

**Network Time Protocol (NTP)** is a networking protocol used to **synchronize the clocks** of computers over a network.

In other words, it ensures that all devices on a network have the same accurate time.

NTP operates over UDP **Port 123** and uses a hierarchical system of time sources to distribute accurate time information.

It is designed to **mitigate the effects of variable network latency** over packet-switched (e.g., Internet), variable-latency data networks.

It provides **high precision time correction** to networked devices, ensuring that their clocks are synchronized to within a few milliseconds of each other.

NTP uses a system of time servers organized in a hierarchical structure, with **stratum levels** indicating the distance from the reference clock. Stratum 0 represents high-precision time sources like atomic clocks or GPS receivers, while higher stratum levels represent servers that synchronize their time from lower stratum servers.

> Fun Fact: You can actually set up your own NTP server using a GPS receiver to get accurate time signals from satellites!

Overall, NTP is a crucial protocol for maintaining accurate time synchronization across networked devices, which is essential for various applications and services.

---

In summary, NTP ensures that all devices on a network have synchronized clocks, which is vital for accurate timestamping and event logging.

## SNMP (OB 1.4)

When it comes to managing the network, you're not going to have not just one device but multiple devices like routers, switches, servers, and more. To effectively monitor and manage these devices, network administrators use the **Simple Network Management Protocol (SNMP)**.

**Simple Network Management Protocol (SNMP)** is an application-layer protocol used for **managing and monitoring network devices** on IP networks.

SNMP operates over UDP **Port 161** for sending commands from the management station to the network devices and UDP **Port 162** for receiving notifications (traps) from the devices to the management station.

SNMP enables network administrators to manage network performance, detect and troubleshoot network issues, and plan for network growth. It allows administrators to collect information about network devices, such as their status, performance metrics, and configuration settings.

SNMP works by using a manager-agent model, where the SNMP manager (management station) communicates with SNMP agents (network devices) to retrieve or modify information stored in the devices' Management Information Base (MIB).

SNMP has three main versions: SNMPv1, SNMPv2c, and SNMPv3. Each version introduces improvements in functionality and security.

**Only use version 3 of SNMP** as it provides enhanced security features, including authentication and encryption, to protect against unauthorized access and data interception.

---

In summary, SNMP is a vital protocol for network management, allowing administrators to monitor and control network devices effectively.

## LDAP (OB 1.4)

If you work in a big company, a company that has thousands of employees, managing all the different user accounts, passwords, and permissions can become quite complex. Microsoft knew this back in 1990s when they created Active Directory.

What exactly is Active Directory? Active Directory is basically a directory (a database) that stores information about users, computers, and other resources on a network. It helps administrators manage and organize these resources efficiently. Administrators can create user accounts, assign permissions, and enforce security policies across the network.

To interact with Active Directory, Microsoft uses a protocol called **Lightweight Directory Access Protocol (LDAP)**.

**Lightweight Directory Access Protocol (LDAP)** is an application protocol used to **access and manage directory information services** over a network.

LDAP operates on **Port 389** for standard communication.

It provides a way to query and modify directory services, allowing users and applications to retrieve information about users, groups, computers, and other resources stored in the directory.

LDAP is widely used in various applications, including email clients, web applications, and network operating systems, to authenticate users and manage access to resources.

However, LDAP does not provide encryption by default, making it vulnerable to interception and eavesdropping.

## LDAP Secure (LDAPS)

**Lightweight Directory Access Protocol Over SSL/TLS (LDAPS)** is a secure version of LDAP that uses TCP **Port 636** to encrypt the communication between clients and directory servers using SSL/TLS.

This secure version of LDAP ensures that sensitive information, such as user credentials and directory data, is protected during transmission, preventing interception and eavesdropping.

---

In summary, LDAP is a crucial protocol for accessing and managing directory services, enabling efficient user and resource management in large networks.

## SMB (OB 1.4)

In networking, you'd often want to share files and printers between computers. We talked about FTP and SFTP for file transfers, but within a local network, especially in Windows environments, the **Server Message Block (SMB)** protocol is commonly used for this purpose.

**Server Message Block (SMB)** is a network protocol used for **network file sharing, printer sharing, and inter-process communication** between computers on a local network.

SMB operates over TCP **Port 445** and is used primarily in Windows environments for file and printer sharing and inter-process communication.

The use of port 445 allows SMB to function without the need for the older NetBIOS layer, which used ports 137-139.

## Syslog (OB 1.4)

In a network, you may have hundreds or even thousands of devices, such as routers, switches, servers, and firewalls. Each of these devices generates logs that contain important information about their operation, performance, and security events.

To effectively manage and analyze these logs, network administrators use the **Syslog** protocol.

**Syslog** is a standard protocol for **message logging**, allowing devices and servers to send event messages across IP networks to a centralized log server, known as a syslog server.

It provides a way to **track and record system events**, errors, and other important information generated by network devices and applications. It is crucial for network and system monitoring, troubleshooting, and security auditing.

Syslog can operate over both UDP and TCP, typically using **Port 514** for communication. UDP is commonly used for its simplicity and low overhead, while TCP provides reliable delivery of log messages.

Overall, Syslog is an essential protocol for managing and analyzing log data in networked environments, helping administrators maintain the health and security of their systems.

---

In summary, Syslog enables centralized logging and monitoring of network devices, facilitating effective network management and security auditing.

## SQL Server (OB 1.4)

When dealing with databases, especially in enterprise environments, **SQL Server** is a popular choice for managing and storing data. SQL Server uses specific ports for communication between clients and the database server.

Other than SQL Server, there are other database management systems like MySQL, PostgreSQL, and Oracle Database, each with its own default ports.

**SQL Server** is a **relational database management system (RDBMS)** developed by Microsoft. It is used to store, manage, and retrieve data for various applications.

SQL Server primarily uses **Port 1433** for client connections to the database server. This port is used for communication between SQL Server instances and client applications.

In addition to Port 1433, SQL Server also uses **Port 1434** for the SQL Server Browser service, which helps clients locate SQL Server instances on the network.

Overall, SQL Server is a powerful database management system that provides robust features for data storage, retrieval, and management in enterprise environments.

---

In summary, SQL Server uses specific ports for communication, with Port 1433 being the primary port for client connections to the database server.

## RDP (OB 1.4)

When you need to remotely access a Windows computer, you can use the **Remote Desktop Protocol (RDP)**. RDP allows you to connect to another computer over a network and interact with its desktop as if you were sitting in front of it.

**Remote Desktop Protocol (RDP)** is a proprietary protocol developed by Microsoft that provides a graphical interface to connect to another computer over a network connection.

RDP operates over **Port 3389** and allows users to graphically access and control a
remote computer's desktop environment.

RDP is widely used for remote administration, technical support, and remote work scenarios. It enables users to access their work computers from home or other locations, providing flexibility and convenience.

---

In summary, RDP is a powerful protocol for remote desktop access, allowing users to connect to and control remote Windows computers over a network.

## SIP (OB 1.4)

When it comes to voice and video communication over the Internet, the **Session Initiation Protocol (SIP)** is a key protocol that enables these services.

**Session Initiation Protocol (SIP)** is a **signaling protocol** used for initiating, maintaining, modifying, and terminating real-time sessions that involve video, voice, messaging, and other communications applications and services.

SIP is fundamental to the operation of Voice over IP (VoIP) and multimedia communication systems. It is used to establish and manage communication sessions between endpoints, such as IP phones, video conferencing systems

It operates at the application layer and can work over various transport protocols, including UDP, TCP, and TLS. Port numbers commonly associated with SIP include **Port 5060** for non-encrypted signaling and **Port 5061** for encrypted signaling using TLS.

---

In summary, SIP is a crucial protocol for enabling real-time communication services over IP networks, facilitating voice and video calls, messaging, and other multimedia interactions.
