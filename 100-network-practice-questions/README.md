# 100 Network+ Practice Questions

1. Which of the following best describes the importance of DHCP relay agents in a network?

   D. They forward DHCP messages between clients and servers when they are not on the same subnet.

   > DHCP relay agents are crucial in networks where clients and DHCP servers are on different subnets. They forward DHCP messages between clients and servers, allowing clients to obtain IP addresses and other configuration information even when they are not on the same subnet as the DHCP server.

---

2. Which of the following DNS record type is used to map a domain name to an IPv4 address?

   D. A record

   > An A record (Address record) is used in DNS to map a domain name to an IPv4 address. It allows users to access websites using human-readable domain names instead of IP addresses.

---

3. Which protocol is used by the Session layer to manage communication sessions between networked devices?

   A. RPC (Remote Procedure Call)

   > RPC is used by the Session layer to manage communication sessions between networked devices. It allows a program to execute a procedure on a remote server as if it were local, facilitating communication and coordination between applications across a network. It maintains a session between two devices, ensuring that data is properly synchronized and that communication is maintained throughout the session.

---

4. How does an IPS differ from an IDS?

   D. IDS detects and alerts on potential threats, while an IPS can take action to block or mitigate those threats.

   > An Intrusion Detection System (IDS) is designed to detect and alert on potential security threats or malicious activities within a network. It monitors network traffic and system activities for signs of suspicious behavior, generating alerts when it identifies potential threats. An Intrusion Prevention System (IPS), on the other hand, not only detects potential threats but also takes proactive measures to block or mitigate those threats. An IPS can automatically respond to detected threats by blocking traffic, terminating connections, or implementing other security measures to prevent the threat from causing harm to the network.

---

5. Which protocol is commonly used to establish secure VPN connections?

   C. IPSec (Internet Protocol Security)

   > IPSec is a suite of protocols used to establish secure VPN connections. It provides encryption, authentication, and integrity for data transmitted over a network, ensuring that the communication between devices is secure and protected from unauthorized access. IPSec can be used in various VPN configurations, such as site-to-site or remote access VPNs, to create secure tunnels for data transmission over the internet or other untrusted networks.

---

6. How does NAT enhance network security?

   C. By hiding internal IP addresses from external networks

> NAT (Network Address Translation) enhances network security by hiding internal IP addresses from external networks. It allows multiple devices on a local network to share a single public IP address when accessing the internet. This means that external entities cannot directly access the internal devices, as they only see the public IP address. This provides an additional layer of security by making it more difficult for attackers to target specific devices within the internal network.

---

7. Which port is commonly used SSH for secure communication?

   B. Port 22

   > SSH (Secure Shell) commonly uses port 22 for secure communication. It is a protocol that provides a secure channel over an unsecured network, allowing users to securely access and manage remote devices and servers. By using port 22, SSH ensures that the communication between the client and server is encrypted and protected from eavesdropping or unauthorized access.

   > Port 20 is used for FTP data transfer, while port 21 is used for FTP control commands. Port 23 is used for Telnet, which is an unsecured protocol for remote access.

---

8. Which of the following ports is used for secure web traffic?

   A. Port 443

   > Port 443 is used for secure web traffic, specifically for HTTPS (Hypertext Transfer Protocol Secure). HTTPS encrypts the data transmitted between a user's browser and a web server, providing a secure connection and protecting sensitive information from being intercepted by attackers. Port 80 is used for unsecured HTTP traffic and port 110 is used for POP3 email retrieval.

---

9. A company has been assigned the network address 192.168.10.0/24. How many usable IP addresses are available for hosts on this network?

   B. 254

   > A /24 subnet mask allows for 256 total IP addresses (2^8), but two of those addresses are reserved: one for the network address (192.168.10.0) and one for the broadcast address (192.168.10.255). This leaves 254 usable IP addresses for hosts on the network.

---

