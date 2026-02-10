# Wireless Networking

## Wireless Combo Devices vs. Dedicated Devices (OB 2.3)

The primary way people connect to networks today is through wireless networking. There are two main types of wireless networking devices: wireless combo devices and dedicated wireless devices.

Beforehand, let's go over two terms people generally confuse, **wireless routers** vs. **wireless access points**.

In a typical home network or small business network, you would typically have a single device that acts as a combination of a wireless router, a wireless access point, a network switch, and a network firewall. This device is often referred to as a **wireless combo device** or simply a **wireless router**.

Versus, on a corporate network or enterprise network, you would typically have dedicated devices for each function. For example, you might have a dedicated wireless access point that connects to a separate network switch and a separate network firewall.

## Wireless Channels and Frequencies (OB 2.3)

So what exactly are wireless channels and frequencies? Well first we have to start of with frequencies. There are three frequencies that you must know for the CompTIA Network+ exam:

- 2.4 GHz
- 5 GHz
- 6 GHz.

### Channels

**WiFi channels** are specific ranges of frequencies within the broader frequency bands (like 2.4 GHz, 5 GHz, and 6 GHz) that are used for wireless communication. Each channel corresponds to a specific frequency range within the overall band. It allows multiple devices to communicate without interfering with each other.

For example, in the 2.4 GHz band, there are typically 11 channels available in North America (channels 1 through 11). Each channel is spaced 5 MHz apart, but the actual bandwidth of each channel is about 20 MHz wide. This means that channels can overlap with each other, which can lead to interference if multiple devices are using overlapping channels.

In simpler terms, think of channels like lanes on a highway. Each lane (channel) allows cars (data) to travel without bumping into each other. However, if two lanes are too close together (overlapping channels), cars might accidentally drift into each other's lanes, causing traffic jams (interference).

So to minimize interference, it's common practice to use non-overlapping channels. In the 2.4 GHz band, the most commonly used non-overlapping channels are 1, 6, and 11.

The availability of channels and allowed channels can vary by country due to regulatory differences. For example, some countries may allow the use of channels 12 and 13 in the 2.4 GHz band, while others may not.

### Regulatory Impacts

**Regulatory impacts** refer to the rules and regulations set by government agencies or international bodies that govern the use of wireless frequencies and channels. These regulations are in place to ensure that wireless devices operate safely and do not interfere with other communication systems. Different countries have different regulatory bodies that set these rules. For example, in the United States, the Federal Communications Commission (FCC) is responsible for regulating wireless communications.

These regulations affect the availability of certain frequencies and channels for wireless networking in different regions which can impact the design and deployment of wireless networks, especially for businesses that operate in multiple countries.

### Channel Width

To recall, **WiFi channels** are specific ranges of frequencies within the broader frequency bands (like 2.4 GHz, 5 GHz, and 6 GHz) that are used for wireless communication. Each channel corresponds to a specific frequency range within the overall band.

- It is used for organizing and managing wireless communication.
- The availability of channels can vary by country due to regulatory differences.

**Frequency bands** are broader ranges of frequencies that are allocated for specific types of communication, such as WiFi, cellular networks, or satellite communication. For WiFi, the most common frequency bands are **2.4 GHz**, **5 GHz**, and **6 GHz**.

**Relationship**: Channels are subdivisions within frequency bands. For example, the 2.4 GHz band contains multiple channels (1-11 in North America), each representing a specific range of frequencies within that band.

**Channel width** refers to the amount of **frequency spectrum** (measured in MHz) that a WiFi channel occupies. Common channel widths for WiFi include 20 MHz, 40 MHz, 80 MHz, and 160 MHz. Wider channel widths can provide higher data transfer rates but may also increase the likelihood of interference with other devices.

- Channel width affects data transfer rates and potential interference.
- Wider channels can carry more data but may overlap with other channels, leading to interference.
- Common channel widths include 20 MHz, 40 MHz, 80 MHz, and 160 MHz.
- Choosing the appropriate channel width is important for optimizing network performance and minimizing interference.

### Frequency Options in Wireless Networking

Wireless networks operate across different frequency bands, each with its own characteristics and use cases. The most common frequency bands used in wireless networking are:

