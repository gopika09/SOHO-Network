# SOHO Network Implementation

The Small Office/Home Office (SOHO) Network Implementation project aims to design and configure a reliable and efficient network 
infrastructure for a simulated organization. This project focuses on segmenting the network using Virtual LANs (VLANs) to enhance 
performance, security, and management.

## Overview :
![diagram](https://github.com/gopika09/SOHO-Network/blob/main/SOHO%20diagram.png)

## Features 
- ​**Efficient IP Addressing and Subnetting**: Designed to optimize network performance and minimize IP waste by carefully planning IP address allocation and subnetting strategies.
- **Inter-VLAN Routing**: Configured to allow seamless communication between different VLANs, enabling secure and efficient data transfer between departments or network segments.
- **VLAN Segmentation**: Divides the network into multiple VLANs, improving network security and reducing broadcast traffic within the network.
- **Network Scalability**: Easily scalable, allowing for the addition of new VLANs or devices as the organization grows, without the need for major changes to the infrastructure.
- **Cisco Packet Tracer Simulation**: The network was designed and implemented in Cisco Packet Tracer, providing a virtual environment to simulate real-world network scenarios and configurations

## Tools and Technologies

- **Cisco Packet Tracer**: Used for simulation and visualization of the network setup.
- **Cisco Routers and Switches**: For configuration and implementation of VLANs, DHCP, and inter-VLAN routing.
- **Subnetting and Networking Protocols**: Knowledge of TCP/IP, VLANs, and DHCP was essential for design and configuration.

## Steps to Deploy

In this project, I have created three key departments: **Admin**, **Finance**, and **Reception**, each requiring its own secure network. The challenge was to ensure seamless communication between the departments while maintaining network isolation for security. The goal was to design and implement a reliable and efficient network infrastructure to meet the company's needs using **Cisco Packet Tracer**.


## Step 1: Planning the Network

In this project, I have created three key departments: Admin, Finance, and Reception, and each department needs its own secure network. The challenge is to ensure seamless communication between these departments while keeping their networks isolated for security purposes. As the network engineer, my task is to design and implement a reliable and efficient network infrastructure to meet the company’s needs using Cisco Packet Tracer.

I started by laying out the network plan. Each department required its own subnet, so I took the base network of 192.168.1.0/24 and split it into smaller subnets. Since I needed three subnets, I borrowed 2 bits from the host portion, creating a new subnet mask of 255.255.255.192. This provided three subnets, one for each department:

- **Admin Subnet:**
  - Network ID: `192.168.1.0`
  - Host Range: `192.168.1.1 - 192.168.1.62`

- **Finance Subnet:**
  - Network ID: `192.168.1.64`
  - Host Range: `192.168.1.65 - 192.168.1.126`

- **Reception Subnet:**
  - Network ID: `192.168.1.128`
  - Host Range: `192.168.1.129 - 192.168.1.190`



## Step 2: Configuring the Router for Inter-VLAN Communication

To ensure each department could communicate with one another while maintaining their own subnet, I configured inter-VLAN routing on the router.
I logged into the router and began by configuring subinterfaces for each VLAN:

- **VLAN 10 (Admin):** `192.168.1.1`
- **VLAN 20 (Finance):** `192.168.1.65`
- **VLAN 30 (Reception):** `192.168.1.129`

Additionally, **DHCP services** were enabled on the router to automatically assign IP addresses to devices in each VLAN, simplifying device management.Now, Admin, Finance, and Reception each had their own IP pool, making device management more streamlined.



## Step 3: Configuring the Switch for VLAN Segmentation

Next, I moved on to the switch, where I assigned specific ports to each VLAN. For example:

- **Ports Fa0/2-4** were assigned to **VLAN 10 (Admin)**
- **Ports Fa0/5-7** were assigned to **VLAN 20 (Finance)**
- **Ports Fa0/8-10** were assigned to **VLAN 30 (Reception)**

I then configured a trunk port on Fa0/1 to connect the switch to the router. The trunk port allowed traffic from all VLANs to pass through, ensuring that inter-VLAN communication was possible via the router.



## Step 4: Testing the Setup

With everything configured, it was time to test the network. I connected devices to the appropriate VLAN ports and verified that they received the correct IP addresses from the DHCP server. I also tested communication between VLANs to ensure that the Admin team could communicate with Finance and Reception, as required. I ran several ping tests from devices in one VLAN to devices in another, and it worked perfectly. The inter-VLAN routing I configured on the router was functioning as expected, and the departments could now communicate seamlessly.


## Conclusion

The SOHO Network Implementation project successfully demonstrated the importance of proper network segmentation and management in a 
small office environment. By utilizing VLANs and effective routing techniques, the project ensured improved security and performance. 
This experience reinforced the understanding of networking concepts and the practical application of Cisco configuration commands, 
providing a solid foundation for future networking endeavors.
