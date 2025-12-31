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