- **2.4 GHz**: This frequency band is widely used for WiFi networks and offers good range and penetration through walls. However, it is more susceptible to interference from other devices like microwaves and cordless phones. It typically supports lower data rates compared to higher frequency bands.
- **5 GHz**: This frequency band provides higher data rates and is less prone to interference compared to the 2.4 GHz band. However, it has a shorter range and is less effective at penetrating walls and obstacles. It is commonly used for high-speed WiFi networks.
- **6 GHz**: This is a newer frequency band that offers even higher data rates and lower latency compared to the 2.4 GHz and 5 GHz bands. It is primarily used for WiFi 6E networks and is less congested, making it ideal for high-performance applications. However, it has a shorter range and limited penetration capabilities.

When designing a wireless network, it is important to consider the specific requirements of the environment and the devices being used to determine the most appropriate frequency band for optimal performance.

### Non-Overlapping Channels

**Non-overlapping channels** are specific channels within a frequency band that do not interfere with each other when used simultaneously.
In the 2.4 GHz band, the most commonly used non-overlapping channels are channels 1, 6, and 11. These channels are spaced far enough apart that their frequency ranges do not overlap, minimizing interference and improving network performance.

In the 5 GHz band, there are more non-overlapping channels available due to the wider frequency range. This allows for better performance and reduced interference in environments with multiple wireless networks.

Using non-overlapping channels is important for optimizing wireless network performance, especially in environments with multiple access points or networks. By selecting non-overlapping channels, network administrators can reduce interference and improve overall connectivity for users.

### 2.4 GHz

The **2.4 GHz** band is widely used for wireless networking due to its longer range and better penetration through walls and obstacles. However, it is also more susceptible to interference from other devices that operate in the same frequency range, such as microwaves, cordless phones, and Bluetooth devices.

- Long range communications because it has better penetration through walls and obstacles.
- Slower data rates compared to higher frequency bands.
- More susceptible to interference from other devices operating in the same frequency range.
- Commonly used for WiFi standards such as 802.11b, 802.11g, and 802.11n.
- Non-overlapping channels: 1, 6, and 11.

### 5 GHz

The **5 GHz** band offers higher data rates and is less prone to interference compared to the 2.4 GHz band. However, it has a shorter range and is less effective at penetrating walls and obstacles.

- Short range communications because it has poorer penetration through walls and obstacles.
- Faster data rates compared to the 2.4 GHz band.
- Less susceptible to interference from other devices.
- Commonly used for WiFi standards such as 802.11a, 802.11n, 802.11ac, and 802.11ax.
- More non-overlapping channels available compared to the 2.4 GHz band.

### 6 GHz

The introduction of the **6 GHz** band expands the bandwidth available for WiFi networks, allowing for higher data rates and lower latency. It is primarily used for WiFi 6E networks and is less congested, making it ideal for high-performance applications. However, it has a shorter range and limited penetration capabilities.

It supports much higher data rates, lower latency, and more simultaneous connections compared to the 2.4 GHz and 5 GHz bands which makes it ideal for high-demanding applications and environments with many connected devices.

The 6 GHz band is particularly beneficial for next-generation WiFi standards like WiFi 6E, which take advantage of the additional spectrum to provide enhanced performance and capacity.

### Band Steering

**Band steering** is a feature found in some wireless access points and routers that automatically directs dual-band capable devices to connect to the most appropriate frequency band (2.4 GHz or 5 GHz) based on factors such as signal strength, network congestion, and device capabilities. This helps optimize network performance by balancing the load between the two frequency bands and reducing interference.

By optimizing the distribution of devices across the available frequency bands, band steering can improve overall network efficiency and user experience. For example, devices that are closer to the access point and capable of using the 5 GHz band may be directed to connect to that band, while devices that are farther away or have limited capabilities may be directed to the 2.4 GHz band.

### 802.11h

**802.11h** is an amendment to the IEEE **802.11** wireless networking standard that introduces additional features for managing spectrum usage and improving coexistence with other wireless systems. It added support for **Dynamic Frequency Selection (DFS)** and **Transmit Power Control (TPC)** to comply with regulatory requirements in certain regions, particularly in the 5 GHz frequency band.

- **Dynamic Frequency Selection (DFS)**: This feature allows wireless devices to automatically switch to a different channel if they detect interference from radar systems or other priority users in the same frequency band. This helps minimize interference and ensures compliance with regulatory requirements.
- **Transmit Power Control (TPC)**: This feature allows wireless devices to adjust their transmit power based on the distance to the receiving device and the surrounding environment. By reducing transmit power when possible, TPC helps minimize interference with other wireless systems and conserves energy.

