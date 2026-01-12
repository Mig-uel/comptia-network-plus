# Networking Cabling

## Intro to Network Cabling (OB 1.5)

Wireless networking has become increasingly popular and easy to set up, but wired networking remains the most reliable and fastest option for many applications.

### 802.3 Standards

The Institute of Electrical and Electronics Engineers (IEEE) 802.3 standards define the physical and data link layers for wired Ethernet networks. These standards cover various types of cabling, speeds, and protocols used in Ethernet networking.

This set of standards, also known as **Ethernet**, defines the protocols for wired LAN technologies, covering aspects like frame formats and physical layer specifications.

This is an older set of standards, but it is still widely used in modern networking.

### Network Cable Properties

- **Transmission Speeds**:
  - Copper cables achieve speeds of up to 40 Gbps.
  - Fiber optic cables can reach speeds of up to 100 Gbps and beyond.
- **Distance Limitations**:
  - Copper cables typically can reach distances of 1,000 meters (3,609 feet) for standard Ethernet.
  - Fiber cables can reach distances of up to 40 kilometers (24.85 miles) or more, depending on the type of fiber used.
- **Duplex Modes**:
  - **Half-Duplex**: Data transmission occurs in one direction at a time.
  - **Full-Duplex**: Data transmission occurs simultaneously in both directions.

### Cable Speeds

**Cable** speeds vary based on the type of cable used, impacting network performance; Ethernet cables like **Cat5**, **Cat5e**, **Cat6**, and **Cat6a** support different maximum speeds and frequencies over varying distances.

**Coaxial Cables** are used for broadband internet, supporting high-speed data transmission, while **Fiber Optic Cables** (single-mode and multi-mode) offer the highest speeds and longest distances for data transmission.

Key factors affecting cable speed include cable quality, installation practices, and environmental conditions.

### Network Cable Properties

- **Noise Immunity**:

  - EMI (Electromagnetic Interference) is a condition where external electromagnetic signals interfere with the data transmission in cables, leading to data corruption or loss.
  - Copper cables are more susceptible to EMI
    - Shielded cables (STP) provide better protection against EMI compared to unshielded cables (UTP).
  - Fiber optic cables are immune to EMI as they use light for data transmission.

- **Frequency**:

  - Measured in MHz, frequency indicates how many cycles per second a cable can handle.
  - Higher frequency cables can support higher data rates.
  - For example, Cat5e cables support frequencies up to 100 MHz, while Cat6a cables can handle frequencies up to 500 MHz.

- **Attenuation**:
  - Attenuation refers to the loss of signal strength as it travels through a cable.
  - It is measured in decibels (dB) and increases with distance.
  - Higher quality cables have lower attenuation rates, allowing for longer transmission distances without signal degradation.

## Coaxial Cable (OB 1.5)

Coaxial cable, or coax, consists of a central conductor surrounded by an insulating layer, a metallic shield, and an outer insulating layer. It is commonly used for cable television and broadband internet connections.

Coaxial cables is a type of electrical cable consisting of a central conductor, an insulating layer, a metallic shield, and an outer insulating layer. The design of coaxial cables helps to reduce electromagnetic interference (EMI) and allows for high-frequency signal transmission. It is commonly used for cable television, broadband internet connections, satellite communication, and other applications requiring reliable data transmission over longer distances.

**RG-6** and **RG-59** are common types of coaxial cables used in networking and television applications. RG-6 is thicker and has better shielding, making it suitable for longer distances and higher frequencies compared to RG-59.

Coax is thicker and has better shielding compared to twisted pair cables, making it suitable for longer distances and higher frequencies. However, it is less flexible and more expensive than twisted pair cables.

It is commonly used in residential and commercial settings for its durability and high-quality signal transmission.

### Coaxial Cable/RG-6

- **BNC Connector**:

  - Bayonet Neill-Concelman (BNC) connectors are commonly used with coaxial cables for secure and reliable connections.
  - They feature a twist-lock mechanism that ensures a tight fit, reducing the risk of signal loss or interference.
  - Commonly used in the old bus and ring network topologies.

- **F Connector**:
  - F connectors are widely used for cable television and broadband internet connections.
  - They screw onto the coaxial cable, providing a secure connection that minimizes signal loss.
  - F connectors are commonly used in residential and commercial settings for their ease of installation and reliable performance.

## Fiber Optic Cable (OB 1.5)

Fiber optic cables use light to transmit data, allowing for high-speed and long-distance communication with minimal signal loss. They consist of a core made of glass or plastic fibers, surrounded by cladding that reflects light back into the core, and an outer protective jacket.

