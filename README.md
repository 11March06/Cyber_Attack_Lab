# Cyber_Attack_Lab
A lab environment for simulating and analyzing cyber attacks, designed for learning, testing, and improving security defenses.

Cyber Security Monitoring & Detection Lab : 
<img width="1142" height="612" alt="image" src="https://github.com/user-attachments/assets/7097c22f-5592-434e-b301-0b4f1fc3c8c4" />
| **Role** | **OS / ISO / VMDK** | **Description** |
|--------------|--------------------------------|----------------|
| Firewall | pfSense-CE-2.6.0-RELEASE-amd64.iso | Open-source firewall, managing traffic and securing the network |
| PC1 | Win11 x64 Pro 2022.iso | User workstation, simulating an endpoint |
| ADC | Server 2019 En Jun 2020.iso | Active Directory server, managing domains and users |
| Kali | kali-linux-2023.2.vmdk | Pentesting operating system, packed with attack and exploitation tools |
| SecOnion | securityonion-2.3.250-20230519.iso | Network security monitoring system, for detection and analysis |
| Metasploitable | Metasploitable 2.vmdk | Vulnerable virtual machine, used for exploitation practice |
| Splunk | Ubuntu Server 22.10 (64bit).vmdk | Log collection and analysis server, for monitoring and SIEM tasks |
| MGMT | Host System Windows 11 | Management host, controlling the entire lab |

**Network roles and subnets/IPs**
| **Component**              | **Subnet / IP Address**      | **Description** |
|-----------------------------|------------------------------|-----------------|
| External Subnet             | 192.168.114.0/24             | External-facing network segment |
| Internal LAN Subnet         | 192.168.1.0/24               | Internal corporate/local network |
| SPAN Port                   | No IP Address                | Mirror port for traffic monitoring |
| Attacker Subnet             | 192.168.3.0/24               | Network segment for attack simulation |
| Security Onion Logs Subnet  | 192.168.4.0/24               | Segment dedicated to log collection |
| Splunk Log Collector Subnet | 192.168.5.0/24               | Segment for Splunk log ingestion |
| Metasploitable              | DHCP                         | Vulnerable VM with dynamic IP |
| ADC (Domain Controller)     | 192.168.1.100                | Active Directory server |
| PC1 (Workstation)           | 192.168.1.10                 | User endpoint |
| Attacker VM                 | DHCP                         | Pentesting/attack machine |
| Splunk Server               | DHCP                         | Log analysis server |
| Security Onion Sensor       | 192.168.114.50               | Security Onion monitoring node |
| Security Onion MGMT         | 192.168.114.1                | Management interface for Security Onion |
| DNS Servers                 | 8.8.8.8, 4.4.4.4             | External DNS resolution |

**VMware & pfSense Interface Mapping**
| **VMware Adapter** | **Network Connection** | **Role** | **pfSense Interface** |
|--------------------|------------------------|-----------|-----------------------|
| Network Adapter 1  | NAT                    | WAN       | EM0                   |
| Network Adapter 2  | VMNet2                 | LAN       | EM1                   |
| Network Adapter 3  | VMNet3                 | SPAN      | EM2                   |
| Network Adapter 4  | VMNet4                 | KALI      | EM3                   |
| Network Adapter 5  | VMNet5                 | SECURITY ONION | EM4              |
| Network Adapter 6  | VMNet6                 | SPLUNK    | EM5                   |

**Subnet & Interface Overview**
| **IP Subnet**      | **Network Connection** | **Role** | **pfSense Interface** | **VMware Adapter** |
|--------------------|------------------------|-----------|-----------------------|--------------------|
| 192.168.114.0/24   | NAT                    | WAN       | EM0                   | Network Adapter 1  |
| 192.168.1.0/24     | VMNet2                 | LAN       | EM1                   | Network Adapter 2  |
| No IP Address       | VMNet3                 | SPAN      | EM2                   | Network Adapter 3  |
| 192.168.3.0/24     | VMNet4                 | KALI      | EM3                   | Network Adapter 4  |
| 192.168.4.0/24     | VMNet5                 | SECURITY ONION | EM4              | Network Adapter 5  |
| 192.168.5.0/24     | VMNet6                 | SPLUNK    | EM5                   | Network Adapter 6  |