Overall, 802.11h enhances the performance and reliability of wireless networks by improving spectrum management and coexistence with other wireless systems, particularly in the 5 GHz frequency band.

## Wireless Standards

When it comes to setting up wireless networks, understanding wireless standards is crucial. Wireless standards define the specifications for wireless communication, including data rates, frequency bands, and security protocols.

There are so many different wireless standards, each with its own characteristics and use cases.

| Standard          | Frequency Band        | Max Data Rate | Compatibility     | Year Introduced |
| ----------------- | --------------------- | ------------- | ----------------- | --------------- |
| 802.11a (WiFi 1)  | 5 GHz                 | 54 Mbps       | 802.11n/ac/ax     | 1999            |
| 802.11b (WiFi 2)  | 2.4 GHz               | 11 Mbps       | 802.11g/n/ac/ax   | 1999            |
| 802.11g (WiFi 3)  | 2.4 GHz               | 54 Mbps       | 802.11n/ac/ax     | 2003            |
| 802.11n (WiFi 4)  | 2.4 GHz, 5 GHz        | 600 Mbps      | 802.11a/b/g/ac/ax | 2009            |
| 802.11ac (WiFi 5) | 2.4 GHz, 5 GHz        | 3.5 Gbps      | 802.11a/b/g/n/ax  | 2012            |
| 802.11ax (WiFi 6) | 2.4 GHz, 5 GHz, 6 GHz | 9.6 Gbps      | 802.11a/b/g/n/ac  | 2019            |

## Understanding SSID (OB 2.3)

**SSID (Service Set Identifier)** is the name assigned to a wireless network. It is used to identify and differentiate between different wireless networks in the same area. Devices use the SSID to connect to the correct network.

In the world of networking, there are additional terms related to wireless networks, such as BSS, SSID, BSSID, ESS, and ESSID.

- **BSS (Basic Service Set)**: A BSS is a group of devices that are connected to the same wireless network and communicate with each other. It typically consists of an access point and the associated client devices.
- **BSSID (Basic Service Set Identifier)**: The BSSID is the unique identifier for a BSS. It is usually the MAC address of the access point in the BSS and is included in the packets transmitted by the access point.
- **SSID (Service Set Identifier)**: The SSID is the name assigned to a wireless network. It is unique character string that identifies an Access Point (AP) or a group of APs in an Extended Service Set (ESS).
- **ESS (Extended Service Set)**: An ESS is a set of connected BSSs that share the same SSID and allow seamless roaming for clients.
- **ESSID (Extended Service Set Identifier)**: The ESSID is the identifier for an ESS. It is the same as the SSID for the network and is used to identify the network across multiple BSSs.

## Wireless Hardware (OB 2.3)

When setting up a wireless network, various hardware components are involved to ensure proper connectivity and performance.

### Wireless NIC (Network Interface Card)

A **Wireless NIC (Network Interface Card)** is a hardware component that allows a device to connect to a wireless network. It can be integrated into the device (like in laptops and smartphones) or can be an external adapter (like USB WiFi adapters) that can be added to desktops or other devices.

- Required to connect to a wireless network or host.
- Defines the capabilities of the wireless connection (e.g., supported standards, frequency bands).
- Can be internal (built-in) or external (USB adapters, PCIe cards).
- Most devices today come with built-in wireless NICs.

### Wireless Access Point (WAP)

A **Wireless Access Point (WAP)** is a networking device that allows wireless devices to connect to a wired network using WiFi or related standards. It acts as a bridge between the wireless devices and the wired network, enabling communication and data transfer.

- Uses Radio Frequency (RF) to provide connections to wireless clients.
- Creates a wireless star topology.
- Uses CSMA/CA to manage collisions.
  - Compared to CSMA/CD used in wired networks, CSMA/CA (Carrier Sense Multiple Access with Collision Avoidance) is used in wireless networks to minimize collisions by using acknowledgments and waiting periods before transmitting data.
  - Clients send a test signal to check if the channel is clear before transmitting data.
- It is a layer 2 device (Data Link Layer) that operates within the OSI model.
- Creates a single collision domain and a single broadcast domain.
  - Compared to switches that create separate collision domains for each port, a WAP creates a single collision domain for all connected wireless clients.
- Requires an IP address for management and configuration.
- Can support multiple SSIDs to create separate virtual networks.
- Can be standalone or integrated into a wireless router or other networking device.

### Autonomous Access Points

An **Autonomous Access Point** is a standalone wireless access point that operates independently and is configured individually. Each autonomous access point has its own management interface and settings.

