# IP Addressing

## Convert Decimal to Binary (OB 1.7)

To convert a decimal number to binary, follow these steps:

1. Divide the decimal number by 2.
2. Record the quotient and the remainder.
3. Continue dividing the quotient by 2 until the quotient is 0.
4. The binary representation is obtained by reading the remainders in reverse order (from last to first).

### Example

Convert the decimal number 13 to binary:

1. 13 ÷ 2 = 6, remainder 1
2. 6 ÷ 2 = 3, remainder 0
3. 3 ÷ 2 = 1, remainder 1
4. 1 ÷ 2 = 0, remainder 1

Reading the remainders in reverse order gives us: 1101
Thus, the binary representation of the decimal number 13 is **1101**.

## Structure of an IP Address (OB 1.7)

> Note: 8 bits is a number between 0 and 255.

Let's talk about the structure of an IP address, specifically IPv4 addresses.

Let's represent an IPv4 address as so:

```
x.x.x.x
```

Where each `x` represents 8 bits (also known as an octet). Therefore, an IPv4 address consists of 4 octets, making a total of 32 bits.

To add more, that means that each `x` can have a value between 0 and 255 (since 2^8 = 256 possible values, ranging from 0 to 255).

An IPv4 address is 32 bits long, divided into four octets of 8 bits each. Each octet can represent a decimal value from 0 to 255.

The first octet can indicate the class of the IP address (A, B, C, D, or E), which determines the network and host portions of the address. The remaining octets are used to identify the specific network and host within that network. Also, the first octet can only go from 0 to 223 for standard unicast addresses.

## Classes of IP Addresses (OB 1.7)

> History: IP addressing is assigned and allocated by an organization called IANA (Internet Assigned Numbers Authority). This organization allocates large blocks of IP addresses to regional registries, which then distribute them to ISPs and organizations.

IP addresses are divided into different classes based on their leading bits and the range of the first octet. The main classes are A, B, C, D, and E.

| Class | 1st Octet Range | Number of Hosts | Subnet Mask   | Usage           |
| ----- | --------------- | --------------- | ------------- | --------------- |
| A     | 0 - 126         | 16.7 million    | 255.0.0.0     | Large networks  |
| B     | 128 - 191       | 65,534          | 255.255.0.0   | Medium networks |
| C     | 192 - 223       | 254             | 255.255.255.0 | Small networks  |

> A subnet mask is used to divide an IP address into network and host portions. It helps determine which part of the IP address refers to the network and which part refers to the host within that network.

Let's look at an example and try to classify the IP address:

`21.6.10.4`

1. Is this a valid IP address?
   - Yes, because each octet is between 0 and 255 and the first octet is between 0 and 223.
2. What class is this IP address?
   - Class A, because the first octet (21) is between 0 and 126.
3. What is the subnet mask for this IP address?
   - The subnet mask is: `255.0.0.0`
4. How many hosts can this network support?
   - This network can support 16.7 million hosts.
5. What is the network portion of this IP address?
   - The network portion is `21.0.0.0`
6. What is the host portion of this IP address?
   - The host portion is `0.6.10.4`

`96.4.100.254`

1. Is this a valid IP address?
   - Yes, because each octet is between 0 and 255 and the first octet is between 0 and 223.
2. What class is this IP address?
   - Class A, because the first octet (96) is between 0 and 126.
3. What is the subnet mask for this IP address?
   - The subnet mask is: `255.0.0.0`
4. How many hosts can this network support?
   - This network can support 16.7 million hosts.
5. What is the network portion of this IP address?
   - The network portion is `96.0.0.0`
6. What is the host portion of this IP address?
   - The host portion is `0.4.100.254`

`160.10.4.100`

1. Is this a valid IP address?
   - Yes, because each octet is between 0 and 255 and the first octet is between 0 and 223.
2. What class is this IP address?
   - Class B, because the first octet (160) is between 128 and 191.
3. What is the subnet mask for this IP address?
   - The subnet mask is: `255.255.0.0`
