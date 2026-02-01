_This project has been created as part of the 42 curriculum by khkomasa_

# NetPractice

## 📖 Description

NetPractice is an introductory simulation project designed to help students understand the fundamentals of computer networks through 10-level practices. The project focuses network configuration problems that focus on TCP/IP addressing with IPv4.

Using a browser-based training interface, the goal is to fix non-functioning network diagrams by correctly configuring parameters such as IP addresses, subnet masks, and default gateways. The networks are not real, but they behave like real-world networking environments.

By completing this project, students gain a practical understanding of how devices communicate within a network and how routing works.

## 🚀 Instructions

1. **A modern web browser**

```bash
⚠️ Google Chrome or any Chromium-based browser is recommended
⚠️ Firefox may not work properly with the interface
```

2. **Download official web-based simulator**

```bash
Step1: donwload it at netpractice project or below path:
https://cdn.intra.42.fr/document/document/43640/net_practice.1.8.tgz

Step2: unzip it. You can see these files.
net_practice/
├── css/
│   └── netpractice.css
├── img/
│   └────── *.png
├── js/
│   └────── *.js
│────────── *.html
└── README.md
```

3. **Start Trainning/Evaluation**

```bash
Step1: Find index.html and open with browser.

Step2: Selection your choices i.e., Training, Evaluation.

Step3: Input your infra-login name.

Step4: Enjoy Trainning/Evaluation. If configuration is correct, the 'Next level' button appear.
```

4. **Exporting Trainning**

```bash
Find 'Get my config' button. Push it, the json file is downloaded.
```

## 🚀 Resources

### **1. TCP/IP model**

TCP/IP model is a collection of communication protocols that standardize data exchange in networks. The name stands for ‘Transmission Control Protocol’ (TCP) and ‘Internet Protocol’ (IP), the two core protocols responsible for data transport across networks. Alongside these, several other protocols exist to support various network functions.

Originally developed in the 1970s for ARPANET, the precursor to the internet, the TCP/IP protocol suite has since become the global standard for network communication. Its flexible and scalable architecture makes it suitable for everything from small business networks to complex global infrastructures.

The TCP/IP model can be described as 4 four-layers from Top to Bottom as below:

#### Application Layer

Provides network services directly to end-user applications. Well-known Protocols:

- HTTP (Hypertext Transfer Protocol) – Web access.
- FTP (File Transfer Protocol) – File transfer.
- SMTP (Simple Mail Transfer Protocol) – Email.

#### Transport Layer

Ensures end-to-end communication between source and destination devices. Well-known Protocols:

- TCP (Transmission Control Protocol): Connection-oriented, reliable, ordered delivery.
- UDP (User Datagram Protocol): Connectionless, fast, no guaranteed delivery.

#### Internet Layer

Handles logical addressing and routing of packets across multiple networks. Well-known Protocols:

- IP (Internet Protocol) – An Internet address works like a postal address, allowing data to be routed to the chosen destination.
- ICMP (Internet Control Message Protocol) – Error reporting and diagnostics.

#### Network Access Layer

Controls the physical transmission of data over the network medium. Well-known Protocols:

- Ethernet – a widely used technology that provides wired connectivity for local area networks (LANs).
- Wi-Fi – a wireless networking technology.

**The TCP/IP model can be summarized as below.**

| Layer | Name               | Protocols       | Function                     |
| ----- | ------------------ | --------------- | ---------------------------- |
| 4     | **Application**    | HTTP, FTP, SMTP | User services and interfaces |
| 3     | **Transport**      | TCP, UDP        | Reliable data delivery       |
| 2     | **Internet**       | IP, ICMP        | Routing and addressing       |
| 1     | **Network Access** | Ethernet, Wi-Fi | Physical data transmission   |

### **2.OSI Model**

The Internet’s layered architecture model that we’ve introduced above is not the only network model in existence. OSI Model, a seven-layer model describing how data moves from physical transmission to user applications. In the education purpose, OSI model is adopted for network understanding. The only real difference between the Internet model and the OSI model is the separation of the application layer.

We can compare TCP/IP and OSI models as below:

| OSI Layer | OSI Name     | TCP/IP Layer   | Examples / Notes                        |
| --------- | ------------ | -------------- | --------------------------------------- |
| 7         | Application  | Application    | HTTP, FTP, SMTP                         |
| 6         | Presentation | Application    | Formatting, encryption, compression     |
| 5         | Session      | Application    | Session setup and management            |
| 4         | Transport    | Transport      | TCP (reliable), UDP (fast, best-effort) |
| 3         | Network      | Internet       | IP addressing and routing               |
| 2         | Data Link    | Network Access | Ethernet, ARP, MAC addressing           |
| 1         | Physical     | Network Access | Cables, signals, hardware               |

**Remark**:
MAC Address is a unique physical hardware address assigned to a network interface controller

---

### **3.TCP/IP Addressing**

TCP/IP is a method that identify the devices on a network using Internet Protocol (IP) addresses so data reaches the correct destination.
Today, we have 2 versions of IP that are IPv4 and IPv6.

#### IPv4 (Internet Protocol version 4)

A 32-bit IP addressing system written as 4-decimal numbers (e.g., `192.168.1.1`).

```
192.168.1.100
 │   │  │  │
 └───┴──┴──┴── Each octet: 0-255 (8 bits)
```

#### IPv6 (Internet Protocol version 6)

A 128-bit IP addressing system written as 32-hex numbers (e.g., `2001:0db8:85a3:0000:0000:8a2e:0370:7334`).