Fiber optic cabling uses light to transmit data, offering significantly higher speeds and greater bandwidth compared to traditional copper cables.

It consists of a core made of glass or plastic fibers that carry light signals over long distances with minimal signal loss, making it ideal for high-speed data transmission in telecommunications and internet backbone infrastructures.

Unlike Coax cables, fiber optic cables consist of an outer jacket, strengthening layer, coating, cladding, and the fiber strands themselves.

There are two main types of fiber optic cables: single-mode and multi-mode.

### Single-Mode Fiber

Single mode fiber optic cables are designed for **long-distance** communication, using a single strand of glass fiber with a small diameter that allows only one mode of light to propagate. This minimizes signal loss and allows for higher bandwidth over longer distances.

This design minimizes signal attenuation and dispersion over long distances, making it suitable for high speed, high bandwidth transmissions over lengths of up to 40 kilometers (24.85 miles) or more.

Single mode fiber typically is commonly used in telecommunications and cable tv networks.

### Multi-Mode Fiber

Multi-mode fiber optic cables use larger core diameters that allow multiple modes of light to propagate simultaneously. This design is suitable for **shorter distance** communication, such as within buildings or campuses, where high bandwidth is required over shorter distances.

This type of fiber is commonly used within buildings or on campuses, supporting data rates at shorter distances, usually up to 500 meters for data applications and up to 2 kilometers for telecom applications.

Multi-mode fiber is generally more cost-effective and easier to work with compared to single-mode fiber, making it a popular choice for local area networks (LANs) and other short-distance applications.

### Advantages and Disadvantages

**Advantages** of fiber optic cables include:

- Not susceptible to electromagnetic interference (EMI)
- Longest transmission distances
- Fastest speeds into the Tbps range
- High bandwidth capacity
- Lightweight and thin

**Disadvantages** of fiber optic cables include:

- More expensive than copper cables
- Most fragile and can be difficult to install
- Difficult to troubleshoot without specialized equipment
- Expensive tools needed for installation and repair
- Can't easily repair cable breaks in the field

### Fiber Connectors

- **ST Connector**:

  - Straight Tip (ST) connectors are one of the earliest types of fiber optic connectors.
  - They use a bayonet-style coupling mechanism for secure connections.
  - ST connectors are commonly used in network environments and are known for their durability and ease of use.

- **SC Connector**:

  - Subscriber Connector (SC) connectors are widely used in fiber optic networks.
  - They feature a push-pull coupling mechanism that provides a secure and reliable connection.
  - SC connectors are known for their low insertion loss and high return loss, making them suitable for high-performance applications.

- **LC Connector**:

  - Lucent Connector (LC) connectors are small form-factor connectors commonly used in high-density fiber optic applications.
  - They use a latch mechanism for secure connections and are known for their compact size.
  - LC connectors are widely used in data centers and telecommunications networks due to their high performance and reliability.

- **Dual LC Connector**:

  - Dual LC connectors combine two LC connectors into a single unit, allowing for higher density fiber optic connections.
  - They are commonly used in data centers and high-density networking environments where space is limited.
  - Dual LC connectors provide efficient and reliable connections for high-speed data transmission.

- **Multi-Fiber Push On (MPO) Connector**:
  - MPO connectors are designed to connect multiple fiber optic strands in a single connector, typically used for high-density applications.
  - They can accommodate 12 or more fibers in a compact form factor, making them ideal for data centers and telecommunications networks.
  - MPO connectors enable efficient and high-speed data transmission by allowing multiple channels to be connected simultaneously.

## DAC Cables (OB 1.5)

When you are building a network, you are going to want to make sure your backbone (the main cabling that connects all your switches and routers) is as fast as possible.

Instead of using fiber optic cables, which can be expensive and require special transceivers, you can use Direct Attach Copper (DAC) cables.

**Direct Attach Copper (DAC)** cables are used for short-range connections between networking devices, such as switches and servers. They consist of twinax (twinaxial) copper cables with integrated transceivers on each end, allowing for high-speed data transmission over short distances.

They offer a cost-effective, low-power alternative for close-range connections, typically up to 7 meters (about 23 feet).

DAC cables are typically used in data centers and high-performance computing environments where low latency and high bandwidth are required for short-distance connections. They are ideal for connecting switches, servers, and storage devices within racks or across adjacent racks.

### Twinaxial Cables

More specifically, DAC cables use **twinaxial** cabling, which consists of two inner conductors surrounded by a shield. This design helps to reduce electromagnetic interference (EMI) and allows for high-speed data transmission over short distances.

