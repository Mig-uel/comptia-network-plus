# IP Services

## Setup and Configure DHCP (OB 3.4)

When it comes to setting up a network, one of the most important things you have to do is configure your devices to get their IP addresses.

But what if you have a lot of devices? Manually assigning IP addresses is called **static IP addressing** and can be time-consuming and prone to errors. That's not ideal for a large network.

What you can do instead is use **dynamic IP addressing**.

### Dynamic Addressing

**Dynamic IP addressing** **automates the process of assigning IP addresses** to devices on a network. It allows devices to obtain their IP addresses automatically from a **DHCP (Dynamic Host Configuration Protocol)** server.

The DHCP server maintains a pool of available IP addresses and assigns them to devices as they connect to the network. It also provides other configuration information, such as the subnet mask, default gateway, and DNS server addresses.

This means that when a device connects to the network, it can request an IP address from the DHCP server, which will then assign it an available IP address from a predefined range. This makes it much easier to manage a large number of devices on a network, as you don't have to worry about manually assigning IP addresses or dealing with conflicts.

This method ensures efficient management of IP addresses, reduces the chances of errors, and allows for easy scalability as new devices can be added to the network without needing manual configuration.

It is particularly useful in environments where devices frequently join and leave the network, such as in offices, schools, or public Wi-Fi networks. By using DHCP, network administrators can save time and effort while ensuring that devices can connect seamlessly to the network.

### DHCP (Dynamic Host Configuration Protocol)

**DHCP (Dynamic Host Configuration Protocol)** is a network management protocol used on IP networks. A DHCP server **automatically assigns IP addresses and other network configuration parameters** to devices on the network, allowing them to communicate effectively.

When a device connects to a network, it sends a DHCP request to the DHCP server. The server then responds with a DHCP offer, which includes an available IP address and other configuration information. The device can then accept the offer, and the DHCP server will finalize the assignment of the IP address.

This process allows for efficient management of IP addresses, reduces the chances of errors, and allows for easy scalability as new devices can be added to the network without needing manual configuration.

Let's take at a few key concepts related to DHCP:

**Scope**: A scope is a **defined range of IP addresses** that the DHCP server can assign to devices on the network. It includes the starting and ending IP addresses, as well as other configuration parameters such as the subnet mask and default gateway.

Each scope is configured with a range of IP addresses and other network settings, such as the subnet mask, default gateway, DNS server addresses, and lease duration. The DHCP server uses this information to assign IP addresses to devices on the network. Scopes are essential for organizing and managing IP address distribution within a network.

For example, you can have a range from `192.168.1.1` to `192.168.1.49` to be statically assigned to servers and printers, and a range from `192.168.1.50` to `192.168.1.100` to be dynamically assigned to other devices. This way, you can ensure that critical devices always have the same IP address while allowing other devices to receive dynamic IP addresses as needed.

**Lease Duration/Time**: The lease duration, also known as lease time, is the amount of time that a DHCP server assigns an IP address to a device. When a device receives an IP address from the DHCP server, it is assigned a lease duration, which specifies how long the device can use that IP address before it needs to renew the lease.

Once the lease duration expires, the device must request a new IP address from the DHCP server. This process helps to ensure that IP addresses are efficiently managed and that devices can continue to connect to the network without interruption.

Lease durations can vary depending on the network's needs. For example, in a home network, a longer lease duration may be appropriate since devices typically remain connected for extended periods. In contrast, in a public Wi-Fi network, a shorter lease duration may be more suitable to accommodate a larger number of devices that may connect and disconnect frequently.

**Reservation**: A reservation is a feature of DHCP that allows you to **reserve a specific IP address for a particular device** on the network. This means that whenever that device connects to the network, it will always receive the same IP address from the DHCP server.

Reservations are useful for devices that require a consistent IP address, such as servers, printers, or networked storage devices. By reserving an IP address for these devices, you can ensure that they always have the same address, which can simplify network management and troubleshooting.