10. Which of the tools is MOST commonly used for analyzing and detecting network-based attacks?

    A. Wireshark

    > Wireshark is a widely used network protocol analyzer that allows users to capture and analyze network traffic in real-time. It is commonly used for analyzing and detecting network-based attacks by providing detailed insights into the data packets being transmitted across the network. Wireshark can help identify suspicious activities, such as unusual traffic patterns, unauthorized access attempts, or malicious payloads, making it an essential tool for network security professionals.

---

11. Which of the following is NOT a DNS record type associated with email routing or email security?

    A. MX

    B. SPF

    **C. SRV <-- Correct answer**

    D. TXT

    > MX (Mail Exchanger) records are used to specify the mail servers responsible for receiving email on behalf of a domain. SPF (Sender Policy Framework) records are used to specify which mail servers are authorized to send email on behalf of a domain, helping to prevent email spoofing. TXT (Text) records can be used for various purposes, including email security, such as storing SPF records or other information related to email authentication. SRV (Service) records, on the other hand, are used to specify the location of services within a domain and are not directly associated with email routing or email security.

---

12. A network technician is tasked with setting up a high-speed, long-distance link between two buildings that are more than 500 meters apart. The connection must maintain high data integrity and be immune to interference. Which cable type should the technician use?

    A. Multimode fiber optic cable

    B. Coaxial cable

    **C. Single-mode fiber optic cable <-- Correct answer**

    D. Twisted pair cable

    > Note the questions asks for long-distance and immune to interference. Single-mode fiber optic cable is designed for long-distance communication and can maintain high data integrity over distances greater than 500 meters. It uses a single strand of glass fiber to transmit light signals, which allows for higher bandwidth and less signal attenuation compared to multimode fiber optic cable. Coaxial cable and twisted pair cable are not suitable for long-distance connections and are more susceptible to interference, making them less ideal for this scenario.

---

13. A government agency requires a security model for its classified information system. The model must ensure strict access control based on the sensitivity of the information and the clearance level of users. Only users with the appropriate security clearance should be able to access certain data, regardless of their role or job function. Which access control model is the MOST appropriate for this scenario?

    A. Discretionary Access Control (DAC)

    **B. Mandatory Access Control (MAC) <-- Correct answer**

    C. Role-Based Access Control (RBAC)

    D. Attribute-Based Access Control (ABAC)

    > Mandatory Access Control (MAC) is the most appropriate access control model for this scenario. MAC is a security model that enforces strict access control based on the sensitivity of the information and the clearance level of users. In a MAC system, access decisions are made by the system based on predefined policies, and users cannot change access permissions. This ensures that only users with the appropriate security clearance can access certain data, regardless of their role or job function, making it ideal for classified information systems in government agencies. Discretionary Access Control (DAC) allows users to control access to their own resources, which may not be suitable for highly sensitive information. Role-Based Access Control (RBAC) and Attribute-Based Access Control (ABAC) are more flexible but may not provide the strict access control required for classified information systems.

---

14. Which of the following allows a single public IP address to represent multiple private IP addresses by tracking traffic using different port numbers?

    A. Dynamic DNS

    B. VPN

    C. Subnetting

    **D. Port Address Translation (PAT) <-- Correct answer**

    > Port Address Translation (PAT), also known as NAT overload, allows a single public IP address to represent multiple private IP addresses by tracking traffic using different port numbers. This enables multiple devices on a local network to share a single public IP address for accessing external networks, such as the internet. Dynamic DNS, VPN, and subnetting do not provide this functionality. An example of PAT in action is when multiple devices on a home network access the internet through a single public IP address provided by the ISP. Each device is assigned a unique port number, allowing the router to keep track of which internal device is associated with each outgoing connection.

---

15. Which of the following is a distance-vector routing protocol used in smaller networks for routing data between routers?

    A. FTP

    B. STP

    C. OSPF

    **D. RIP <-- Correct answer**

    > Routing Information Protocol (RIP) is a distance-vector routing protocol used in smaller networks for routing data between routers. RIP uses hop count as its primary metric for determining the best path to a destination network. It is simple to configure and suitable for small networks but has limitations in larger networks due to its maximum hop count of 15 and slower convergence times. OSPF, on the other hand, is a link-state routing protocol that is more suitable for larger and more complex networks. FTP and STP are not routing protocols and do not perform the same function as RIP.

