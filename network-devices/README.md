# Network Devices

## Hardware vs Virtual Appliances (OB 1.2)

Physical appliances are **dedicated hardware devices** focused on specific networking tasks, such as firewalls, routers, or switches, offering high performance and reliability but at a higher cost and with space requirements.

Virtual appliances are **software-based solutions** that run on virtual machines, providing similar functionalities as physical appliances but with greater flexibility, scalability, and cost-effectiveness, but potentially at the expense of raw performance.

## Router (OB 1.2)

When you have a network, you are going to want to connect it to other networks. For example, let's say you have a home network with multiple devices, and you want to connect to the outside world (the internet). A router is a device that connects your home network to the internet, allowing your devices to communicate with other devices on different networks.

A router operates at the **network layer (Layer 3)** of the OSI model, directing **data packets** between different networks based on their IP addresses. It uses routing tables and protocols to determine the best path for data to travel.

Routers use **routing tables** to determine the best path for forwarding data packets to their destination, connecting **multiple networks** together, such as a local network to the internet.

Routers also provide network security features like **firewalls** and **VPN support**, helping to protect your network from unauthorized access.

## Switches (OB 1.2)

When you are working in a network, two terms you might hear are a **broadcast domain** and a **collision domain**.

A **broadcast domain** is a logical division of a computer network, in which all devices can reach each other by broadcast at the data link layer.

A **collision domain** is a network segment where data packets can collide with one another when being sent on a shared medium or through repeaters.

Back in the day, we used to use hubs to connect devices in a network. A hub is a simple networking device that connects multiple devices in a network, but it has some limitations. Hubs operate at the **physical layer (Layer 1)** of the OSI model and simply **broadcast incoming data packets** to all connected devices, leading to potential **collisions** and inefficiencies.

Collisions are a problem because when two devices send data at the same time, the data can collide and become corrupted, leading to retransmissions and slower network performance.

The technology that allows it to detect collisions is called **Carrier Sense Multiple Access with Collision Detection (CSMA/CD)**. CSMA/CD is a protocol used in Ethernet networks to manage how devices share the same communication channel and handle collisions.

The hubs are basically repeaters that amplify the signal and send it to all devices connected to the hub. This means that all devices connected to the hub are in the same collision domain, which can lead to performance issues as more devices are added to the network.

How do you solve this problem? You use a switch!

A switch works differently. A switch has a table called a **MAC address table** that maps the MAC addresses of connected devices to specific ports on the switch. It operates at the **data link layer (Layer 2)** of the OSI model and **forwards data packets only to the specific device** they are intended for, based on their MAC addresses. This means that each device connected to the switch has its own collision domain, reducing the chances of collisions and improving overall network performance.

In theory, switches have no collisions because each port on a switch represents a separate collision domain. However, in practice, collisions can still occur in certain scenarios, such as when multiple devices connected to the same switch port attempt to send data simultaneously in a half-duplex mode. In full-duplex mode, where devices can send and receive data simultaneously, collisions are effectively eliminated.

There is a problem with switches, though. It is called **broadcast domains**.

Let's say you have a switch with multiple devices connected to it. Before computer A can send data to computer C, it needs to know the MAC address of computer C. How does it find out? It sends a **broadcast** message to all devices in the network, asking "Who has this MAC address?" This broadcast message is sent to all devices connected to the switch, which means that all devices in the network receive the message, even if they are not the intended recipient. This creates a broadcast domain, where all devices can hear each other's broadcast messages. Computer C will respond with its MAC address, and computer A can then send the data directly to computer C.

This works with a protocol called **Address Resolution Protocol (ARP)**, which is used to map IP addresses to MAC addresses in a local network.

In summary, switches help to reduce collisions in a network by providing each device with its own collision domain, but they can still create broadcast domains where all devices can hear each other's broadcast messages. And a router can be used to break up broadcast domains.

### What Exactly is a Switch?

A switch operates at the **data link layer (Layer 2)** of the OSI model and is responsible for **forwarding data packets** between devices within the same network based on their MAC addresses.

Switches maintain a **MAC address table** that maps MAC addresses to specific physical ports on the switch. When a data packet arrives at the switch, it examines the destination MAC address and forwards the packet only to the port associated with that address, rather than broadcasting it to all ports like a hub would. This selective forwarding reduces network congestion and improves overall performance.

It creates **separate collision domains** for each connected device, meaning that data collisions are minimized, leading to more efficient communication.

Switches can also support **VLANs (Virtual Local Area Networks)**, allowing network administrators to segment a physical network into multiple logical networks for improved security and traffic management.

