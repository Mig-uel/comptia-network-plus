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

## Zero Trust (OB 1.8)

In traditional network security models, once a user or device is inside the network perimeter, they are often trusted by default. However, with the increasing complexity of modern networks and the rise of sophisticated cyber threats, this approach is no longer sufficient.

One way of preventing unauthorized access is by implementing a **Zero Trust** security model.

**Zero Trust** is a security model that operates on the principle of "never trust, always verify." In a Zero Trust architecture, no user or device is trusted by default, regardless of whether they are inside or outside the network perimeter. Instead, every access request is thoroughly verified before granting access to resources.

It requires **strict identity verification** for every person and device trying to access resources on a private network, regardless of whether they are located inside or outside the network perimeter.

Zero Trust minimizes attack surfaces by treating all network traffic as potentially hostile, thereby reducing the risk of data breaches and unauthorized access.

### Policy-Based Authentication

In a Zero Trust model, access to resources is granted based on **policy-based authentication**. This means that access decisions are made based on a set of predefined policies that consider various factors, such as the user's identity, device health, location, and the sensitivity of the requested resource. Access is granted only if the request meets the criteria defined in the policies.

Authentication policies can include multi-factor authentication (MFA), biometric verification, and behavioral analysis to ensure that only authorized users and devices can access specific resources.

### Authorization in Zero Trust Architecture

While authentication verifies the identity of users and devices, **authorization** determines what resources they are allowed to access once authenticated.

Authorization in a Zero Trust architecture is dynamic and strictly enforced before access to any resource is granted. This means that even after a user or device has been authenticated, they are only allowed to access resources that they have explicit permission for, based on their role, the context of the request, and the sensitivity of the resource.

This process is **context-aware**, taking into account the user's identity, location, device status, service or workload, data classification, and anomalies before granting access to resources.

Access to resources is granted on a **per-session basis**, meaning that each access request is evaluated independently, and permissions can be adjusted dynamically based on real-time conditions.

### Least Privilege Access

A key principle of Zero Trust is **least privilege access**, which means that users and devices are granted the minimum level of access necessary to perform their tasks. This reduces the risk of unauthorized access and limits the potential damage that can be caused by compromised accounts or devices.

## SASE/SSE (OB 1.8)

As organizations increasingly adopt cloud services and remote work, traditional network security models that rely on perimeter-based defenses are becoming less effective. To address these challenges, a new approach called **Secure Access Service Edge (SASE)** has emerged.

**Secure Access Service Edge (SASE)** and **Security Service Edge (SSE)** are modern network security frameworks that combine wide-area networking (WAN) capabilities with comprehensive security services delivered from the cloud. SASE integrates various security functions, such as secure web gateways (SWG), cloud access security brokers (CASB), firewall-as-a-service (FWaaS), and zero trust network access (ZTNA), into a single, unified service.

In other words, SASE and SSE provide secure access to applications and data regardless of the user's location, device, or network.

SASE integrates comprehensive WAN services and security functions directly into the network fabric, enabling secure and optimized access to applications and data from any location.

SSE focuses specifically on delivering security services from the cloud, providing protection for users and devices accessing cloud applications and services. On the other hand, SASE encompasses both networking and security services, offering a more holistic approach to secure access.

SSE focuses more on the security aspects, centralizing various security services like secure web gateways, cloud access security brokers, and zero trust network access into a unified cloud-delivered service.

These services are provided in the cloud to ensure secure access and data protection for users and devices, regardless of their location.

In other other words, SASE is a SaaS-based architecture that combines networking and security functions into a single cloud-delivered service, while SSE focuses specifically on delivering security services from the cloud. It also removes the need for VPNs by providing secure access directly from the cloud and removes the need for traditional on-premises security appliances.

## Infrastructure as Code (IaC) (OB 1.8)

In traditional network management, configuring and managing network devices often involves manual processes, which can be time-consuming, error-prone, and difficult to scale. To address these challenges, the concept of **Infrastructure as Code (IaC)** has been introduced.

**Infrastructure as Code (IaC)** is a practice that involves managing and provisioning computing infrastructure through machine-readable configuration files, rather than through manual processes. This approach allows for the automation of infrastructure deployment and management, making it easier to scale, replicate, and maintain network environments.

It enables IT infrastructure to be automatically managed, monitored, and provisioned through code, rather than through manual processes, improving efficiency and reducing the potential for human error.

### Playbooks, Templates, Reusable Tasks

IaC often utilizes **playbooks, templates, and reusable tasks** to define and manage infrastructure configurations.

