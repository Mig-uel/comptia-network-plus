# Modern Network Environments

## Software Defined Networking (SDN) (OB 1.8)

In today's large networks with many many routers and switches, it can become very difficult to manage and configure all the devices individually.

In order to solve this problem, Software Defined Networking (SDN) was developed. SDN is a network architecture approach that enables the network to be intelligently and centrally controlled, or 'programmed,' using software applications. This is done by separating the network's control plane (which makes decisions about where traffic is sent) from the data plane (which forwards traffic to its destination).

**Software-defined networking (SDN)** is an innovative networking approach that decouples the network control and forwarding functions, enabling network management through software applications. This separation allows for more flexible and efficient network management, as administrators can programmatically control network behavior without needing to configure individual devices manually.

Something related to SDN is SD-WAN (Software Defined Wide Area Network).

### SD-WAN

**Software-Defined Wide Area Network (SD-WAN)** is a specific application of SDN technology applied to wide area networks (WANs), which are used to connect enterprise networks - including branch offices and data centers - over large geographic distances. SD-WAN simplifies the management and operation of a WAN by separating the networking hardware from its control mechanism. This allows for more efficient use of network resources, improved performance, and enhanced security.

### SDN Functionality

SDNs (Software Defined Networks) separate the network architecture into **three distinct planes (layers)**:

1. **Data Plane (Forwarding Plane)**: This layer is responsible for the actual movement of packets through the network. It consists of network devices like switches and routers that forward data based on rules set by the control plane.
2. **Control Plane**: This layer makes decisions about where traffic is sent. It contains the network's intelligence and logic, often implemented in a centralized controller that communicates with the data plane devices to manage traffic flow.
3. **Application Plane**: This layer consists of the applications and services that communicate their network requirements to the control plane. It allows for the development of network applications that can dynamically adjust network behavior based on real-time needs.

Basically, a software is used to control the entire network, instead of configuring each device individually. The control plane is in charge of managing the data plane, while the application plane interacts with the control plane to implement network policies and services.

### Central Policy Management

One of the key benefits of SDN is **centralized policy management**. In traditional networks, policies (like security rules, quality of service settings, etc.) have to be configured on each individual device.

With SDNs, policies can be defined centrally in the control plane and automatically propagated to all relevant devices in the data plane. This makes it much easier to implement and enforce network-wide policies consistently.

**Centralized management** enables network admins to set policies that manage and configure all SDN devices across the network from a single interface, improving efficiency and reducing the potential for configuration errors.

### Application Aware

SDNs are **application-aware**, meaning they can intelligently manage network resources based on the specific needs of applications. For example, an SDN can prioritize traffic for a video conferencing application to ensure smooth performance, while deprioritizing less critical traffic. This dynamic adjustment helps optimize network performance and enhances the user experience.

### Zero-Touch Provisioning

**Zero-touch provisioning** is a feature of SDN that allows new network devices to be automatically configured and integrated into the network without manual intervention. When a new device is added, it can connect to the SDN controller, which then pushes the necessary configurations and policies to the device. This significantly reduces the time and effort required to deploy new hardware in the network.

This feature allows for the **remote deployment of network devices** with minimal manual intervention.

Network devices can automatically obtain their configuration from a central controller when they are connected to the network, simplifying the setup process and reducing the potential for human error.

### Transport Agnostic

SDNs are **transport agnostic**, meaning they can operate over various types of network transport technologies (like Ethernet, MPLS, Wi-Fi, etc.) without being tied to a specific one. This flexibility allows organizations to choose the most appropriate transport technology for their needs while still benefiting from the centralized control and management provided by SDN.

This means that SDN can work over different types of network infrastructures without being dependent on any specific transport technology, allowing for greater flexibility and adaptability in network design.

## VXLAN (OB 1.9)

When you are working with the cloud or large data centers, you may need to create many isolated networks for different customers or different departments within an organization. The service that one customer or department uses should not be accessible by another customer or department. What needs to be done is separate these networks from each other while still allowing them to share the same physical infrastructure.

We typically use VLANs (Virtual Local Area Networks) to separate networks within a physical network. However, VLANs have a limitation of 4096 unique IDs, which can be insufficient in large-scale environments like data centers or cloud infrastructures.

To overcome this limitation, we use VXLAN (Virtual Extensible LAN).

**VXLAN (Virtual Extensible LAN)** is a **network virtualization technology** that allows for the creation of **logical (virtual) Layer 2 networks** over a Layer 3 (IP) network infrastructure. It extends Layer 2 segments over an underlying Layer 3 network, enabling the creation of large numbers of isolated virtual networks.

### Layer 2 Encapsulation

VXLAN encapsulates Layer 2 Ethernet frames within Layer 3 UDP packets. This encapsulation allows VXLAN to transport Layer 2 traffic over a Layer 3 network, effectively creating a virtual Layer 2 network that can span across different physical locations.

This encapsulation allows VXLAN to create a logical network for virtual machines (VMs) that can be spread across multiple physical servers and data centers, while still maintaining the appearance of being on the same Layer 2 network.

### DCI (Data Center Interconnect)

VXLAN is commonly used in **Data Center Interconnect (DCI)** scenarios, where multiple data centers need to be connected while maintaining isolated networks for different tenants or departments. VXLAN allows for the extension of Layer 2 networks across geographically dispersed data centers, enabling seamless connectivity for virtual machines and applications.
