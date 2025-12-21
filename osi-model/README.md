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
