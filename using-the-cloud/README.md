# Using the Cloud

## Cloud Terminology

What is cloud computing? To keep it simple, cloud computing is basically using someone else's computer to do your work. Instead of running applications and storing data on your own local machine, you can use remote computers aka servers that are hosted on the internet to perform these tasks. This allows you to access your applications and data from anywhere with an internet connection, and it also provides scalability and flexibility.

For example, Amazon has a many giant buildings filled with servers that provide cloud computing services to millions of users around the world. When you use a cloud service, you're essentially renting space on those servers to run your applications and store your data.

### Network Functions Virtualization (NFV)

**Network Functions Virtualization (NFV)** is a concept in cloud computing that involves virtualizing network functions that traditionally ran on dedicated hardware. Instead of using physical devices like routers, firewalls, and load balancers, NFV allows these functions to be implemented as software running on virtual machines or containers in the cloud.

NFV involves the **decoupling of network functions from proprietary hardware devices** and running them as software instances on virtual machines or containers.

In cloud computing, NFV allows for **flexible deployment and management of network services** like firewalls, load balancers, and intrusion detection systems.

It **reduces the need for dedicated hardware** and enables **dynamic scaling and management of network resources** based on demand. This leads to **cost savings, improved agility, and faster deployment of network services** in cloud environments.

In a normal network setup, you might have physical devices like switches, routers, and firewalls that are responsible for specific functions.
With NFV, these functions can be virtualized and run on standard servers in the cloud, allowing for greater flexibility and scalability.
For example, instead of having a physical firewall device, you can run a virtual firewall as a software instance in the cloud, which can be easily scaled up or down based on traffic demands. This approach allows for more efficient use of resources and can lead to cost savings, as you only pay for the resources you use.
Additionally, NFV enables faster deployment of network services, as you can quickly spin up new instances of virtual network functions without the need for physical hardware installation.

### Virtual Private Cloud (VPC)

A **Virtual Private Cloud (VPC)** is a virtual network that you can create within a cloud provider's infrastructure. It allows you to have your own isolated network environment in the cloud, where you can launch and manage your resources such as virtual machines, databases, and storage.

A VPC is an **isolated network environment within a public cloud** designed to provide a similar level of segmentation, control and security as a traditional on-premises network. It allows you to create your own virtual network topology, including subnets, route tables, and network gateways, while still benefiting from the scalability and flexibility of the cloud.

Users can define their own IP address ranges, create and configure subnets, route tables, and set up network gateways to control the flow of traffic within their VPC. This allows for greater control over the network configuration and security of resources within the VPC.

Again, a VPC provides you with control over your network configuration, including IP address ranges, subnets, route tables, and network gateways. It allows you to create a secure and private environment for your applications and data in the cloud.

A VPC allows enterprises to run their cloud resources (like virtual machines, databases, and storage) in a logically isolated section of the cloud, providing enhanced security and control over their network environment. It also enables them to connect their on-premises data centers to the cloud securely using VPNs or dedicated connections, creating a hybrid cloud environment.

In summary, a Virtual Private Cloud (VPC) is a virtual network that provides an isolated and secure environment for running resources in the cloud, giving users control over their network configuration and enabling them to connect their on-premises data centers to the cloud securely.

### Network Security Groups and List

**Network Security Groups (NSGs)** are used to **control inbound and outbound traffic** to and from resources in a Virtual Private Cloud (VPC). They act as virtual firewalls that allow you to define rules to permit or deny traffic based on source and destination IP addresses, ports, and protocols.

Similar to network security groups, **Network Security Lists (NSLs)** are also used for **managing and securing network traffic** in a VPC. However, NSLs are typically associated with subnets rather than individual resources. They allow you to define rules that apply to all resources within a subnet, providing a broader level of security control.

They generally provide **stateful or stateless traffic filtering on a subnet level**, enabling more granular control over network traffic between subnets and to/from the internet.

> NSLs can be used to enforce security policies across multiple resources within a subnet, while NSGs are typically used for more specific control over individual resources.

Both NSGs and NSLs act as **virtual firewalls** for associated instances and subnets, allowing you to define rules that control the flow of traffic based on source and destination IP addresses, ports, and protocols. They are essential components for securing resources in a VPC and ensuring that only authorized traffic is allowed to reach your applications and data.

> Remember, NSGs are typically associated with individual resources like virtual machines, while NSLs are associated with subnets. They operate at different levels of the network hierarchy, providing different scopes of control over network traffic. NSGs provide more granular control over specific resources, while NSLs provide broader control over all resources within a subnet.

To give an analogy, think of NSGs as security guards stationed at the entrance of a building, checking the credentials of each person trying to enter. They can allow or deny access based on specific rules. On the other hand, NSLs are like security policies that apply to an entire neighborhood, setting rules for who can enter or exit the area. Both are important for maintaining security, but they operate at different levels of granularity.

In summary, Network Security Groups (NSGs) and Network Security Lists (NSLs) are both essential components for securing resources in a Virtual Private Cloud (VPC). NSGs provide granular control over individual resources, while NSLs provide broader control over all resources within a subnet. They work together to ensure that only authorized traffic is allowed to reach your applications and data in the cloud.

