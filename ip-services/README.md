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
