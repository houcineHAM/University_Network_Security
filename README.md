# **Martin Luther King University Network Design**

## Overview

This repository contains the network design and implementation plan for Martin Luther King University. The goal is to create a secure, reliable, scalable, and robust network system that supports the university’s operations, ensuring confidentiality, integrity, and availability while maintaining top-tier performance, redundancy, and scalability.

The design focuses on creating a seamless communication and secure access for users across two campuses, supporting academic and administrative needs. It covers the integration of various technologies such as firewalls, wireless infrastructure, VPNs, and cloud services.

## Acknowledgements

This project was completed with the help of a **YouTube tutorial**. Special thanks to [Gurutech Networking Training](https://www.youtube.com/watch?v=VrfhC9qpN64&t=2349s&ab_channel=GurutechNetworkingTraining) for the detailed walkthrough and guidance throughout the process.

## Table of Contents

- [Key Network Components](#key-network-components)
- [Network Topology](#network-topology)
- [IP Addressing Scheme](#ip-addressing-scheme)
- [Technologies Implemented](#technologies-implemented)
- [Design Tool](#design-tool)
- [Implementation Steps](#implementation-steps)
- [Testing and Verification](#testing-and-verification)
- [Contributions](#contributions)
- [License](#license)

## Key Network Components

- **ISP (Internet Service Provider):** Airtel
- **Firewalls:** Cisco ASA 5500-X series firewalls (one per campus)
- **Switches:**
  - Catalyst 3850 48-Port Switches for both campuses
  - Catalyst 2960 48-Port Switches for each faculty
- **Server Hardware & Virtualization:** Two physical servers running hypervisors to create virtual machines for various services
- **Wireless LAN Controllers (WLC):** Two Cisco Wireless LAN Controllers to manage wireless access points
- **VPN:** Site-to-site IPsec VPN for secure communication between campuses
- **Cloud Connectivity:** Integration with Google Cloud platform for access to university services and resources

## Network Topology

The network design follows a hierarchical model with redundancy and high availability. Key components include:
- A central server farm (DMZ) at the main campus for critical services such as DHCP, DNS, FTP, Web, Email, and SMTP.
- Secure, segregated VLANs for management, voice, WLAN, and LAN traffic.
- Wireless infrastructure with centralized management for seamless Wi-Fi access.
- Site-to-site IPsec VPN to ensure secure communication between the campuses.

You can view the network topology by referring to the network diagram in the source files.

## IP Addressing Scheme

- **WLAN:** 192.168.10.0/24
- **LAN:**
  - Main Campus: 10.10.0.0/16
  - Branch Campus: 10.11.0.0/16
- **Voice:**
  - Main Campus: 172.16.0.0/16
  - Branch Campus: 172.17.0.0/16
- **DMZ:** 10.20.20.0/27
- **Public IPs:**
  - Main Campus: 105.100.50.0/30
  - Branch Campus: 205.200.100.0/30

## Technologies Implemented

- **Routing Protocol:** OSPF (Open Shortest Path First) for inter-campus routing
- **DHCP:** Dynamic IP addressing from the central server farm for all devices
- **VoIP:** IP phones configured for Voice over IP communication
- **VLANs:** Separated VLANs for management, LAN, WLAN, and blackhole ports
- **EtherChannel:** Link Aggregation using LACP for efficient bandwidth management
- **Security:** Cisco ASA firewalls, standard ACL for SSH, and Site-to-Site IPsec VPN
- **High Availability:** HSRP for router redundancy and failover

## Design Tool

The network design was created using **Cisco Packet Tracer**. You can find the source file for the design in this repository.

## Implementation Steps

1. **Configure Firewalls:** Set up Cisco ASA firewalls at both campuses with basic security policies and VPN configuration.
2. **Set up Network Switches:** Configure Catalyst switches for Layer 2 connectivity, including VLANs and EtherChannel.
3. **Configure Routing:** Set up OSPF routing across the network to enable communication between campuses.
4. **Implement Wireless Infrastructure:** Configure the Wireless LAN Controllers and Access Points for wireless network access.
5. **Set up Server Farm (DMZ):** Configure DHCP, DNS, FTP, Web, and other essential services within the DMZ.
6. **Test VPN Connectivity:** Ensure secure Site-to-Site IPsec VPN communication between campuses.
7. **Verify Network Communication:** Conduct thorough testing to ensure proper inter-VLAN routing, connectivity, and failover mechanisms.

## Testing and Verification

The network has been thoroughly tested for functionality and security. Tests include:
- **Ping Tests:** To verify connectivity between network devices and campuses.
- **Security Checks:** Ensuring proper firewall configurations and VPN tunnel operation.
- **VoIP Test:** Verifying the functionality of IP phones and voice communication.
- **Wireless Testing:** Ensuring proper access and coverage for wireless clients.

## Contributions

Feel free to contribute to this project by submitting issues, pull requests, or suggestions for improvement. This repository is open for collaboration!

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

### How to Use This Repository

1. Clone the repository:
   ```bash
   git clone https://github.com/username/repository-name.git