## Firewalls (OB 1.2)

A **firewall** is a network security device that **monitors** incoming and outgoing network traffic and decides whether to **allow** or **block** specific traffic based on a defined set of **security rules**.

Firewalls are crucial for establishing a **barrier** between secure **internal** networks and **untrusted external** networks, such as the internet, to protect against unauthorized access, cyber threats, and data breaches.

It can be hardware-based, software-based, or a combination of both. Hardware firewalls are physical devices that are typically placed between a network and the internet, while software firewalls are installed on individual computers or servers.

Firewalls can operate at various layers of the OSI model, including the network layer (Layer 3) and the application layer (Layer 7), providing different levels of security and control over network traffic.

## IDS/IPS (OB 1.2)

When it comes to managing a network in today's world, security is a top priority. Two important tools used to enhance network security are **Intrusion Detection Systems (IDS)** and **Intrusion Prevention Systems (IPS)**.

IDS and IPS can be implemented as hardware appliances, software applications, or a combination of both. They can be deployed at various points in a network, such as at the perimeter or within internal segments, to monitor and protect against potential threats.

### What is an IDS/IPS?

An **Intrusion Detection System (IDS)** is a security tool that can detect malicious network activity or policy violations. It monitors network traffic and analyzes it for signs of suspicious behavior, such as unauthorized access attempts, malware infections, or other security threats. When an IDS detects a potential threat, it generates an alert to notify network administrators, allowing them to take appropriate action.

- Uses signature identification techniques like antimalware software. For example, if a known virus signature is detected in network traffic, the IDS will generate an alert.
- Additionally, can detect malicious activity based on anomalies or deviations from normal behavior. For example, if a user suddenly starts accessing large amounts of sensitive data, the IDS may flag this as suspicious behavior.

An **Intrusion Prevention System (IPS)**, on the other hand, goes a step further by not only detecting potential threats but also taking proactive measures to block or prevent them from causing harm. An IPS can automatically respond to detected threats by dropping malicious packets, blocking IP addresses, or resetting connections.

- Rules must be configured on an IPS to define what actions to take when a threat is detected. For example, if an IPS detects a known malware signature, it can be configured to automatically drop the malicious packets and block the source IP address.

Both of these systems can operate at multiple layers of the OSI model, including the network layer (Layer 3) and the application layer (Layer 7), providing comprehensive protection against a wide range of threats.

### How IDS/IPS Work?

In a small example, let's say you have a network with several devices connected to it, including computers, servers, and other network appliances. An IDS/IPS can be connected to a port on a switch or router, allowing it to monitor all network traffic passing through that point. As traffic goes through the switch and its destinations, the switch sends a copy of the traffic to the IDS/IPS for analysis. This is called **port mirroring** or **SPAN (Switched Port Analyzer)**.
The IDS/IPS analyzes the traffic in real-time, looking for signs of malicious activity or policy violations. If it detects a potential threat, it generates an alert (in the case of an IDS) or takes proactive measures to block or prevent the threat (in the case of an IPS). This helps to protect the network from unauthorized access, data breaches, and other security threats.

## Load Balancers (OB 1.2)

In your career, you are going to be managing big networks with lots of users. And lots of users means lots and lots of servers. When you have lots of servers, you need a way to make sure that the traffic is distributed evenly across all of them. This is where a **load balancer** comes in.

Imagine a scenario where you have many users and these users are all trying to access data on one server. What if its 1000+ users? 10,000? 1,000,000? And your server is not that powerful. The server can only handle so much traffic before it becomes overwhelmed and starts to slow down or crash.
What you would do is get more servers to handle the load. But now you have a new problem: how do you make sure that the traffic is distributed evenly across all of these servers?
You need to balance the load. You need something that we can plugin, that all the user requests go to first, and then distribute those requests across all of the servers. This is what a load balancer does.

A load balancer **distributes** incoming network traffic across **multiple servers** to ensure that no single server becomes overwhelmed with too much traffic. By spreading the workload evenly or according to specific algorithms, load balancers help to improve the performance, reliability, and availability of applications and services.

Load balancers can operate at various layers of the OSI model, including the **transport layer (Layer 4)**, the **application layer (Layer 7)**, and the **network layer (Layer 3)**, providing different levels of control and functionality.

A load balancer can be implemented as a hardware appliance, a software application, or a cloud-based service.

