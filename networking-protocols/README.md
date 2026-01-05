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