4. How many hosts can this network support?
   - This network can support 65,534 hosts.
5. What is the network portion of this IP address?
   - The network portion is `160.10.0.0`
6. What is the host portion of this IP address?
   - The host portion is `0.4.100`

An easy way to remember subnet masks for classes A, B, and C is:

- Class A: The letter A has 1 letter, so the subnet mask has 1 octet of 255: `255.0.0.0`
- Class B: The letter B has 2 letters, so the subnet mask has 2 octets of 255: `255.255.0.0`
- Class C: The letter C has 3 letters, so the subnet mask has 3 octets of 255: `255.255.255.0`

## How Many Computers Are in Each Network? (OB 1.7)

> Note: A subnet mask determines which portion of an IP address is the network part and which part is the host part. It also determines how many hosts (computers) can be in that network.

Let's look at an IPv4 address with its subnet mask:

IP Address:

```
192.168.30.10
```

Subnet Mask:

```
255.255.255.0
```

The network ID is determined by the IP address and the subnet mask. The simplest way to find the network ID is to compare the IP address and subnet mask octet by octet. Wherever there is a `255` in the subnet mask, we take the corresponding octet from the IP address for the network ID. Wherever there is a `0` in the subnet mask, we replace the corresponding octet in the IP address with a `0` for the network ID.

So, for the given IP address and subnet mask:

- First octet: 192 (from IP address, since subnet mask is 255)
- Second octet: 168 (from IP address, since subnet mask is 255)
- Third octet: 30 (from IP address, since subnet mask is 255)
- Fourth octet: 0 (replaced with 0, since subnet mask is 0)

Thus, the network ID is:

```
192.168.30.0
```

A network ID identifies a specific network and is used to route traffic within that network. Computers within the same network ID can communicate directly with each other.

Another example with two IP addresses and their subnet masks:

IP Address with Subnet Mask 1:

```
192.168.40.32 | 255.255.255.0
```

IP Address with Subnet Mask 2:

```
192.168.40.220 | 255.255.255.0
```

Can these two IP addresses communicate directly with each other? First let's find the network ID for both IP addresses.

For the first IP address:

- First octet: 192 (from IP address, since subnet mask is 255)
- Second octet: 168 (from IP address, since subnet mask is 255)
- Third octet: 40 (from IP address, since subnet mask is 255)
- Fourth octet: 0 (replaced with 0, since subnet mask is 0)

Thus, the network ID for the first IP address is:

```
192.168.40.0
```

For the second IP address:

- First octet: 192 (from IP address, since subnet mask is 255)
- Second octet: 168 (from IP address, since subnet mask is 255)
- Third octet: 40 (from IP address, since subnet mask is 255)
- Fourth octet: 0 (replaced with 0, since subnet mask is 0)

Thus, the network ID for the second IP address is:

```
192.168.40.0
```

Since both IP addresses have the same network ID (`192.168.40.0`), they can communicate directly with each other within the same network.

---

Let's see another example:

IP Address with Subnet Mask 1:

```
120.10.40.60 | 255.0.0.0
```

It's network ID is:

```
120.0.0.0
```

IP Address with Subnet Mask 2:

```
120.180.60.100 | 255.0.0.0
```

It's network ID is:

```
120.0.0.0
```

Since both IP addresses have the same network ID (`120.0.0.0`), they can communicate directly with each other within the same network. Remember that the subnet mask determines which portion of the IP address is the network part and which part is the host part. In this case, both IP addresses belong to the same network because their network IDs are identical.

---

Let's try a class B example:

IP Address with Subnet Mask 1:

```
180.16.32.100 | 255.255.0.0
```

It's network ID is:

```
180.16.0.0
```

IP Address with Subnet Mask 2:

```
180.17.19.100 | 255.255.0.0
```

It's network ID is:

```
180.17.0.0
```

Since both IP addresses have different network IDs (`180.16.0.0` and `180.17.0.0`), they cannot communicate directly with each other within the same network.

