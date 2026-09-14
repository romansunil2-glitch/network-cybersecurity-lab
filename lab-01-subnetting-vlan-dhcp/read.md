# Lab 01 - Small Company Network

## Scenario

A small company has two departments:

- IT: 5 PCs + 1 Printer
- HR: 5 PCs + 1 Printer

Network: 192.168.10.0/24

## Network Design

### IT Department

VLAN: 10
Network: 192.168.10.0/28
Gateway: 192.168.10.1
Subnet Mask: 255.255.255.240
Broadcast: 192.168.10.15

### HR Department

VLAN: 20
Network: 192.168.10.16/28
Gateway: 192.168.10.17
Subnet Mask: 255.255.255.240
Broadcast: 192.168.10.31

## Technologies Used

- IP Addressing
- Subnetting
- VLAN
- DHCP
- Router-on-a-Stick
- Inter-VLAN Routing
- Cisco Packet Tracer

## Result

Both IT and HR devices successfully received IP addresses through DHCP
and were able to communicate through the router.
