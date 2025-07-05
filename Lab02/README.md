# <p align='center'> Configuring a Switch Management Address </p>
## Topology
<p align='center'>

| |
|-----|
| ![Topology](topology.jpg) |

</p>

## Addressing Table 
| Device | Interface | IP Address   | Subnet Mask   |
|--------|-----------|--------------|---------------|
| S1     | VLAN 1    | 192.168.1.2  | 255.255.255.0 |
| PC0    | NIC       | 192.168.1.10 | 255.255.255.0 |

## Objectives 
Part 1: Configure a Basic Network Device 
Part 2: Verify and Test Network Connectivity 

## Background / Scenario 
Cisco switches have a special interface, known as a switch virtual interface (SVI). The SVI can be configured 
with an IP address, commonly referred to as the management address. The management address is used for 
remote access to the switch to display or configure settings. 
In this lab, you will build a simple network using Ethernet LAN cabling and access a Cisco switch using the 
console and remote access methods. You will configure basic switch settings, IP addressing, and 
demonstrate the use of a management IP address for remote switch management. The topology consists of 
one switch and one host using only Ethernet and console ports. 

> [!NOTE]
>  The switches used are Cisco Catalyst 2960s with Cisco IOS Release 15.0(2) (lanbasek9 image). Other 
switches and Cisco IOS versions can be used. Depending on the model and Cisco IOS version, the available 
commands and output produced might vary from what is shown in the labs. 

> [!NOTE]
>  Make sure that the switch has been erased and has no startup configuration. If you are unsure, contact 
your instructor.

## Required Resources 
- 1 Switch (Cisco 2960 with Cisco IOS Release 15.0(2) lanbasek9 image or comparable) 
- 1 PC (Windows 7 or 8 with terminal emulation program, such as Tera Term) 
- Console cables to configure the Cisco IOS devices via the console ports 
- Ethernet cables as shown in the topology