## Assigning IP Addresses Practice (OB 1.7)

In order to make two computers that are in different IP networks communicate with each other, we need to use a router. Recall that a router works at the network layer (Layer 3) of the OSI model and is responsible for forwarding data packets between different networks. It uses IP addresses to determine the best path for data to travel from the source to the destination.

When two computers are in different IP networks, they cannot communicate directly because their IP addresses belong to different network segments. The router acts as an intermediary that connects these different networks.

A router is a device that connects dissimilar networks together and routes data packets between them. It examines the destination IP address of each packet and determines the best path for it to reach its destination. In contrast, a switch operates at the data link layer (Layer 2) and is used to connect devices within the same network segment. Switches use MAC addresses to forward data frames within the same network.

In other related news, a default gateway is the IP address of the router that connects a local network to other networks, including the internet. It serves as an access point for devices within the local network to communicate with devices outside of that network. When a device wants to send data to a destination outside its own network, it sends the data to the default gateway (router), which then forwards it to the appropriate destination.

## What are the Private IP Addresses? (OB 1.7)

> History: When IP addresses were first being allocated, they realized that the number of available IP addresses was limited. To address this issue, they designated certain ranges of IP addresses as private, which can be used within local networks without being routable on the public internet. These private IP addresses help conserve the limited pool of public IP addresses.

Private IP addresses are IP addresses that you can assign to devices within your own private network, such as your home or office network. These addresses are not routable on the public internet, meaning they cannot be accessed directly from outside your local network.

The ranges of private IP addresses are defined by the Internet Assigned Numbers Authority (IANA) and are as follows:

| Class | Private IP Address Range      |
| ----- | ----------------------------- |
| A     | 10.0.0.0 - 10.255.255.255     |
| B     | 172.16.0.0 - 172.31.255.255   |
| C     | 192.168.0.0 - 192.168.255.255 |

Devices within a private network can communicate with each other using these private IP addresses. However, to access the internet, devices with private IP addresses typically use a router with Network Address Translation (NAT) to translate their private IP addresses to a public IP address.

Using private IP addresses helps conserve the limited pool of public IP addresses and provides an additional layer of security for devices within the private network.

## What is CIDR? (OB 1.7)

CIDR stands for Classless Inter-Domain Routing. It is a method for allocating IP addresses and routing IP packets. CIDR was introduced to improve the efficiency of IP address allocation and to slow the exhaustion of IPv4 addresses.

CIDR allows for more flexible allocation of IP addresses compared to the traditional class-based system (Classes A, B, and C). Instead of being restricted to fixed subnet masks based on classes, CIDR uses variable-length subnet masking (VLSM), which allows network administrators to allocate IP addresses based on the actual number of hosts needed in a network.

You may see some IP addresses written in CIDR notation, which includes the IP address followed by a slash and a number:

```
192.168.30.4/24
```

In this example, `/24` indicates that the first 24 bits of the IP address are used for the network portion, and the remaining bits are used for the host portion. This corresponds to a subnet mask of `255.255.255.0`. (Recall that each octet is 8 bits, so `/24` means the first three octets (8 + 8 + 8 = 24) are for the network.)

CIDR notation allows for more efficient use of IP addresses by enabling the creation of subnets that can accommodate varying numbers of hosts, reducing waste and improving routing efficiency on the internet.

## Other Types of IP Addresses (OB 1.7)

In the world of IT, there are basically three ways to communicate using IP addresses: unicast, multicast, and broadcast.

- **Unicast**: This is the most common type of IP communication. In unicast, data is sent from one specific source to one specific destination. For example, when you visit a website, your computer sends a unicast request to the web server's IP address, and the server responds directly to your computer's IP address.

  - Public IP: These are IP addresses that are assigned to devices that are directly connected to the internet. They are unique across the entire internet and can be accessed from anywhere in the world.
  - Private IP: These are IP addresses that are used within private networks (like home or office networks) and are not routable on the public internet. They allow devices within the same network to communicate with each other.
  - APIPA: Stands for **Automatic Private IP Addressing**. This is a feature in some operating systems that automatically assigns a private IP address (from the range `169.254.0.1` to `169.254.255.254`) when a device is unable to obtain an IP address from a DHCP server.