Twinaxial cables are used in data enters for high-speed short-distance connections. Various speeds are supported, including 10 Gbps, 25 Gbps, 40 Gbps, 50 Gbps, and 100 Gbps.

Advantages of twinaxial cables include:

- Shielding against EMI
- Lower latency compared to fiber optic cables
- Cost-effective for short-distance connections

Disadvantages of twinaxial cables include:

- More expensive than traditional coax and twisted pair cables
- Limited to short distances (typically up to 7 meters)
- Less flexible than other cable types

### DAC Connectors

- **SFP+ Connector**:

  - Small Form-Factor Pluggable Plus (SFP+) connectors are commonly used with DAC cables for high-speed data transmission.
  - They support speeds of up to 10 Gbps and are widely used in data centers and enterprise networks.
  - SFP+ connectors provide a compact and versatile solution for connecting networking devices.

- **QSFP+ Connector**:

  - Quad Small Form-Factor Pluggable Plus (QSFP+) connectors are designed for high-speed data transmission using DAC cables.
  - They support speeds of up to 40 Gbps and are commonly used in data centers and high-performance computing environments.
  - QSFP+ connectors provide a high-density solution for connecting multiple channels in a single connector.

- **QSFP28 Connector**:
  - Quad Small Form-Factor Pluggable 28 (QSFP28) connectors are used for ultra-high-speed data transmission with DAC cables.
  - They support speeds of up to 100 Gbps and are widely used in data centers and telecommunications networks.
  - QSFP28 connectors provide a compact and efficient solution for high-speed networking applications.

## Twisted Pair Cable (OB 1.5)

When it comes to cabling up your network, the most common type of cable you will encounter is twisted pair cabling. This type of cabling is widely used for Ethernet networks and telephone systems.

**Twisted pair cabling** consists of eight individual wires twisted into four pairs. The twisting helps to reduce electromagnetic interference (EMI) and crosstalk between the pairs, improving signal quality.

This is the most used network cabling type for LANs (Local Area Networks) due to its cost-effectiveness and ease of installation.

Advantages of twisted pair cabling include:

- Easier to install and manage than coax or fiber optic cables
- STP (Shielded Twisted Pair) protects against EMI
- UTP (Unshielded Twisted Pair) is more affordable and flexible
- Least expensive type of network cabling

Disadvantages of twisted pair cabling include:

- Transmission distances are shorter compared to coax and fiber optic cables (330 feet/100 meters for standard Ethernet)
- More susceptible to EMI, especially UTP cables
- Lower maximum speeds compared to fiber optic cables

### Twisted Pair Types

- **Unshielded Twisted Pair (UTP)**:

  - UTP cables consist of twisted pairs of wires without any additional shielding.
  - They are commonly used in Ethernet networks and telephone systems due to their affordability and ease of installation.
  - UTP cables are suitable for environments with low electromagnetic interference (EMI).

- **Shielded Twisted Pair (STP)**:
  - STP cables have an additional shielding layer that protects against electromagnetic interference (EMI).
  - They are used in environments with high EMI, such as industrial settings or areas with heavy machinery.
  - STP cables provide better signal quality and reduced crosstalk compared to UTP cables.

### Twisted Pair Connectors

- **RJ-45 Connector**:

  - The Registered Jack 45 (RJ-45) connector is the most common connector used with twisted pair cabling for Ethernet networks.
  - It features eight pins that correspond to the eight wires in a twisted pair cable, allowing for reliable data transmission.
  - RJ-45 connectors are widely used in residential and commercial networking applications.

- **RJ-11 Connector**:
  - The Registered Jack 11 (RJ-11) connector is commonly used for telephone connections.
  - It typically has four or six pins, depending on the application, and is smaller than the RJ-45 connector.
  - RJ-11 connectors are widely used in residential and commercial telephone systems.

### Twisted Pair Categories

Twisted pair cables are categorized based on their performance characteristics, including maximum data rates and frequency capabilities. Common categories include:

- **Cat5**: Supports speeds up to 100 Mbps and frequencies up to 100 MHz. Suitable for basic Ethernet networks.
- **Cat5e**: An enhanced version of Cat5, supporting speeds up to 1 Gbps and frequencies up to 100 MHz. It reduces crosstalk and is widely used in modern Ethernet networks.
- **Cat6**: Supports speeds up to 10 Gbps for distances up to 55 meters and frequencies up to 250 MHz. It provides better performance and reduced crosstalk compared to Cat5e.
- **Cat6a**: An augmented version of Cat6, supporting speeds up to 10 Gbps for distances up to 100 meters and frequencies up to 500 MHz. It offers improved shielding and performance for high-speed networks.
- **Cat7**: Supports speeds up to 10 Gbps for distances up to 100 meters and frequencies up to 600 MHz. It features enhanced shielding for reduced interference.
- **Cat8**: The latest category, supporting speeds up to 25 Gbps or 40 Gbps for distances up to 30 meters and frequencies up to 2000 MHz. It is designed for data centers and high-performance computing environments.