---

16. What physical tool should a technician use to verify the integrity of an Ethernet cable?

    C. Cable tester

    > A cable tester is a physical tool used to verify the integrity of an Ethernet cable. It can check for continuity, identify wiring faults, and ensure that the cable is properly connected. Cable testers can also measure the length of the cable and detect any breaks or shorts in the wiring. A multimeter can be used for basic electrical testing but may not provide the specific functionality needed for testing Ethernet cables. A cable crimper is used for attaching connectors to cables, and a wire stripper is used for removing the insulation from wires, but neither of these tools is designed for testing the integrity of a cable.

---

17. Which of the following devices acts as a multiport network appliance that operates primarily at Layer 2 (Data Link layer) of the OSI model, using MAC address tables to forward data traffic based on hardware addresses, thereby segregating collision domains within a broadcast domain?

    **A. Switch <-- Correct answer**

    B. Hub

    C. Access Point

    D. Router

    > A switch is a multiport network appliance that operates primarily at Layer 2 (Data Link layer) of the OSI model. It uses MAC address tables to forward data traffic based on hardware addresses, allowing it to segregate collision domains within a broadcast domain. This means that each port on a switch creates a separate collision domain, improving network performance and reducing collisions compared to a hub, which operates at Layer 1 (Physical layer) and does not use MAC address tables. An access point is used for wireless networking, and a router operates at Layer 3 (Network layer) to route traffic between different networks.

---

18. A network technician has received reports of slow network performance from several users on the same subnet. The technician confirms that the issue is consistent across multiple devices and that other subnets are not affected. According to the troubleshooting methodology, what should the technician do NEXT?

    A. Escalate the issue to a higher level of support

    B. Test and implement a potential solution

    **C. Establish a theory of probable cause <-- Correct answer**

    D. Document the finding and actions

    > Following the troubleshooting methodology, after identifying the problem and gathering information (in this case, confirming the issue is isolated to a specific subnet), the next step is to establish a theory of probable cause.

---

19. After an investigation, an IT department discovered that many employees are accessing social media and streaming websites during work hours. The company wants to ensure that employees can only access work-related websites during business hours. What should the do NEXT to address this issue?

    A. Configure the firewall to block specific ports used by these websites

    **B. Deploy a web proxy server with content filtering to restrict access to non-work-related websites <-- Correct answer**

    C. Enable port mirroring to monitor employee internet traffic in real-time

    D. Set up logging on the router to capture all employee web traffic

    > Deploying a web proxy server with content filtering is the most effective way to restrict access to non-work-related websites during business hours. A web proxy can be configured to allow or block access to specific websites based on predefined rules, ensuring that employees can only access work-related websites. Configuring the firewall to block specific ports may not be effective, as many websites use common ports (e.g., port 80 for HTTP and port 443 for HTTPS). Enabling port mirroring and setting up logging can help monitor employee internet traffic but do not directly address the issue of restricting access to certain websites.

---

20. What is the golden configuration in the context of network device management?

    A. A configuration that allows for maximum throughput on a network devices

    B. A temporary configuration applied during scheduled maintenance windows

    C. A dynamic configuration that automatically adjusts based on network conditions

    **D. A baseline configuration that is known to be stable and secure, used as a reference for future configurations and troubleshooting <-- Correct answer**

    > The golden configuration is a baseline configuration that is known to be stable and secure. It serves as a reference for future configurations and troubleshooting. By maintaining a golden configuration, network administrators can quickly restore devices to a known good state in case of misconfigurations or issues, ensuring consistent performance and security across the network. It is not necessarily focused on maximum throughput, temporary maintenance, or dynamic adjustments based on network conditions.