- **Multicast**: In multicast communication, data is sent from one source to multiple specific destinations. This is often used for streaming media or online gaming, where the same data needs to be sent to multiple users simultaneously.

  - IP Range: The IP address range for multicast is from `224.0.0.0` to `239.255.255.255`.

- **Broadcast (Layer 3)**: In broadcast communication, data is sent from one source to all devices on a specific network segment. This is typically used for network discovery protocols or when a device needs to send a message to all other devices in the same subnet.

  - IP Address: The broadcast address for a subnet is typically the highest address in that subnet. For example, in the subnet `192.168.1.0/24`, the broadcast address would be `192.168.1.255`.

- **Loopback**: The loopback IP address is used to test network software without physically transmitting packets over a network. It allows a device to send data to itself.
  - IP Address: The loopback address is typically `127.0.0.1` - `127.255.255.255`, with `127.0.0.1` being the most commonly used address.
  - Usage: It is commonly used for testing and troubleshooting network applications and services on the local machine.

## What is a Loopback Address? (OB 1.7)

A loopback address is an IP address that is already assigned to your own computer that basically represents your computer. It is used to test network software without physically transmitting packets over a network. When you send data to the loopback address, it is immediately returned to your own computer.

Recall that the loopback IP address is typically `127.0.0.1` - `127.255.255.255`.
The most commonly used loopback address is `127.0.0.1`.

You can use the loopback address to test network applications and services on your local machine. For example, if you are developing a web application, you can run a web server on your computer and access it using the loopback address `127.0.0.1`.

## Summary of IPv4 Addresses So Far (OB 1.7)

- An IPv4 address is a 32-bit number divided into four octets (8 bits each), represented in decimal format (e.g., `192.168.1.1`).
- IP addresses are classified into different classes (A, B, C) based on the range of the first octet, which determines the subnet mask and the number of hosts supported.
- A subnet mask is used to divide an IP address into network and host portions, helping to determine the network ID.
- Private IP addresses are reserved for use within private networks and are not routable on the public internet.
- CIDR (Classless Inter-Domain Routing) allows for more flexible allocation of IP addresses using variable-length subnet masking (VLSM).
- There are different types of IP communication: unicast (one-to-one), multicast (one-to-many), broadcast (one-to-all), and loopback (self-communication).
- The loopback address (`127.0 .0.1`) is used to test network applications on the local machine without sending data over a network.
- A router is used to connect different IP networks and facilitate communication between them, while a switch connects devices within the same network segment.
- A default gateway is the IP address of the router that connects a local network to other networks, allowing devices to communicate outside their own network.
- APIPA (Automatic Private IP Addressing) assigns a private IP address when a device cannot obtain one from a DHCP server, using the range `169.254.0.1` to `169.254.255.254`.
- The multicast IP address range is from `224.0.0.0` to `239.255.255.255`.
- The broadcast address for a subnet is typically the highest address in that subnet (e.g., `192.168.1.255`).
- The loopback IP address range is from `127.0.0.1` to `127.255.255.255`.
- The most commonly used loopback address is `127.0.0.1`.

| Class | 1st Octet Range | # of Bits for Network | # of Networks | Default Subnet Mask | CIDR Notation | # of Hosts per Network | Reserved Addresses            |
| ----- | --------------- | --------------------- | ------------- | ------------------- | ------------- | ---------------------- | ----------------------------- |
| A     | 1 - 127         | 8                     | 126           | 255.0.0.0           | /8            | 16,777,214             | 10.0.0.0 - 10.255.255.255     |
| B     | 128 - 191       | 16                    | 16,384        | 255.255.0.0         | /16           | 65,534                 | 172.16.0.0 - 172.31.255.255   |
| C     | 192 - 223       | 24                    | 2,097,152     | 255.255.255.0       | /24           | 254                    | 192.168.0.0 - 192.168.255.255 |
| D     | 224 - 239       | N/A                   | N/A           | N/A                 | N/A           | N/A                    | Multicast Range               |
| E     | 240 - 255       | N/A                   | N/A           | N/A                 | N/A           | N/A                    | Experimental Use              |