- **Playbooks** are sets of instructions that define how to configure and deploy infrastructure components. They can include tasks such as installing software, configuring network settings, and deploying applications.
- **Templates** are pre-defined configurations that can be reused across multiple deployments. They provide a standardized way to define infrastructure components, making it easier to maintain consistency across environments.
- **Reusable tasks** are modular components that can be used across different playbooks and templates. This modularity allows for greater efficiency and consistency in infrastructure management.

### Configuration Drift and Compliance

IaC helps to mitigate **configuration drift**, which occurs when the actual state of infrastructure diverges from the desired state defined in code due to manual changes or updates. By using IaC, organizations can ensure that infrastructure configurations remain consistent and aligned with the defined code, reducing the risk of errors and inconsistencies.

IaC also facilitates **compliance** by enabling organizations to define and enforce infrastructure policies through code. This ensures that infrastructure configurations adhere to regulatory requirements and organizational standards, making it easier to audit and maintain compliance over time.

### Upgrades

With IaC, upgrading infrastructure components becomes more manageable. Since the infrastructure is defined in code, updates and upgrades can be automated through version-controlled scripts. This allows for consistent and repeatable upgrades across multiple environments, reducing downtime and minimizing the risk of errors during the upgrade process.

### Dynamic Inventories

IaC supports the use of **dynamic inventories**, which are automatically generated lists of infrastructure components based on the current state of the environment. Dynamic inventories allow for real-time tracking of resources, making it easier to manage and provision infrastructure as needed.

This flexibility is essential for managing environments that need to scale up or down based on demand, ensuring that resources are allocated efficiently and effectively.

### Source Control

Source control is a fundamental aspect of IaC, as it allows for versioning and tracking of infrastructure code. By storing infrastructure configurations in source control systems (like Git), organizations can maintain a history of changes, collaborate on code development, and roll back to previous versions if needed.

This practice enhances collaboration among team members, improves code quality, and ensures that infrastructure changes are well-documented and auditable.

### Central Repository

A central repository in source control systems acts as the **single source of truth** for all infrastructure code. It provides a centralized location where all team members can access, contribute to, and manage infrastructure configurations.

This centralization facilitates collaboration, ensures consistency across deployments, and simplifies the management of infrastructure code by providing a unified platform for version control and code review.

### Conflict Identification

Source control systems help identify conflicts that may arise when multiple team members make changes to the same infrastructure code simultaneously. These conflicts can lead to inconsistencies and errors if not properly managed.

By using source control, teams can detect and resolve conflicts early in the development process, ensuring that changes are integrated smoothly and that the infrastructure remains stable and reliable.

## IPv6 Mitigation

As the world transitions from IPv4 to IPv6, many organizations face challenges related to compatibility and interoperability between the two protocols. To address these challenges, various **IPv6 mitigation** techniques have been developed to facilitate the coexistence of IPv4 and IPv6 networks.

IPv6 addresses the limitations of IPv4, such as address exhaustion, by providing a vastly larger address space. However, IPv6 introduces several new concepts and changes that can complicate network management and interoperability with existing IPv4 infrastructure.

Transitioning to IPv6 involves compatibility strategies to ensure that both IPv4 and IPv6 can operate simultaneously during the migration period.

This is necessary because the internet will operate in a mixed IPv4 and IPv6 environment for the foreseeable future, requiring mechanisms to ensure seamless communication between the two protocols.

### Tunneling

**Tunneling** is a technique used to encapsulate IPv6 packets within IPv4 packets (or vice versa) to enable communication between IPv4 and IPv6 networks. This allows devices on an IPv6 network to communicate with devices on an IPv4 network by creating a "tunnel" through the IPv4 infrastructure.

Tunneling works by wrapping the IPv6 packet inside an IPv4 packet, allowing it to traverse IPv4 networks. Once the packet reaches its destination, it is decapsulated to retrieve the original IPv6 packet.

### Dual Stack

**Dual stack** is a strategy that involves configuring network devices to support both IPv4 and IPv6 protocols simultaneously. This allows devices to communicate using either protocol, depending on the capabilities of the destination device.

In a dual stack environment, devices can send and receive both IPv4 and IPv6 traffic, enabling a smooth transition between the two protocols. This approach allows for gradual migration to IPv6 while maintaining compatibility with existing IPv4 infrastructure.

### NAT64

**NAT64** is a network address translation technique that enables communication between IPv6-only and IPv4-only networks. It translates IPv6 addresses to IPv4 addresses and vice versa, allowing devices on an IPv6 network to access resources on an IPv4 network.

NAT64 works by using a translation gateway that performs the address translation, allowing IPv6 clients to communicate with IPv4 servers seamlessly. This technique is particularly useful in environments where IPv6 adoption is high, but access to IPv4 resources is still required.