### Internet Gateways

An **Internet Gateway** is a component in cloud computing that allows communication between resources in a Virtual Private Cloud (VPC) and the internet. It serves as a bridge between the VPC and the outside world, enabling resources within the VPC to send and receive traffic to and from the internet.

An Internet Gateway serves as a bridge between a company's VPC and the public internet.
It enables internet access for the resources within the VPC, allowing them to communicate with external services and users.

This gateway facilitates communications between instances in the VPC and the internet, allowing for activities such as web browsing, API calls, and data transfer. It also provides a route for incoming traffic from the internet to reach resources within the VPC, such as web servers or applications.

It is a horizontally scaled, redundant, and highly available component that provides a target in your VPC route tables for internet-routable traffic.

When you create an Internet Gateway, it is associated with your VPC, and you can then update your route tables to direct traffic destined for the internet to the Internet Gateway.

In summary, an Internet Gateway is a crucial component in cloud computing that enables communication between resources in a Virtual Private Cloud (VPC) and the internet. It allows resources within the VPC to send and receive traffic to and from the internet, facilitating activities such as web browsing, API calls, and data transfer. It also provides a route for incoming traffic from the internet to reach resources within the VPC, making it an essential part of any cloud infrastructure.

### NAT Gateways

Another thing you can use in a VPC is a **NAT Gateway**. A NAT Gateway, or Network Address Translation Gateway, is a service that allows instances in a private subnet to connect to the internet or other AWS services, but prevents the internet from initiating connections with those instances.

A NAT Gateway **allows instances in a private subnet to connect to the internet** or other external services while preventing inbound traffic from the internet to those instances. It acts as a bridge between the private subnet and the internet, translating the private IP addresses of the instances to a public IP address for outbound traffic.

This is particularly useful for instances that need to access the internet for updates, patches, or to access external APIs, but do not require inbound internet access for security reasons.

Don't we have NAT at home? Yes, we do. A NAT Gateway in the cloud serves a similar purpose to a NAT device in a home network. In a home network, a NAT device allows multiple devices to share a single public IP address when accessing the internet. Similarly, in a VPC, a NAT Gateway allows instances in a private subnet to share a single public IP address for outbound internet access.

In summary, a NAT Gateway is a service that allows instances in a private subnet to connect to the internet or other external services while preventing inbound traffic from the internet to those instances. It acts as a bridge between the private subnet and the internet, translating private IP addresses to public IP addresses for outbound traffic. This is particularly useful for instances that need to access the internet for updates or external APIs but do not require inbound internet access for security reasons.

### Cloud Gateways

So far, we've talked about Internet Gateways and NAT Gateways. Remember, an Internet Gateway allows communication between resources in a VPC and the internet, while a NAT Gateway allows instances in a private subnet to connect to the internet while preventing inbound traffic from the internet.

In your organization, you are not going to use just one cloud provider. You might have resources in multiple cloud providers, such as AWS, Azure, and Google Cloud. In this case, you would need a way to connect these different cloud environments together. This is where **Cloud Gateways** come into play.

What we need is a centralized gateway that can connect multiple cloud environments together, allowing for seamless communication between resources in different clouds. This would sit between the different cloud providers and your workstations, allowing you to access resources across all your cloud environments from a single point of entry.

Cloud gateways serve as a intermediary (or bridge) devices or services that **connect different cloud environments together**, including privater data centers or other cloud services.

They facilitate communication, data transfer, and management between these dissimilar environments, allowing for seamless integration and interoperability.

The whole point of a cloud gateway is to provide a single point of access and control for resources across multiple cloud environments, enabling organizations to manage their multi-cloud infrastructure more efficiently and effectively. This can help reduce complexity, improve security, and enhance the overall performance of their cloud resources.

In summary, cloud gateways are intermediary devices or services that connect different cloud environments together, allowing for seamless communication and integration between them. They provide a single point of access and control for resources across multiple cloud environments, helping organizations manage their multi-cloud infrastructure more efficiently and effectively.

### Cloud Connectivity Options

Cloud connectivity options refer to the various **methods through which data and applications can connect to and interact with cloud environments**.

These options are crucial for ensuring efficient, secure, and reliable access to cloud resources from different locations and devices.

Some common cloud connectivity options include:

1. **Virtual Private Network (VPN)**: A VPN allows users to securely connect to a cloud environment over the internet by creating an encrypted tunnel between the user's device and the cloud provider's network. VPNs are used to establish secure connections between remote users or remote sites and an organization's private cloud resources. It allows for secure data transmission across public networks as if the user were **directly connected** to the private network.

2. **Private-Direct Connection to Cloud Provider**: A private-direct connection, such as AWS Direct Connect or Azure ExpressRoute, refers to a **dedicated network link** between an organization's on-premises infrastructure and the cloud provider's network. This type of connection provides a more reliable and consistent network experience compared to VPNs, as it bypasses the public internet and offers higher bandwidth and lower latency.
   - This direct connection **bypasses the public internet**, providing a more reliable, secure, and faster connection for accessing cloud resources.
   - It is ideal for organizations that require high performance and low latency when accessing cloud services, such as for data transfer, hybrid cloud deployments, or connecting to cloud-based applications.