To create a reservation, you typically need to provide the MAC address of the device you want to reserve the IP address for, along with the desired IP address. The DHCP server will then associate that IP address with the specified MAC address, ensuring that the device receives the same IP address whenever it connects to the network.

**DHCP Options and Functionality**: DHCP options extend the capabilities of the DHCP protocol by allowing the DHCP server to provide additional configuration information to DHCP clients beyond just IP addresses. These options can include DNS server addresses, Network Time Protocol (NTP) server addresses, Windows Internet Name Service (WINS) server addresses, and more.

By using DHCP options, network administrators can provide clients with the necessary information to properly configure their network settings without requiring manual intervention. This helps to streamline the network configuration process and ensures that devices can connect to the network with the correct settings.

**DHCP Relay**: In some cases, a DHCP server may not be located on the same subnet as the DHCP clients. In such scenarios, a **DHCP relay** can be used to forward DHCP messages between clients and servers across different subnets.

A DHCP relay is a network function that **forwards DHCP requests** from clients on one network segment to a DHCP server on another segment.

This allows devices on different subnets **without a direct DHCP server** to still obtain IP addresses and configuration information from a central DHCP server.

The DHCP relay agent listens for DHCP requests on the local subnet and forwards them to the DHCP server, which then processes the requests and sends back the appropriate responses. This enables efficient management of IP address allocation across multiple subnets in a network.

**Exclusion Ranges**: Exclusion ranges are subsets of a DHCP scope that are **not used for dynamic IP address assignment**. These ranges are reserved for specific purposes, such as static IP addresses for servers, printers, or other critical devices that require a consistent IP address.

These IP addresses are typically reserved for **manual assignment** or for devices that require a fixed IP address, such as servers, printers, or networked storage devices.

Setting up exclusion ranges helps to prevent conflicts between dynamically assigned IP addresses and those that are manually assigned, ensuring that critical devices always have the same IP address while allowing other devices to receive dynamic IP addresses as needed.

**Stateless Address Autoconfiguration (SLAAC)**: Stateless Address Autoconfiguration (SLAAC) is a method used in IPv6 networks to allow devices to automatically configure their own IP addresses without the need for a DHCP server. SLAAC enables devices to generate their own IPv6 addresses based on the network prefix and their own unique identifier, such as the MAC address.

SLAAC works by using the **Router Advertisement (RA)** messages sent by routers on the network. When a device connects to the network, it listens for RA messages, which contain information about the network prefix and other configuration parameters. The device then uses this information to generate its own IPv6 address.

This capability **provides plug-and-play functionality** for IPv6 devices, allowing them to connect to the network and communicate without requiring manual configuration or a DHCP server. SLAAC is particularly useful in environments where devices frequently join and leave the network, such as in home networks or public Wi-Fi networks.

The problem with SLAAC is that it does not provide a way to assign additional configuration information, such as DNS server addresses or default gateway information. This can lead to issues with network connectivity and functionality for devices that rely on this information to communicate effectively on the network. To address this limitation, DHCPv6 can be used in conjunction with SLAAC to provide additional configuration information to devices on the network.

## DNS Server (OB 3.4)

When it comes to a network, one of the most important things you need to set up is a **DNS (Domain Name System) server**. A DNS server is responsible for translating human-readable domain names (like www.example.com) into IP addresses that computers can understand.

### Name Resolution

**Name resolution** is the process of **converting human-readable domain names into IP addresses** that networking equipment can understand and use to route traffic.

It is facilitated by the DNS (Domain Name System), which acts like a phone book for the internet, allowing users to access websites and services using easy-to-remember domain names instead of having to remember complex IP addresses.

When a user enters a domain name into their web browser, the browser sends a request to a DNS server to resolve the domain name into an IP address. The DNS server then looks up the domain name in its database and returns the corresponding IP address to the browser, allowing it to establish a connection with the web server hosting the website.