Coming back to our example, let's say you set up three more servers to handle the load. Now you have four servers in total. You set up a load balancer in front of these servers. When a user tries to access data, their request goes to the load balancer first. The load balancer then decides which server to send the request to based on factors like current server load, response time, or specific algorithms (like round-robin, least connections, etc.). This way, the traffic is distributed evenly across all four servers, preventing any single server from becoming overwhelmed.
If one of the servers goes down, no one will notice because the load balancer will simply stop sending traffic to that server and distribute the load among the remaining servers. This helps to ensure that the application or service remains available and responsive, even in the face of server failures or high traffic loads.

## Proxy Servers (OB 1.2)

When you manage a network, do you want your users to have unrestricted access to the internet? Or do you want them to have specific access? Do you want to limit what websites they can go to? You've probably experienced this in schools or workplaces where certain websites are blocked. This is where a **proxy server** comes in.

A proxy server acts as an **intermediary** between a user's device and the internet. When a user makes a request to access a website or online resource, the request first goes to the proxy server. The proxy server then forwards the request to the internet on behalf of the user, retrieves the requested content, and sends it back to the user's device.

It can provide additional functionalities such as content caching, access control, and filtering, enhancing both performance and security.

A proxy server is technically a type of firewall, as it can enforce security policies and control access to resources based on predefined rules. By acting as an intermediary, a proxy server can help to protect the internal network from external threats and unauthorized access.

Proxy servers can be implemented as hardware appliances, software applications, or cloud-based services.

For example, let's say you are managing a network for a company. You want to make sure that your employees can only access certain websites during work hours. You set up a proxy server that filters internet traffic based on predefined rules. When an employee tries to access a website, their request goes to the proxy server first. The proxy server checks the request against its rules and decides whether to allow or block the request. If the request is allowed, the proxy server forwards it to the internet and retrieves the requested content. If the request is blocked, the proxy server sends a message back to the employee's device, informing them that access to the website is not allowed.

In summary, a proxy server acts as an intermediary between users and the internet, providing functionalities such as access control, content filtering, and security enforcement to manage and protect network traffic.

## Network Attached Storage (NAS) (OB 1.2)

A Network Attached Storage (NAS) is a **dedicated file storage device** that provides centralized data storage and file sharing capabilities over a network. It is designed to be easily accessible by multiple users and devices, allowing them to store, retrieve, and share files from a central location.

NAS systems are designed for **easy file sharing, data backups, and centralized data management**, supporting various file protocols such as SMB/CIFS, NFS, and AFP.

They offer a scalable and cost-effective solution for businesses and home users needing reliable and accessible storage solutions.

NAS devices typically connect to a local area network (LAN) via Ethernet and can be accessed by computers, smartphones, tablets, and other networked devices. They often come with built-in features such as RAID (Redundant Array of Independent Disks) for data redundancy and protection, user access controls, and remote access capabilities.

For example, in a small office environment, a NAS device can be set up to store shared documents, project files, and multimedia content. Employees can access the NAS from their computers to collaborate on files, back up important data, and share resources without needing to transfer files via email or external drives. The NAS provides a centralized location for data storage, making it easier to manage and secure the organization's data.

In summary, Network Attached Storage (NAS) is a dedicated file storage device that provides centralized data storage and file sharing capabilities over a network, making it easy for multiple users and devices to access and manage files from a central location.

## Storage Area Network (SAN) (OB 1.2)

Previously, we discussed Network Attached Storage (NAS), which is a dedicated file storage device that provides centralized data storage and file sharing capabilities over a network.

In a big business environment, they don't just need file storage; they need the ability to process large amounts of data quickly and efficiently.

What they have is an even bigger device called a **Storage Area Network (SAN)**.

A <u>Storage Area Network (SAN)</u> is a dedicated, high-speed network that **provides block-level storage access** to servers. Unlike NAS, which operates at the file level (file-level storage), SANs allow servers to access raw storage blocks (block-level storage), enabling more efficient data processing and management.

<u>SANs</u> are designed to **handle large volumes of data transfers**, providing high performance, scalability, and reliability for enterprise storage needs.

They are commonly used in enterprise environments to enhance storage solutions and improve data access speeds for applications such as databases, virtualization, and large-scale data processing.

SANs typically use specialized networking technologies such as Fibre Channel or iSCSI to connect storage devices (like disk arrays or tape libraries) to servers. This dedicated network allows for faster data transfer rates and reduced latency compared to traditional network storage solutions.

SANs have their own switches and cabling, separate from the regular data network, to ensure optimal performance and reliability. Via switches, it can connect multiple servers to multiple storage devices, creating a flexible and scalable storage infrastructure.

