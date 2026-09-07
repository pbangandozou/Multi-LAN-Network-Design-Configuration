Cisco Network Routing & Subnetting Lab

A Cisco Packet Tracer networking lab demonstrating IPv4 addressing, subnetting, switching, and routing by connecting two separate LANs through a central router.

Project Overview

This topology consists of two independent /24 networks connected through a router:

                 ┌─────────────────┐
                 │     Router      │
                 │  Inter-LAN      │
                 │    Routing      │
                 └───────┬─────────┘
                         │
            ┌────────────┴────────────┐
            │                         │
      192.168.1.0/24           192.168.2.0/24
            │                         │
      ┌─────┴─────┐             ┌─────┴─────┐
      │  Switch 0 │             │  Switch 1 │
      └─────┬─────┘             └─────┬─────┘
            │                         │
       PCs / Server /            PCs / Server /
          Printer                   Printer

Devices within each LAN communicate through their local switch. Traffic destined for the other subnet is forwarded to the router, which provides Layer 3 connectivity between the two networks.

Network Configuration

Network

Subnet Mask

Purpose

192.168.1.0/24

255.255.255.0

LAN 1

192.168.2.0/24

255.255.255.0

LAN 2

Each /24 network provides 254 usable IPv4 host addresses.

Devices

LAN 1 — 192.168.1.0/24

Cisco switch

Multiple PCs

Server

Printer

LAN 2 — 192.168.2.0/24

Cisco switch

Multiple PCs

Server

Printer

Routing

Central Cisco router

One interface serving each subnet

Key Concepts

IPv4 Addressing

Each device is assigned an IPv4 address appropriate for its subnet along with the 255.255.255.0 subnet mask.

Default Gateway

Hosts use the router interface on their local subnet as the default gateway. This allows them to forward traffic destined for devices outside their local network.

Switching

Each LAN uses a Layer 2 switch to connect local devices. Hosts on the same subnet can communicate through the switch without requiring the router.

Routing

The router connects the two separate IP networks:

192.168.1.0/24
       │
       ▼
    Router
       │
       ▼
192.168.2.0/24

This allows devices on 192.168.1.0/24 to communicate with devices on 192.168.2.0/24.

Connectivity Testing

Connectivity can be tested from the PCs using ping.

Same-Subnet Test

PC → Switch → PC

A successful ping between hosts on the same subnet confirms local Layer 2 connectivity and correct IP addressing.

Inter-Subnet Test

PC
 │
 ▼
Switch
 │
 ▼
Router
 │
 ▼
Switch
 │
 ▼
PC

A successful ping between the two subnets verifies that the router interfaces, IP addressing, subnet masks, and default gateways are configured correctly.

Troubleshooting Methodology

When a connection fails, the lab can be diagnosed layer by layer:

Physical Connectivity
        ↓
IP Address
        ↓
Subnet Mask
        ↓
Default Gateway
        ↓
Router Interface
        ↓
End-to-End Connectivity

Common checks include:

Verify Ethernet connections.

Confirm devices have addresses in the correct subnet.

Verify subnet masks.

Check the configured default gateway.

Confirm router interfaces are configured for the correct networks.

Use ping to identify where communication fails.

Skills Demonstrated

Cisco Packet Tracer

IPv4 addressing

Subnetting and CIDR

TCP/IP fundamentals

Layer 2 switching

Layer 3 routing

Default gateways

Router interface configuration

Network topology design

Connectivity testing

Network troubleshooting

Future Improvements

Potential additions to this lab include:

VLAN segmentation

Inter-VLAN routing

DHCP configuration

Static routing

OSPF dynamic routing

Access Control Lists (ACLs)

Additional subnets

Network redundancy

Network failure and troubleshooting scenarios

Full Cisco IOS configuration documentation

Project Purpose

The purpose of this project was to build hands-on experience with the fundamentals of network infrastructure and understand how addressing, switching, and routing work together to enable communication between systems.

This lab demonstrates the practical relationship between IP addressing and routing decisions and how those configurations determine whether traffic can successfully reach its destination.
