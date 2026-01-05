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
