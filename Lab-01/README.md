# Lab 01 - Network and Active Directory Setup

## Objective
Set up Kali Linux, Windows Server, and Windows Client in VirtualBox.

## Lab Network
- Kali Linux: 192.168.56.102
- Windows Server: 192.168.56.10
- Windows Client: 192.168.56.101
- Domain: adlab.test
# Lab 01 — Network and Active Directory Setup

## Objective
Build an isolated cybersecurity lab using VirtualBox with Kali Linux, Windows Server, and Windows 10 Client.

## Lab Environment
- Virtualization: Oracle VirtualBox
- Attacker machine: Kali Linux
- Domain Controller: Windows Server
- Client machine: Windows 10
- Active Directory domain: `adlab.test`

## IP Addressing

| Machine | IP Address |
|---|---|
| Kali Linux | `192.168.56.102` |
| Windows Server | `192.168.56.10` |
| Windows Client | `192.168.56.101` |

Subnet mask: `255.255.255.0`

## Tasks Completed
- Configured the VirtualBox Host-Only network.
- Configured the Windows Server as an Active Directory domain controller.
- Configured DNS for `adlab.test`.
- Joined the Windows Client to the domain.
- Verified connectivity between the Windows Client and Server.
- Tested the Active Directory DNS SRV record.
- Located the domain controller using `nltest`.

## Verification Commands

### Kali Linux
```bash
ip addr
ping -c 4 192.168.56.10
```

### Windows Client
```cmd
ipconfig
ping 192.168.56.10
whoami
nslookup -type=SRV _ldap._tcp.dc._msdcs.adlab.test 192.168.56.10
nltest /dsgetdc:adlab.test
```

## Evidence
Screenshots will be added to document IP configuration, connectivity, DNS, and domain membership.

## Learning Outcome
Practised basic network configuration, DNS resolution, Active Directory domain joining, and domain controller discovery in an isolated lab.