```
2001:0db8:85a3:0000:0000:8a2e:0370:7334
│    │    │    │    │    │    │    │
└────┴────┴────┴────┴────┴────┴────┴───── Each block: 0000–FFFF (16 bits, hexadecimal)
```

**Remark**:
For netpractice, we will focus on TPC/IP with IPv4.

#### Network and Host Portion

Generally, IP Address comprise of the network address and host address. The identifier that determine which part of an IP address identifies the network and which part identifies the host is called **subnet mask**.

For example,

- IP Address: 192.168.1.100
- Subnet Mask: 255.255.255.240

To derive the network/host addresses, we will bitwise operation in binary form as below:

```
IP              :   11000000.10101000.00000001.01100100
Subnet Mask     :   11111111.11111111.11111111.11110000
Network Address :   11000000.10101000.00000001.01100000
Host Address    :   00000000.00000000.00000000.00000100
```

#### Available/Usable IP

Furthermore, we can find the available IP (Max/Min IP) from above information:

```
IP              :   11000000.10101000.00000001.01100100
Subnet Mask     :   11111111.11111111.11111111.11110000
IP Min          :   11000000.10101000.00000001.01100000
IP Max          :   00000000.00000000.00000000.01101111
```

We can summarize that the minimum IP (192.168.96) is network address. The maximum IP (192.168.111) is the broadcast address. Both addresses can not be assigned with network interface.

#### CIDR Notation

CIDR (Classless Inter-Domain Routing) represent the subnet mask in shorten form with slash notation:

| CIDR | Subnet Mask     | Available IPs | Usable IPs    |
| ---- | --------------- | ------------- | ------------- |
| /30  | 255.255.255.252 | 4             | 2             |
| /29  | 255.255.255.248 | 8             | 6             |
| /28  | 255.255.255.240 | 16            | 14            |
| /27  | 255.255.255.224 | 32            | 30            |
| /26  | 255.255.255.192 | 64            | 62            |
| /25  | 255.255.255.128 | 128           | 126           |
| /24  | 255.255.255.0   | 256           | 254           |
| /23  | 255.255.254.0   | 512           | 510           |
| /22  | 255.255.252.0   | 1,024         | 1,022         |
| /21  | 255.255.248.0   | 2,048         | 2,046         |
| /20  | 255.255.240.0   | 4,096         | 4,094         |
| /19  | 255.255.224.0   | 8,192         | 8,190         |
| /18  | 255.255.192.0   | 16,384        | 16,382        |
| /17  | 255.255.128.0   | 32,768        | 32,766        |
| /16  | 255.255.0.0     | 65,536        | 65,534        |
| /15  | 255.254.0.0     | 131,072       | 131,070       |
| /14  | 255.252.0.0     | 262,144       | 262,142       |
| /13  | 255.248.0.0     | 524,288       | 524,286       |
| /12  | 255.240.0.0     | 1,048,576     | 1,048,574     |
| /11  | 255.224.0.0     | 2,097,152     | 2,097,150     |
| /10  | 255.192.0.0     | 4,194,304     | 4,194,302     |
| /9   | 255.128.0.0     | 8,388,608     | 8,388,606     |
| /8   | 255.0.0.0       | 16,777,216    | 16,777,214    |
| /7   | 254.0.0.0       | 33,554,432    | 33,554,430    |
| /6   | 252.0.0.0       | 67,108,864    | 67,108,862    |
| /5   | 248.0.0.0       | 134,217,728   | 134,217,726   |
| /4   | 240.0.0.0       | 268,435,456   | 268,435,454   |
| /3   | 224.0.0.0       | 536,870,912   | 536,870,910   |
| /2   | 192.0.0.0       | 1,073,741,824 | 1,073,741,822 |
| /1   | 128.0.0.0       | 2,147,483,648 | 2,147,483,646 |
| /0   | 0.0.0.0         | 4,294,967,296 | 4,294,967,294 |

#### Public/Private IP

A Public IP Address is assigned by your Internet Service Provider (or ISP). The private IP is established by network administration. These ranges are reserved for private networks:

| Range                         | Class | CIDR | Usage                |
| ----------------------------- | ----- | ---- | -------------------- |
| 10.0.0.0 - 10.255.255.255     | A     | /8   | Large organizations  |
| 172.16.0.0 - 172.31.255.255   | B     | /12  | Medium networks      |
| 192.168.0.0 - 192.168.255.255 | C     | /16  | Small networks/homes |
| 127.0.0.0 - 127.255.255.255   | -     | /8   | Loopback testing     |

### **4.Network Configuration**

Network configuration involves setting up network devices (IP, subnet mask, default gateway) to communicate, while subnetting breaks a large network into smaller, manageable subnetworks to improve security, traffic management, and IP efficiency. The important physical devices are:

- **Switches**: A Layer 2 device that connect devices within the same local network.
- **Routers**: A Layer 3 device that connect different networks and direct traffic between them.
- **Gateway**: A network device (usually a router) that acts as an entry and exit point for a network.

```
IP Address:     192.168.1.100
Subnet Mask:    255.255.255.0    (/24)
Network:        192.168.1.0
Host:           0.0.0.100
```

Default Gateways The doorway that connect from a local network to external networks.
Interface: A physical port or connection point on a network device.
Default Route (0.0.0.0/0): A routing table entry that acts as a "gateway of last resort" for unknown destinations.

Routing Table: A data table in a router that lists routes to network destinations.
Next Hop: The IP address of the next router a packet should be sent to on its path to the destination.

**Remark**:
default or 0.0.0.0/0 , we will focus on TPC/IP with IPv4.

[TCP/IP Protocol](https://www.a1.digital/knowledge-hub/tcp-ip-explained/)