Each category of twisted pair cable is designed to meet specific networking requirements, and selecting the appropriate category is essential for ensuring optimal network performance.

### Wiring Standards

There two main wiring standards for twisted pair cabling: T568A and T568B. These standards define the pinout configurations for RJ-45 connectors, specifying how the individual wires within the cable should be arranged.

- **T568A**:

  - The T568A wiring standard is one of the two main configurations for terminating twisted pair cables with RJ-45 connectors.
  - It specifies the arrangement of the eight wires within the cable, ensuring proper connectivity and performance.
  - T568A is commonly used in residential installations and is recognized by the Telecommunications Industry Association (TIA).
  - It is important to use the same wiring standard on both ends of a cable to ensure proper communication between devices.

- **T568B**:
  - The T568B wiring standard is the second main configuration for terminating twisted pair cables with RJ-45 connectors.
  - It specifies a different arrangement of the eight wires compared to T568A, while still ensuring proper connectivity and performance.
  - T568B is widely used in commercial installations and is also recognized by the Telecommunications Industry Association (TIA).
  - Similar to T568A, it is crucial to use the same wiring standard on both ends of a cable to ensure proper communication between devices.

Both T568A and T568B wiring standards are widely used, and the choice between them often depends on existing infrastructure or personal preference. However, it is essential to maintain consistency within a network to avoid connectivity issues.

## Twisted Pair Wiring Standards (OB 1.5)

When wiring twisted pair cables, it is essential to follow specific wiring standards to ensure proper connectivity and performance. The two main wiring standards for twisted pair cabling are T568A and T568B. These standards define the pinout configurations for RJ-45 connectors, specifying how the individual wires within the cable should be arranged.

Most organizations use the T568B standard, but either is acceptable as long as both ends of the cable are wired the same way.

When following either standard, it is called a **straight-through cable** if both ends are wired the same way.

However, mixing the two standards on either end of a cable will result in a crossover cable, which is used for specific applications like connecting two computers directly without a switch.

### Straight-Through Cable

**Straight-through cables** are used to connect different types of devices, such as a computer to a switch or a router to a modem. In a straight-through cable, both ends are wired using the same standard (either T568A or T568B).

### Crossover Cable

**Crossover cables** are used to connect similar devices directly, such as connecting two computers or two switches together. In a crossover cable, one end is wired using the T568A standard, while the other end is wired using the T568B standard. This configuration allows for proper communication between the devices by crossing over the transmit and receive pairs.

## Ethernet Specs (OB 1.5)

When setting up a networks, you are going to encounter different Ethernet specifications that define the speed and distance capabilities of various cabling types. It can also be called Ethernet at the Physical Layer (Layer 1) of the OSI model.

Here are some common Ethernet specifications:

- 10Base2
- 10Base5
- 10BaseT
- 100BaseTX
- 100BaseFX
- 1000BaseCX
- 1000BaseT
- 1000BaseSX
- 1000BaseLX
- 10GBaseT
- 10GBaseSR
- 10GBaseLR
- 10GBaseER
- 10GBaseSW
- 10GBaseLW
- 10GBaseEW
- 40GBaseT

But what do these names mean?

Well, let's break it down: `[Speed][Base][Medium]`

- **Speed**: The first part indicates the maximum data transfer rate of the Ethernet standard. For example, "10" means 10 Mbps, "100" means 100 Mbps, "1000" means 1 Gbps, and "10G" means 10 Gbps.
- **Base**: The second part, "Base," stands for baseband signaling, which means that the entire bandwidth of the medium is used for a single data channel.
  - Baseband is the most common signaling method for Ethernet networks.
  - Broadband, on the other hand, allows multiple channels to share the same medium simultaneously.
- **Type of Medium**: The last part indicates the type of cabling or medium used for the Ethernet connection. Common mediums include:
  - **T**: Twisted Pair (e.g., Cat5, Cat6 cables)
  - **FX**: Fiber Optic (Fast Ethernet over fiber)
  - **CX**: Copper (short-range copper connections)
  - **SR**: Short Range (fiber optic)
  - **LR**: Long Range (fiber optic)
  - **ER**: Extended Range (fiber optic)
  - **SW**: Short Wavelength (fiber optic)
  - **LW**: Long Wavelength (fiber optic)
  - **EW**: Extended Wavelength (fiber optic)