## What is Subnetting and Why Do It? (OB 1.7)

Subnetting is the process of dividing a larger network into smaller, more manageable subnetworks (subnets). This is done by borrowing bits from the host portion of an IP address to create additional network bits, allowing for more efficient use of IP addresses and improved network performance.

Subnetting is about taking a big network and breaking it down into smaller networks. This helps in organizing the network better, improving security, and reducing congestion.

Subnetting is when we take a Classful network (like Class A, B, or C) and divide it into smaller parts called subnets. This is done by changing the subnet mask to include more bits for the network portion and fewer bits for the host portion.

- Benefits of Subnetting:
  - Minimize Broadcast Traffic: By dividing a large network into smaller subnets, broadcast traffic is limited to each subnet, reducing overall network congestion.
  - Optimized Network Performance: Smaller subnets can lead to improved performance as there are fewer devices competing for bandwidth within each subnet.
  - Simpler Management: Issues can be often isolated to their respective subnets, making it easier to manage and troubleshoot the network.
  - Security: Subnetting can enhance security by isolating different segments of the network, limiting access between subnets as needed.
  - Efficient IP Address Utilization: Subnetting allows for better allocation of IP addresses, reducing waste and ensuring that IP addresses are used more effectively.
  - Filtering Traffic: Routers can be configured to filter traffic between subnets, enhancing security and control over data flow.

## How to Calculate the Subnet Mask in Subnetting (OB 1.7)

Let's look at a IP address with CIDR notation:

`192.168.30.0/24`

Subnetting involves borrowing bits from the host portion of the IP address to create additional network bits. In this example, the `/24` indicates that the first 24 bits are used for the network portion, leaving 8 bits for the host portion.

At the moment, the subnet mask is `255.255.255.0` and we have 1 network with 256 addresses (254 usable for hosts).

When we subnet, we will increase the number of networks by borrowing bits from the host portion. Each bit borrowed doubles the number of networks and halves the number of hosts per network.

Let's borrow a bit from the host portion:

`192.168.30.0/25`

- Subnet Mask: `255.255.255.128`

A tip to remember subnet masks is that each octet has 8 bits, and the values of each bit from left to right are: `128, 64, 32, 16, 8, 4, 2, 1`.

By borrowing 1 bit, we have:

- Number of Networks: 2 (2^1)
- Number of Hosts per Network: 126 (2^7 - 2)

Why minus 2? Because we have to reserve 2 addresses in each subnet: one for the network address and one for the broadcast address.

Let's borrow another bit:

`192.168.30.0/26`

- Subnet Mask: `255.255.255.192`

By borrowing 2 bits, we have:

- Number of Networks: 4 (2^2)
- Number of Hosts per Network: 62 (2^6 - 2)

We are calculating the subnet mask by adding the values of the borrowed bits in the last octet. For `/26`, we borrowed 2 bits, which are `128` and `64`. Adding these gives us `192`, resulting in a subnet mask of `255.255.255.192`.

Another example:

`/8 = 255.0.0.0` (no bits borrowed)

`/9 = 255.128.0.0` (1 bit borrowed: 128)

- Number of Host Bits left: 23
- Number of Networks: 2
- Number of Hosts per Network: 8,388,606
  - Calculation: 2^23(octets left in host portion) - 2

`/30 = ?`

- We borrow 22 bits (30 - 8 = 22)
- Subnet Mask: `255.255.255.?`
  - Calculation: 22 - 16 = 6 bits borrowed in the last octet
  - Values of borrowed bits: 128, 64, 32, 16, 8, 4
  - Adding these gives us: 128 + 64 + 32 + 16 + 8 + 4 = 252
  - Therefore, the subnet mask is `255.255.255.252`
