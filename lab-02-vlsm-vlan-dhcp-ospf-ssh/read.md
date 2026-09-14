# Lab 02 – VLSM, VLAN, DHCP, OSPF & Secure SSH Network

## Objective

Designed and configured a small company network using Cisco Packet Tracer.

## Network Scenario

- 2 Routers
- 2 Switches
- IT – 20 PCs
- HR – 10 PCs
- Finance – 6 PCs
- Admin – 5 PCs

## VLSM Addressing

Base Network: 192.168.20.0/24

| Department | CIDR | Network | Gateway | Broadcast |
|---|---|---|---|---|
| IT | /27 | 192.168.20.0 | 192.168.20.1 | 192.168.20.31 |
| HR | /28 | 192.168.20.32 | 192.168.20.33 | 192.168.20.47 |
| Finance | /28 | 192.168.20.48 | 192.168.20.49 | 192.168.20.63 |
| Admin | /29 | 192.168.20.64 | 192.168.20.65 | 192.168.20.71 |
| R0-R1 | /30 | 192.168.20.72 | R0: .73 / R1: .74 | 192.168.20.75 |

## VLAN Configuration

| VLAN | Department | Switch |
|---|---|---|
| 10 | IT | S0 |
| 20 | HR | S1 |
| 30 | Finance | S1 |
| 40 | Admin | S1 |

## DHCP

DHCP was configured on both routers to automatically provide:

- IP Address
- Subnet Mask
- Default Gateway
- DNS Server

DNS Server: 8.8.8.8

## Router-on-a-Stick

### R0

- Fa0/1.10
- VLAN 10 – IT
- Gateway: 192.168.20.1/27

### R1

- Fa0/1.20
- VLAN 20 – HR
- Gateway: 192.168.20.33/28

- Fa0/1.30
- VLAN 30 – Finance
- Gateway: 192.168.20.49/28

- Fa0/1.40
- VLAN 40 – Admin
- Gateway: 192.168.20.65/29

## OSPF

Configured OSPF between R0 and R1 using Area 0.

R0-R1 Link:

- R0: 192.168.20.73/30
- R1: 192.168.20.74/30

OSPF neighbor relationship successfully reached FULL.

## SSH

Configured secure remote management using SSH Version 2.

Configured:

- Hostname
- Domain Name
- Local Username
- RSA Keys
- SSH Version 2
- VTY Lines
- Local Authentication
- SSH-only remote access

## SSH Security with ACL

Authorized Admin PC:

192.168.20.66

ACL was configured to allow SSH access only from the authorized Admin PC.

access-list 10 permit host 192.168.20.66
line vty 0 4
access-class 10 in

## Verification

- DHCP address assignment – Successful
- VLAN configuration – Successful
- R0-R1 connectivity – Successful
- OSPF neighbor – FULL
- Inter-network ping – Successful
- SSH from Admin PC – Successful
- SSH access control using ACL – Successful

## Skills Practiced

- VLSM Subnetting
- IPv4 Addressing
- VLANs
- Trunking
- Router-on-a-Stick
- DHCP
- OSPF
- SSH
- RSA Keys
- VTY Configuration
- ACL
- Network Troubleshooting
- Cisco IOS CLI
- Cisco Packet Tracer

## Key Learning

This lab demonstrates how multiple networking and security concepts work together:

VLSM → VLAN → DHCP → Inter-VLAN Routing → OSPF → SSH → ACL

## Tools Used

- Cisco Packet Tracer
- Cisco IOS CLI
