# Network Monitoring

## Simple Network Management Protocol (SNMP) (OB 3.2)

As a network administrator, you are responsible for monitoring and managing the network devices in your organization. What if you have hundreds or even thousands of devices to monitor? Manually checking each device would be time-consuming and inefficient.

What if we could have one dedicated system that can monitor all the devices in the network and alert us when something goes wrong? We can configure network devices to send alerts to a central monitoring system when they encounter issues. This way, we can quickly identify and address problems before they escalate.

### Simple Network Management Protocol

**Simple Network Management Protocol (SNMP)** is a widely used protocol for monitoring and managing network devices. It allows network administrators to collect information about the status and performance of devices such as routers, switches, servers, and printers.

It operates on the **application layer** of the OSI model and uses a client-server architecture. The SNMP manager (client) communicates with SNMP agents (servers) running on network devices to retrieve information and receive alerts. It provides a standardized way to monitor and manage network devices, making it easier for administrators to maintain the health of their networks.

### SNMP Traps

**SNMP traps** are a mechanism used by SNMP agents to send **unsolicited notifications** to the SNMP manager when certain events occur on the network device. These events can include things like a device going down, a high CPU usage alert, or a configuration change.

When an SNMP agent detects an event that requires attention, it generates a trap message and sends it to the SNMP manager. The manager then processes the trap and can take appropriate action, such as logging the event, sending an email notification, or triggering an automated response.

By unsolicited notifications, we mean that the SNMP agent does not wait for a request from the SNMP manager to send the trap. Instead, it proactively sends the trap when it detects an event that meets certain criteria. This allows network administrators to be alerted in real-time about issues that may require immediate attention.

### Management Information Bases (MIBs)

**Management Information Bases (MIBs)** are databases that define the structure of the information that can be managed using SNMP. They contain a collection of objects that represent various aspects of network devices, such as their configuration, performance metrics, and status.

MIBs contain information about the objects that can be monitored and managed using SNMP. Each object in a MIB is identified by a unique **Object Identifier (OID)**, which is a hierarchical identifier that specifies the location of the object within the MIB.

### SNMP Versions

SNMP has evolved over time, and there are currently three main versions in use:

1. **SNMPv1**: The original version of SNMP, which provides basic monitoring and management capabilities. It uses a simple community string for authentication and is not very secure. This version is not in use anymore due to its security vulnerabilities.

2. **SNMPv2c**: An improved version of SNMP that provides better performance and additional features, such as bulk retrieval of data. It still uses community strings for authentication and is not very secure. It lacks robust security features, relying on plain text community strings for authentication, which can be easily intercepted.

3. **SNMPv3**: The most secure version of SNMP, which provides authentication and encryption for communication between the SNMP manager and agents. It uses user-based security models (USM) to provide strong authentication and privacy for SNMP messages. This version is recommended for use in modern networks due to its enhanced security features.

### Community Strings in SNMP

**Community strings** are used in SNMP to provide a simple form of authentication between the SNMP manager and agents. They act as passwords that control access to the SNMP data on network devices. Community strings are typically configured on both the SNMP manager and the SNMP agents.

There are two common types of community strings:

- **Public community string**: This is a read-only community string that allows the SNMP manager to retrieve information from the SNMP agent but does not allow any modifications to the device's configuration. It is often used for monitoring purposes.
- **Private community string**: This is a read-write community string that allows the SNMP manager to both retrieve information and modify the configuration of the SNMP agent. It should be kept secure and only shared with trusted administrators.

When you configure a device as an SNMP agent, you will typically set up both a public and private community string. The public community string is used for monitoring and retrieving information, while the private community string is used for making changes to the device's configuration.

### Authentication in SNMPv3

SNMPv3 introduces a more robust authentication mechanism compared to the previous versions. It uses user-based security models (USM) to provide strong authentication and privacy for SNMP messages. It verifies the identity of the source (SNMP manager) and destination (SNMP agent) of the SNMP messages, ensuring that only authorized users can access the SNMP data.

## Capturing Packets (OB 3.2)

As a network administrator, one of the most fundamental thing you must learn is how to capture packets on the network and analyze them. Packet capturing is a crucial skill for troubleshooting network issues, monitoring network traffic, and ensuring the security of your network.

### Flow Data

**Flow data** is a type of network data that provides information about the traffic flowing through a network. It includes details such as the **source and destination IP addresses, port numbers, protocol types, and the amount of data transferred**.

It is typically collected by network devices such as routers and switches, which can generate flow records based on the traffic they observe. Flow data is useful for understanding network usage patterns, bandwidth utilization, and identifying potential security threats. It can also help network administrators optimize network performance and plan for future capacity needs.

### Packet Capturing

**Packet capturing (pcap)** is the process of **intercepting and logging** network traffic that passes through a network interface. It allows network administrators to analyze the contents of packets, including headers and payloads, to troubleshoot issues, monitor performance, and detect security threats.

As a diagnostic tool, packet capturing is invaluable for understanding how data flows through a network and identifying potential problems. By capturing packets, administrators can gain insights into the behavior of applications, protocols, and devices on the network.
