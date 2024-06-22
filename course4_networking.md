https://res.cloudinary.com/kodekloud/image/upload/v1702543781/course-resource-new/Networking-Basics.pdf

{ command for DNS: 
1. remote conf file: vi /etc/resolv.conf
2. local conf file: vi /etc/hosts }

( search yahoo.com - to add as extension for DNS to add in remote sonf file)

( nslookup command is used to query the DNS server)
   
## What is Networking?
Networking refers to the practice of connecting computers and other devices together to share resources, such as files, internet connections, and printers, as well as to enable communication. Networks can vary in size from a small home network to a large enterprise network and can include various types of devices like computers, servers, routers, switches, and more. Networking involves both hardware components (like cables, switches, routers, and network interface cards) and software components (like network protocols and operating systems).

# Key Concepts in Networking:
1 Network Topology: The arrangement of different elements (links, nodes, etc.) in a computer network. Common topologies include star, ring, bus, and mesh.

2 Protocols: Rules and conventions for communication between network devices. Examples include TCP/IP, HTTP, FTP, and SMTP.

3 Bandwidth: The maximum rate of data transfer across a given path. It is usually measured in bits per second (bps).

4 Latency: The time it takes for data to travel from the source to the destination. Lower latency is critical for real-time applications.

5 IP Addressing: A unique address assigned to each device on a network, allowing it to be identified and located.

6 Subnets: Smaller networks within a larger network, created to optimize performance and improve security.

7 Routing: The process of selecting paths in a network along which to send data packets.

8 Switching: The process of moving packets within the same network segment.

# What is an Interface in Networking?
In networking, an interface refers to a point of interaction between a computer and a network or between different network devices. It is the means through which devices connect and communicate with each other. An interface can be hardware-based (like a network interface card) or software-based (like a virtual network interface).

Key Characteristics of Network Interfaces:

• Uniqueness: Each network interface has a unique identifier, usually a MAC (Media Access Control) address for hardware interfaces.

• Configuration: Interfaces need to be configured with network settings like IP addresses, subnet masks, and default gateways.

• Types: Interfaces can be physical, such as Ethernet ports, or virtual, such as loopback interfaces.

## Types of Interfaces in Networking
# 1 Physical Interfaces:

◦ Ethernet: Commonly used in wired local area networks (LANs). Uses twisted pair or fiber optic cables. Examples include RJ45 connectors.

◦ Wireless: Interfaces for Wi-Fi connections using radio waves. Includes Wi-Fi adapters and antennas.

◦ Fiber Optic: Uses light to transmit data over long distances with high speed and low latency. Common connectors include SC, LC, and ST.

◦ Serial and Parallel Ports: Older interfaces used for direct connections between devices, often seen in legacy systems.

# 2 Virtual Interfaces:

◦ Loopback Interface: A virtual interface used by the system for internal communication. Typically uses the IP address 127.0.0.1.

◦ VLAN (Virtual Local Area Network): Allows network administrators to segment a physical network into multiple logical networks.

◦ VPN (Virtual Private Network): Creates a secure connection over a less secure network, such as the internet.

◦ Bridge Interface: Used to connect two or more network segments, making them act as a single network.

◦ Bonding or Teaming Interface: Combines multiple network interfaces into a single logical interface to increase bandwidth and provide redundancy.

3 Specialized Interfaces:

Management Interfaces: Used for administrative access to network devices, such as the console port on a router or switch.

Trunk Ports: Used to carry traffic for multiple VLANs between network devices.

Tunnel Interfaces: Used in tunneling protocols like GRE (Generic Routing Encapsulation) to encapsulate packets of one protocol inside another protocol.

## Examples of Network Interfaces:

# 1 Ethernet Interface (eth0, eth1, etc.):
◦ Typically used in wired networks.
◦ Configured with static or dynamic IP addresses.

# 2 Wireless Interface (wlan0, etc.):
◦ Used in wireless networks.
◦ Can be configured to connect to wireless access points using SSID and security protocols like WPA/WPA2.

# 3 Loopback Interface (lo):
◦ Used for testing and network diagnostics.
◦ Always available and not tied to any physical device.

# 4 Virtual Network Interface (tun0, tap0, etc.):
◦ Used in virtual networking, such as in VPNs or network emulation.
◦ Configured through software to represent network connections.

# Conclusion
Understanding networking and network interfaces is crucial for designing, implementing, and managing networks. Physical interfaces enable the physical connection of devices, while virtual interfaces provide flexibility and additional functionality such as network segmentation and secure communications. Effective use of both physical and virtual interfaces ensures robust, secure, and efficient network operations.