For example, in a large data center, a SAN can be implemented to provide high-speed storage access for multiple servers running critical applications. The SAN allows these servers to read and write data directly to the storage devices at the block level, improving performance and reducing bottlenecks. This setup is particularly beneficial for applications that require fast access to large datasets, such as databases or virtualized environments.

In summary, a Storage Area Network (SAN) is a dedicated, high-speed network that provides block-level storage access to servers, enabling efficient data processing and management for enterprise storage needs.

### NAS vs SAN

NAS and SAN are both storage solutions used in networking, but they have some key differences:

- **Storage Type**: NAS operates at the file level, providing file-based storage and sharing capabilities, while SAN operates at the block level, allowing servers to access raw storage blocks for more efficient data processing.
- **Network Type**: NAS devices connect to a local area network (LAN) using standard Ethernet protocols, while SANs use specialized networking technologies such as Fibre Channel or iSCSI for high-speed data transfer.
- **Use Cases**: NAS is typically used for file sharing, data backups, and centralized data management in small to medium-sized environments. SANs are used in enterprise environments that require high performance, scalability, and reliability for applications such as databases, virtualization, and large-scale data processing.
- **Performance**: SANs generally offer higher performance and lower latency compared to NAS due to their dedicated network infrastructure and block-level access.
- **Complexity**: SANs are more complex to set up and manage compared to NAS, often requiring specialized knowledge and equipment.

In summary, NAS and SAN are both storage solutions with different architectures, use cases, and performance characteristics. NAS is suitable for file-level storage and sharing, while SAN is designed for high-performance block-level storage access in enterprise environments.

## Access Points and Wireless Controllers (OB 1.2)

Modern networks that are being built today are not really built-in wired solutions unless the environment absolutely requires super high speeds. What we mean by built-in wired solutions is that everything is connected via Ethernet cables. Most networks today are a combination of wired and wireless solutions.

A wireless network is made up of two main components: **access points (APs)** and **wireless controllers**.

A dedicated access point (AP) gives wireless devices the ability to connect to a wired network using Wi-Fi or related standards. Access points are typically connected to a wired router, switch, or hub via an Ethernet cable, and they broadcast a Wi-Fi signal that allows wireless devices to connect to the network.

In more detail, an access point (AP) is a networking device that allows **wireless devices** to connect to a wired network using Wi-Fi or related standards.

**APs operate at the data link layer (Layer 2)** of the OSI model and are responsible for **managing wireless connections**, including authentication, encryption, and data transmission. They bridge the gap between wired and wireless networks, enabling devices such as laptops, smartphones, and tablets to access network resources without the need for physical cables.

They **extend the wireless coverage area** of a network and can manage multiple wireless connections simultaneously, providing reliable and secure access to network resources.

In enterprise networks, you are not going to have just one access point. You are going to have multiple access points spread throughout the building to provide adequate coverage. This is where a **wireless controller** comes in.

A Wireless LAN Controller (WLC) is a networking device that **manages multiple wireless access points (APs)** in a network. It provides centralized control and management of the wireless network, allowing administrators to configure, monitor, and optimize the performance of multiple APs from a single interface.

WLCs simplify the **deployment and management** of large-scale wireless networks, including configuration, security policies, and managing guest access, enhancing the efficiency and security of the wireless infrastructure.

WLCs can also provide features such as load balancing, roaming support, and interference mitigation, ensuring a seamless and reliable wireless experience for users.

For example, in a large office building, multiple access points are installed on different floors to provide Wi-Fi coverage throughout the building. A wireless controller is used to manage all of these access points, allowing network administrators to configure settings, monitor performance, and enforce security policies from a centralized location. This setup ensures that employees can connect to the wireless network seamlessly as they move throughout the building, while also providing robust security and management capabilities for the IT team.

In summary, access points and wireless controllers are essential components of modern wireless networks, providing reliable and secure connectivity for wireless devices while enabling centralized management and control of the wireless infrastructure.

## Content Delivery Networks (CDN) (OB 1.2)

A Content Delivery Network (CDN) is a **globally distributed network of proxy servers** and data centers designed to deliver web content and services rapidly and efficiently to users based on their geographic location.

CDNs **cache** content such as web pages, images, videos, and other digital assets on servers located closer to end-users, reducing latency and improving load times.

They enhance the performance, reliability, and scalability of web applications by distributing content across multiple servers, reducing the load on origin servers, and mitigating the impact of traffic spikes.

CDNs also provide security features such as DDoS protection, secure content delivery, and traffic encryption, helping to safeguard web applications from cyber threats.

