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