### Domain Name System (DNS)

The **Domain Name System (DNS)** is a **hierarchical and decentralized naming system** for computers, services, or any resource connected to the internet or a private network.

It translates human-readable domain names into IP addresses that computers use to identify each other on the network.

DNS is essential for the functioning of the internet, as it allows users to access websites and services using easy-to-remember domain names instead of having to remember complex IP addresses.

### Recursive DNS Queries

When a DNS server receives a query for a domain name, it can either provide an answer if it has the information in its cache or forward the query to another DNS server if it does not have the information.

**Recursive DNS queries** involve a DNS server **taking on the responsibility** of retrieving data from other DNS servers on behalf of the client. When a client sends a recursive query to a DNS server, the server will perform the necessary lookups to resolve the domain name and return the final answer to the client.

This process is essential when the local DNS server does not have the requested information in its cache. The server will query other DNS servers, starting from the root servers, then moving to the top-level domain (TLD) servers, and finally to the authoritative name servers for the specific domain until it retrieves the required IP address.

### DNS Zones

A **DNS zone** is a portion of the DNS namespace that is managed by a specific organization or administrator. It contains information about the domain names and their corresponding IP addresses within that portion of the namespace.

> What is a DNS namespace? The DNS namespace is the hierarchical structure of domain names that are used to organize and manage the DNS system. It consists of multiple levels, with the root level at the top, followed by top-level domains (TLDs), second-level domains, and so on.

**DNS zones** are portions of the DNS namespace that are managed by a specific organization or administrator.

A DNS zone can contain multiple domain names and their corresponding IP addresses, as well as other DNS records such as MX (mail exchange) records, CNAME (canonical name) records, and NS (name server) records.

DNS zones are used to delegate authority for a portion of the DNS namespace to a specific organization or administrator. This allows for distributed management of the DNS system, as different organizations can manage their own zones without needing to coordinate with other organizations.

For example, a company may have a DNS zone for its internal network, which contains domain names and IP addresses for its internal servers and devices. The company may also have a separate DNS zone for its public-facing website, which contains domain names and IP addresses for the website's servers.

> Remember for your exam: A **forward lookup zone** is used to resolve domain names to IP addresses, while a **reverse lookup zone** is used to resolve IP addresses to domain names.

DNS stores entries in a **zone file**, which is a text file that contains the DNS records for the domain names within the zone. The zone file is typically stored on a DNS server and is used to provide information about the domain names and their corresponding IP addresses when a DNS query is made.

A zone is basically just a file that contains all the information about a specific domain and its subdomains. It includes records such as A records (which map domain names to IP addresses), MX records (which specify mail servers for the domain), and CNAME records (which provide aliases for domain names).

### Forward Zone

A **forward zone** is a type of DNS zone that is used to **resolve domain names to IP addresses**.

It contains DNS records like **A records** (which map domain names to IPv4 addresses) and **AAAA records** (which map domain names to IPv6 addresses), and **MX records** (which specify mail servers for the domain).

When a client makes a DNS query for a domain name, the DNS server looks up the forward zone to find the corresponding IP address and returns it to the client.

### Reverse Zone

A **reverse zone** is a type of DNS zone that is used to **resolve IP addresses to domain names**.

It contains **PTR records** (pointer records) that map IP addresses to domain names.

When a client makes a DNS query for an IP address, the DNS server looks up the reverse zone to find the corresponding domain name and returns it to the client.

This is basically the opposite of a forward zone, which resolves domain names to IP addresses. Reverse zones are often used for troubleshooting and network management purposes, as they allow administrators to identify the domain name associated with a specific IP address.

### Authoritative vs. Non-Authoritative

An **authoritative DNS server** is a DNS server that has the **final authority** to provide answers for a specific domain name. It is responsible for maintaining the DNS records for that domain and can provide authoritative responses to DNS queries. By final authority, we mean that the authoritative DNS server has the most up-to-date and accurate information about the domain name it is responsible for.