- Configured and managed individually.
- Suitable for small networks with a limited number of access points.
- Each access point operates independently without centralized control.
- Ideal for straightforward, smaller network environments where individual management is sufficient.

### Lightweight Access Points

A **Lightweight Access Point** is a type of wireless access point that relies on a centralized controller for management and configuration. Lightweight access points are designed to work in larger networks where multiple access points need to be managed collectively. They are managed via a Wireless LAN Controller (WLC).

- Managed centrally through a Wireless LAN Controller (WLC).
- Suitable for large networks with multiple access points.
- Allows for easier management, configuration, and monitoring of multiple access points.
- Supports features like seamless roaming, load balancing, and centralized security policies.
- Cannot be managed directly; all configurations are done through the WLC.

### Wireless Antennas

Wireless antennas are essential components of wireless networking devices that facilitate the transmission and reception of radio signals. Different types of antennas are used based on the specific requirements of the wireless network.

- **Omnidirectional Antennas**: These antennas radiate signals in all directions (360 degrees) and are commonly used in environments where coverage is needed in multiple directions, such as in homes or offices. They are ideal for general-purpose wireless networking.
  - These are the most common type of antennas used in consumer and business wireless access points.
  - Shorter range compared to directional antennas.

- **Directional Antennas**: These antennas focus the signal in a specific direction, providing a longer range and stronger signal in that direction. They are used in point-to-point connections or when coverage is needed in a specific area, such as connecting two buildings.
  - Used for long-distance communication or point-to-point links.
  - Longer range compared to omnidirectional antennas.
  - Examples include Yagi, parabolic, and panel antennas.
    - Yagi-Uda antennas are highly directional and focus the signal for up to a mile or more.
    - Parabolic antennas use a parabolic reflector to focus the signal into a narrow beam for up to 8 miles or more.

## Wireless Setups (OB 2.3)

When setting up a wireless network, there are a few wireless topologies and configurations to consider.

### Point-to-Point

A **Point-to-Point** wireless setup involves a direct connection between two wireless devices, typically two access points or bridges. This setup is often used to connect two separate locations, such as two buildings on a campus or two offices in different locations.

Point-to-Point networks establish a **direct connection** between two wireless devices, allowing them to communicate directly with each other without the need for an intermediary device.

This type of setup is commonly used for **linking two locations** in a WAN (Wide Area Network) or providing a dedicated pathway for data transmission between two points.

We consumers do not typically use Point-to-Point setups in our homes, but businesses like ISPs or large enterprises may use them to connect different sites.

### Mesh Network

A **Mesh Network** is a type of wireless network topology where multiple access points or nodes are interconnected to provide seamless coverage and redundancy. In a mesh network, each node can communicate with multiple other nodes, creating a web-like structure that allows for efficient data routing and improved reliability.

Mesh networks consist of nodes that connect directly and dynamically to as many other nodes as possible. This creates multiple pathways for data to travel, enhancing network resilience and coverage.

This configuration creates multiple pathways for data to travel between devices, improving reliability and coverage. If one node fails or experiences interference, data can be rerouted through other nodes in the network.

Mesh networks are self-healing and scalable, making them ideal for large areas like smart cities and IoT applications.

### Ad-Hoc Network

An **Ad-Hoc Network** is a type of wireless network topology where devices communicate directly with each other without the need for a central access point or router. In an ad-hoc network, each device can act as both a client and a router, allowing for peer-to-peer communication.

Ad-hoc networks are decentralized and not rely on a pre-existing infrastructure.

Nodes within an ad-hoc network communicate directly with each other without the need for a central access point or router. Each device can act as both a client and a router, allowing for peer-to-peer communication.

Ad-hoc networks are typically used in situations where a temporary network is needed, such as during emergencies, outdoor events, or in remote areas where traditional infrastructure is not available. They are also commonly used for file sharing and gaming among devices in close proximity.

If you ever want to connect two devices like two laptops with a cable, you can use a crossover cable.

### Infrastructure Network

An **Infrastructure Network** is a type of wireless network topology where devices communicate through a central access point or router. In an infrastructure network, all devices connect to the access point, which manages the communication and data transfer between devices.

Infrastructure networks rely on fixed routers or access to manage traffic to and from wireless devices.

This is the most common type of network setup used in homes, businesses, and public WiFi hotspots. It provides centralized management, security, and scalability for wireless networks.
