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

Let's say you have a switch with multiple devices connected to it. Before computer A can send data to computer C, it needs to know the MAC address of computer C. How does it find out? It sends a **broadcast** message to all devices in the network, asking "Who has this IP address?" This broadcast message is sent to all devices connected to the switch, which means that all devices in the network receive the message, even if they are not the intended recipient. This creates a broadcast domain, where all devices can hear each other's broadcast messages. Computer C will respond with its MAC address, and computer A can then send the data directly to computer C.

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