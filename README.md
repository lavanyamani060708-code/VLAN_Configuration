# VLAN Configuration Using Cisco Packet Tracer

## Aim
To create and configure two Virtual Local Area Networks (VLANs) using a Cisco 2960 switch and test network communication between computers.

## Software Required
- Cisco Packet Tracer

## Devices Used
- 4 PCs
- 1 Cisco 2960 Switch
- 4 Copper Straight-Through cables

## Network Topology
The network contains four PCs connected to a central Cisco 2960 switch. The switch ports are assigned to two separate VLANs.

- **VLAN 10 – STUDENTS:** PC0 and PC1
- **VLAN 20 – STAFF:** PC2 and PC3

## IP Address Configuration

| Device | VLAN | IP Address | Subnet Mask |
|---|---|---|---|
| PC0 | VLAN 10 | 192.168.10.1 | 255.255.255.0 |
| PC1 | VLAN 10 | 192.168.10.2 | 255.255.255.0 |
| PC2 | VLAN 20 | 192.168.20.1 | 255.255.255.0 |
| PC3 | VLAN 20 | 192.168.20.2 | 255.255.255.0 |

## Switch Port Assignment

| Switch Port | Connected PC | VLAN |
|---|---|---|
| FastEthernet0/1 | PC0 | VLAN 10 |
| FastEthernet0/2 | PC1 | VLAN 10 |
| FastEthernet0/3 | PC2 | VLAN 20 |
| FastEthernet0/4 | PC3 | VLAN 20 |

## Configuration Commands

The following commands create the VLANs and assign switch ports:

```text
enable
configure terminal

vlan 10
name STUDENTS
exit

vlan 20
name STAFF
exit

interface range fa0/1-2
switchport mode access
switchport access vlan 10
exit

interface range fa0/3-4
switchport mode access
switchport access vlan 20
exit

end
show vlan brief
```

## Testing

### Test 1: Communication within VLAN 10

From PC0, run:

`ping 192.168.10.2`

### Test 2: Communication within VLAN 20

From PC2, run:

`ping 192.168.20.2`

### Test 3: Communication between VLANs

From PC0, run:

`ping 192.168.20.1`

Without a router or Layer 3 switch configured for inter-VLAN routing, communication between VLAN 10 and VLAN 20 is not expected to succeed.

## Advantages
- Separates devices into logical networks.
- Improves network organization.
- Helps isolate traffic between different groups.
- Supports better network management.

## Result
Two VLANs, STUDENTS and STAFF, are configured using a Cisco 2960 switch. Network connectivity is tested using the ping command.

## Project File
`VLAN_Configuration.pkt`

## Author
GitHub: [lavanyamani060708-code](https://github.com/lavanyamani060708-code)
