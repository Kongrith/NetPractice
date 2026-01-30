_This project has been created as part of the 42 curriculum by khkomasa_

<!--HEADER-->
<!-- <h1 align="center"> NetPractice | 
  <picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://cdn.simpleicons.org/42/white">
  <img alt="42" width=40 align="center" src="https://cdn.simpleicons.org/42/Black">
 </picture>
 Cursus
  <img alt="Complete" src="https://raw.githubusercontent.com/Mqxx/GitHub-Markdown/main/blockquotes/badge/dark-theme/complete.svg">
</h1> -->

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

### Networking Concepts

- [1] [An Intro to IP Addresses and Subnets](https://www.youtube.com/watch?v=HQUw0CfQWAM)
- [2] [An Intro to IP Addresses and Subnets](https://www.youtube.com/watch?v=HQUw0CfQWAM)

#### Definitions

- **TCP/IP Addressing**  
  A method for identifying devices on a network using IP addresses so data reaches the correct destination.

- **IPv4**  
  A 32-bit IP addressing system written as four decimal numbers (e.g., `192.168.1.1`).

- **Subnet Masks**  
  Values that determine which part of an IP address identifies the network and which part identifies the host.

- **Default Gateways**  
  The router that forwards traffic from a local network to external networks.

- **Routing**  
  The process of choosing paths and forwarding data packets between networks.

- **Routers and Switches**
  - **Switches** connect devices within the same local network.
  - **Routers** connect different networks and direct traffic between them.

- **OSI Model Basics**  
  A seven-layer model describing how data moves from physical transmission to user applications.

#### Network Configuration

Network configuration involves setting up network devices (IP, subnet mask, gateway) to communicate, while subnetting breaks a large network into smaller, manageable subnetworks to improve security, traffic management, and IP efficiency. Key concepts include using subnet masks (e.g., /24, 255.255.255.0) to divide IP addresses into network and host portion.

| Layer | Name               | Protocols       | Function                     |
| ----- | ------------------ | --------------- | ---------------------------- |
| 4     | **Application**    | HTTP, FTP, SMTP | User services and interfaces |
| 3     | **Transport**      | TCP, UDP        | Reliable data delivery       |
| 2     | **Internet**       | IP, ICMP        | Routing and addressing       |
| 1     | **Network Access** | Ethernet, Wi-Fi | Physical data transmission   |

| OSI Layer | OSI Name     | TCP/IP Layer   | Examples / Notes                        |
| --------- | ------------ | -------------- | --------------------------------------- |
| 7         | Application  | Application    | HTTP, FTP, SMTP, DNS                    |
| 6         | Presentation | Application    | Formatting, encryption, compression     |
| 5         | Session      | Application    | Session setup and management            |
| 4         | Transport    | Transport      | TCP (reliable), UDP (fast, best-effort) |
| 3         | Network      | Internet       | IP addressing and routing               |
| 2         | Data Link    | Network Access | Ethernet, ARP, MAC addressing           |
| 1         | Physical     | Network Access | Cables, signals, hardware               |