A **non-authoritative DNS server**, on the other hand, is a DNS server that does not have the final authority for a specific domain name. It may provide answers to DNS queries based on cached information or by forwarding the query to an authoritative DNS server. However, the information provided by a non-authoritative DNS server may not be as accurate or up-to-date as that provided by an authoritative DNS server.

In summary, an authoritative DNS server is the primary source of information for a specific domain name, while a non-authoritative DNS server may provide answers based on cached information or by forwarding queries to authoritative servers.

### Primary vs. Secondary DNS Zones

A **primary DNS zone** is a DNS zone that is the original source of information for a specific domain name. It is the authoritative source for that domain and contains the master copy of the DNS records. The primary DNS zone is responsible for maintaining and updating the DNS records for the domain. It allows changes to be made to the DNS records directly, and these changes are then propagated to secondary DNS zones.

A **secondary DNS zone**, on the other hand, is a copy of the primary DNS zone. It is used for redundancy and load balancing purposes. The secondary DNS zone receives updates from the primary DNS zone through a process called zone transfer. This means that any changes made to the primary DNS zone are automatically replicated to the secondary DNS zone, ensuring that both zones have the same information.

### DNSSEC

**DNSSEC (Domain Name System Security Extensions)** is a suite of extensions to the DNS protocol that provides **authentication and integrity** for DNS data. It is designed to protect against various types of attacks, such as cache poisoning and man-in-the-middle attacks, by ensuring that the DNS responses received by clients are authentic and have not been tampered with.

DNSSEC enhances DNS security by using digital signatures to verify the authenticity of DNS data. It verifies that the DNS responses received by clients are authentic and have not been tampered with. This is achieved through the use of public key cryptography, where each DNS zone has a pair of cryptographic keys: a private key used to sign the DNS records and a public key used to verify the signatures.

When a client receives a DNS response, it can use the public key to verify the digital signature attached to the response. If the signature is valid, it indicates that the response is authentic and has not been tampered with. If the signature is invalid or missing, it indicates that the response may have been compromised, and the client can choose to reject it.

It does not encrypt the DNS data, but it provides a way to verify the authenticity and integrity of the data, which helps to protect against various types of attacks on the DNS system. By implementing DNSSEC, organizations can enhance the security of their DNS infrastructure and protect their users from potential threats.

### DNS over HTTPS (DoH) and DNS over TLS (DoT)

**DNS over HTTPS (DoH)** and **DNS over TLS (DoT)** are two protocols that provide **encryption for DNS queries and responses**, enhancing the privacy and security of DNS communications. Both protocols aim to protect DNS traffic from eavesdropping and tampering by encrypting the communication between the client and the DNS server. It ensured that DNS queries and responses are encrypted, preventing third parties from intercepting, modifying, eavesdropping, or tampering with DNS traffic.

**DNS over HTTPS (DoH)** uses the HTTPS protocol to encrypt DNS queries and responses. It sends DNS requests over an encrypted HTTPS connection, making it difficult for attackers to intercept or modify the DNS traffic. DoH is designed to work with existing DNS infrastructure and can be used with any DNS server that supports the DoH protocol.

**DNS over TLS (DoT)**, on the other hand, uses the TLS protocol to encrypt DNS queries and responses. It establishes a secure TLS connection between the client and the DNS server, ensuring that all DNS traffic is encrypted and protected from eavesdropping and tampering. DoT is typically used in environments where there is a need for strong security and privacy, such as in corporate networks or when using public Wi-Fi networks.

Both DoH and DoT provide enhanced security for DNS communications, but they have different use cases and implementation requirements. DoH is more widely supported and can be used with existing DNS infrastructure, while DoT may require additional configuration and support from the DNS server. Ultimately, the choice between DoH and DoT depends on the specific needs and requirements of the network environment.