- Number of Networks: 4,194,304 (2^22)
- Number of Hosts per Network: 2 (2^2 - 2)

## What are the Subnets on a Class C Network? (OB 1.7)

Let's try to write down all the subnets we can create on a Class C network by borrowing bits from the host portion. This goes from `/24` to `/31`.

- `/24 = 255.255.255.0`

  - Number of Networks: 1
  - Number of Hosts per Network: 254

- `/25 = 255.255.255.128`

  - Number of Networks: 2
  - Number of Hosts per Network: 126 (128 - 2)

- `/26 = 255.255.255.192`

  - Number of Networks: 4
  - Number of Hosts per Network: 62 ((2^6) - 2)

- `/27 = 255.255.255.224`

  - Number of Networks: 2^3 (3 = number of borrowed bits) = 8
  - Number of Hosts per Network: 30 ((2^5) - 2)

- `/28 = 255.255.255.240`

  - Number of Networks: 2^4 = 16
  - Number of Hosts per Network: 14 ((2^4) - 2)

- `/29 = 255.255.255.248`

  - Number of Networks: 2^5 = 32
  - Number of Hosts per Network: 6 ((2^3) - 2)

- `/30 = 255.255.255.252`

  - Number of Networks: 2^6 = 64
  - Number of Hosts per Network: 2 ((2^2) - 2)

- `/12 = 255.240.0.0`

  - Number of Networks: 2^4 = 16
  - Number of Hosts per Network: 1048576 - 2 = 1048574

## Subnetting Class C Network /25 (OB 1.7)

Let's look at an example of subnetting a Class C network: `192.168.30.0/24`

Let's subnet this network into two subnets by borrowing 1 bit from the host portion.

`192.168.30.0/25`

- Subnet Mask: `255.255.255.128`
- Block Size: 256 - 128 = 128
- Number of Networks: 2 (2^1)
  - We raise 2 to the number of bits borrowed (1 bit) to get the number of networks.
- Number of Hosts per Network: 126 (2^7 - 2)
  - Why minus 2? Because we have to reserve 2 addresses in each subnet: one for the network address and one for the broadcast address.
- IP Ranges:
  - Subnet 1: `192.168.30.0 - 192.168.30.127`
  - Subnet 2: `192.168.30.128 - 192.168.30.255`

### Subnetting Class C Network /26 (OB 1.7)

Let's look at an example of subnetting a Class C network: `192.168.60.0/24`

We want four networks, so we need to borrow 2 bits from the host portion.

`192.168.60.0/26`

- Subnet Mask: `255.255.255.192`
- Block Size: 256 - 192 = 64
- Number of Networks: 4 (2^2)
- Number of Hosts per Network: 2^6 - 2 = 62
- IP Ranges:
  - Subnet 1: `192.168.60.0 - 192.168.60.63`
    - Network Address: `192.168.60.0`
    - Broadcast Address: `192.168.60.63`
  - Subnet 2: `192.168.60.64 - 192.168.60.127`
    - Network Address: `192.168.60.64`
    - Broadcast Address: `192.168.60.127`
  - Subnet 3: `192.168.60.128 - 192.168.60.191`
    - Network Address: `192.168.60.128`
    - Broadcast Address: `192.168.60.191`
  - Subnet 4: `192.168.60.192 - 192.168.60.255`
    - Network Address: `192.168.60.192`
    - Broadcast Address: `192.168.60.255`

Remember, now that these are subnets, devices in different subnets cannot communicate directly without a router.

## Subnetting Class C Network /28 (OB 1.7)

Let's look at an example of subnetting a Class C network: `192.168.100.0/24`

We want to create 16 subnets, so we need to borrow 4 bits from the host portion.

`192.168.100.0/28`

- Subnet Mask: `255.255.255.240`
- Block Size: 256 - 240 = 16
- Number of Networks: 16 (2^4)
- Number of Hosts per Network: 2^4 - 2 = 14
