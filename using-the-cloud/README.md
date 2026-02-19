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

## Cloud Deployment Models (OB 1.3)

When it comes to cloud computing, you have to know how we deploy our applications and services in the cloud.

There are three main cloud deployment models: **Public Cloud**, **Private Cloud**, and **Hybrid Cloud**.

### Deployment Models

**Deployment models** in networking and cloud computing refer to the different ways in which network resources and services can be deployed and accessed. These models define how network infrastructure is set up, managed, and utilized to provide connectivity and services to users.

**Public Cloud**: In a public cloud deployment model, the cloud infrastructure is owned and operated by a third-party cloud service provider, and resources are shared among multiple customers. Users can access and utilize these resources over the internet on a pay-as-you-go basis. Examples of public cloud providers include Amazon Web Services (AWS), Microsoft Azure, and Google Cloud Platform (GCP).

- Multi-tenant environment where resources are shared among multiple customers.
- Hardware resources are shared with other customers, but each customer's data and applications are isolated and secure.
- Most affordable and least secure option, as resources are shared and managed by a third-party provider.

**Private Cloud**: In a private cloud deployment model, the cloud infrastructure is dedicated to a single organization and is not shared with other customers. The organization can either host the private cloud on-premises or use a third-party provider to manage it. Private clouds offer greater control, security, and customization options compared to public clouds.

- Single-tenant environment where resources are dedicated to a single organization.
- No hardware resources are shared with other customers, providing greater control and security.
- First-party or third-party management options available, allowing for more customization and control over the cloud environment.
- Most secure and expensive option, as resources are dedicated and managed by the organization or a trusted provider.
- Can be hosted by the organization on-premises or by a third-party provider.

**Community Cloud**: A community cloud is a cloud deployment model where the cloud infrastructure is shared by several organizations that have common concerns, such as security requirements, compliance needs, or specific industry regulations. The community cloud can be managed by the organizations themselves or by a third-party provider. It allows for collaboration and resource sharing among the participating organizations while maintaining a level of isolation from other users.

- Shared environment where resources are shared among a specific community of users with common concerns.
- Can be managed by the organizations themselves or by a third-party provider.
- Provides a balance between the cost-effectiveness of public clouds and the security and control of private clouds.
- Suitable for organizations that have similar requirements and want to collaborate while maintaining some level of isolation from other users.

**Hybrid Cloud**: A hybrid cloud deployment model combines elements of both public and private clouds, allowing organizations to leverage the benefits of both. In a hybrid cloud, an organization can keep sensitive data and critical applications in a private cloud while utilizing the public cloud for less sensitive workloads or for scalability. This model provides flexibility and allows organizations to optimize their cloud resources based on their specific needs.

- Combines elements of both public and private clouds also being hosted on-premises or by a third-party provider.
- Bounded together using standardized or proprietary technology that enables data and application portability.
- Enables data and application portability, allowing organizations to move workloads between public and private clouds as needed.
  - i.e., load balancing, failover, or data migration.

In summary, cloud deployment models define how network resources and services are deployed and accessed in the cloud. Public clouds offer shared resources and are cost-effective but less secure, while private clouds provide dedicated resources and greater control at a higher cost. Community clouds allow for collaboration among organizations with common concerns, while hybrid clouds combine elements of both public and private clouds to provide flexibility and optimize resource utilization based on specific needs.

## Cloud Service Models (OB 1.3)

Cloud service models refer to the different levels of abstraction and responsibility in cloud computing.

**Service models** in cloud computing refer to the different levels of abstraction and responsibility that cloud providers offer to customers. These models define how cloud services are delivered and consumed, and they determine the level of control and management that customers have over their resources.

### Software as a Service (SaaS)

**Software as a Service (SaaS)** is a cloud service model where applications are hosted and managed by a third-party provider and made available to customers over the internet. In this model, customers do not have to worry about the underlying infrastructure, software updates, or maintenance, as these responsibilities are handled by the service provider.

Examples of SaaS include email services like Gmail, customer relationship management (CRM) software like Salesforce, and collaboration tools like Microsoft Office 365.

It allows users to access software applications on a subscription basis, providing a convenient and cost-effective way to use software without the need for installation or maintenance.

### Infrastructure as a Service (IaaS)

Let's say you develop your own in-house custom application and you want to deploy it but you don't want to manage the underlying infrastructure. In this case, you can use **Infrastructure as a Service (IaaS)**. IaaS is a cloud service model where customers can rent virtualized computing resources such as servers, storage, and networking from a cloud provider. Customers have control over the operating systems, applications, and data running on the infrastructure, while the cloud provider manages the underlying hardware and virtualization.

Examples of IaaS providers include Amazon Web Services (AWS) EC2, Microsoft Azure Virtual Machines, and Google Cloud Compute Engine.

IaaS allows customers to quickly provision and scale resources as needed, providing flexibility and cost savings compared to traditional on-premises infrastructure. It is ideal for organizations that want to have more control over their infrastructure while still benefiting from the scalability and flexibility of the cloud.

### Platform as a Service (PaaS)

What if you want to develop and deploy your application without worrying about the underlying infrastructure or the software stack? This is where **Platform as a Service (PaaS)** comes in. PaaS is a cloud service model that provides a platform for developers to build, deploy, and manage applications without having to worry about the underlying infrastructure or software stack. In this model, the cloud provider manages the infrastructure, operating system, and runtime environment, while developers focus on writing code and developing applications.

Examples of PaaS providers include Heroku, Google App Engine, and Microsoft Azure App Service.

This model provides a higher level of abstraction compared to IaaS, allowing developers to focus on application development rather than infrastructure management. PaaS is ideal for developers who want to quickly build and deploy applications without the need for extensive infrastructure management or configuration. It also provides features such as scalability, load balancing, and integrated development tools, making it easier for developers to create and manage their applications in the cloud.

In summary, cloud service models define the different levels of abstraction and responsibility in cloud computing. SaaS provides fully managed applications, IaaS offers virtualized infrastructure resources, and PaaS provides a platform for application development and deployment. Each model offers different levels of control and management, allowing organizations to choose the one that best fits their needs and requirements.

### Service Models Comparison

|                       | SaaS     | PaaS     | IaaS     |
| --------------------- | -------- | -------- | -------- |
| User                  | Customer | Customer | Customer |
| Application           | Provider | Customer | Customer |
| Operating System      | Provider | Provider | Customer |
| Hardware              | Provider | Provider | Provider |
| Network               | Provider | Provider | Provider |
| Facility              | Provider | Provider | Provider |
| Regulatory Compliance | Provider | Provider | Customer |