For example, when a user accesses a website that utilizes a CDN, their request is routed to the nearest CDN server rather than the origin server. This proximity reduces the distance data must travel, resulting in faster load times and a better user experience. Additionally, by distributing content across multiple servers, CDNs can handle high traffic volumes more effectively, ensuring that websites remain accessible even during peak usage periods.

In summary, a Content Delivery Network (CDN) is a globally distributed network of proxy servers that delivers web content and services efficiently to users based on their geographic location, enhancing performance, reliability, and security.

## Virtual Private Networks (VPN) (OB 1.2)

One of the most recent changes in networking is the rise of remote work. With more people working from home or other remote locations, there is a need for secure connections to company networks. How are you going to make sure that these remote workers can connect to the company network securely? You use a **Virtual Private Network (VPN)**.

A Virtual Private Network (VPN) is a technology that creates a **safe and encrypted connection** over a less secure network, such as the internet. It allows users to send and receive data as if their devices were directly connected to a private network, providing enhanced security and privacy.

VPNs are used to establish **secure connections** between remote users and a corporate's internal network, allowing for secure data transmission across public networks as if the devices were directly connected to the private network.

They use encryption protocols to protect data from interception and unauthorized access, ensuring that sensitive information remains confidential.

VPNs can be implemented using various protocols, such as IPsec, SSL/TLS, and OpenVPN, each offering different levels of security and performance.

For example, when a remote employee wants to access their company's internal network from home, they can use a VPN client on their device to establish a secure connection to the company's VPN server. The VPN encrypts all data transmitted between the employee's device and the company network, protecting it from potential eavesdropping or interception by malicious actors on the internet. This allows the employee to access company resources, such as files and applications, securely and privately.

In summary, a Virtual Private Network (VPN) is a technology that creates a secure and encrypted connection over a less secure network, enabling remote users to access private networks safely and protecting sensitive data from unauthorized access.

## VOIP (OB 1.2)

On a network, you are going to have different types of traffic. One of the most common types of traffic is voice traffic. Voice traffic is used for making phone calls over the internet. This is called **Voice over Internet Protocol (VoIP)**.

VoIP converts voice signals into digital data packets that can be transmitted over IP networks, allowing for cost-effective and flexible communication solutions.

Usually, VoIP data is prioritized over other types of data on a network to ensure clear and uninterrupted voice communication. This prioritization is often achieved through Quality of Service (QoS) settings that allocate more bandwidth and lower latency for VoIP traffic.

Quality of Service (QoS) refers to the **set of technologies and policies** used to manage and prioritize network traffic to ensure optimal performance for specific types of data, such as voice or video.

QoS assigns **different priority levels** to various types of network traffic, allowing critical applications to receive the necessary bandwidth and low latency required for optimal performance.

This helps in reducing latency, jitter, and packet loss for time-sensitive applications like VoIP and video conferencing while enhancing the overall user experience in networks with limited bandwidth.

For example, in a corporate network, QoS can be configured to prioritize VoIP traffic over regular web browsing or file downloads. This ensures that during peak usage times, voice calls remain clear and uninterrupted, while less critical data traffic may experience slight delays. By implementing QoS policies, network administrators can optimize the performance of essential applications and maintain a high quality of service for users.

In summary, Voice over Internet Protocol (VoIP) is a technology that enables voice communication over IP networks, and Quality of Service (QoS) is used to prioritize VoIP traffic to ensure clear and uninterrupted voice communication.

## TTL (OB 1.2)

On a network, every time you send data from one device to another, that data has to travel through multiple devices, such as routers and switches, before it reaches its destination. Something gets attached to that data called a **Time to Live (TTL)**.

All data in a network must be assigned a TTL value, which is a field in the header of IP packets that indicates the maximum time or number of hops that the data packet is allowed to exist in the network before it is discarded by a router.

TTL helps prevent data packets from **looping indefinitely** in the network due to routing errors or misconfigurations, which can lead to network congestion and performance issues.

Each time a data packet passes through a router, the router decrements the TTL value by one. If the TTL value reaches zero before the packet reaches its destination, the router discards the packet and typically sends an ICMP "Time Exceeded" message back to the sender.

For example, when a user sends an email, the email data is broken down into smaller packets, each with its own TTL value. As these packets travel through various routers on their way to the recipient's email server, each router decreases the TTL value by one. If a packet's TTL reaches zero before it arrives at the destination, that packet is discarded, preventing it from circulating endlessly in the network. This mechanism helps maintain network efficiency and prevents congestion caused by undeliverable packets.

In summary, Time to Live (TTL) is a field in the header of IP packets that indicates the maximum time or number of hops a data packet is allowed to exist in the network, helping to prevent indefinite looping and maintain network efficiency.
