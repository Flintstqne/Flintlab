# Network Layout

## Overview

| Property | Value |
|---|---|
| Network | 192.168.1.0/24 |
| Subnet mask | 255.255.255.0 |
| Gateway | 192.168.1.1 |
| DNS | 192.168.1.11 (Windows Server 2022) |
| DHCP | 192.168.1.11 (Windows Server 2022) |

## IP address assignments

| IP | Device | Role |
|---|---|---|
| 192.168.1.1 | Home router | Gateway |
| 192.168.1.10 | Laptop 1 (Proxmox) | Hypervisor host |
| 192.168.1.11 | Windows Server 2022 (VM) | Domain controller, DNS, DHCP |
| 192.168.1.12 | Windows 11 (VM) | Workstation |
| 192.168.1.13 | Ubuntu Server (VM) | Linux host |
| 192.168.1.20 | ThinkPad | Attack simulation and NSM |
| 192.168.1.30 | Raspberry Pi | Monitoring stack |

## Proxmox network configuration

Proxmox uses a Linux bridge (`vmbr0`) to connect VMs to the home network. All VMs receive IPs in the 192.168.1.0/24 range and are reachable from other devices on the network.

| Bridge | Interface | Purpose |
|---|---|---|
| vmbr0 | Physical NIC | Bridges VMs to home network |

## Traffic flows

| Source | Destination | Protocol | Purpose |
|---|---|---|---|
| Windows 11, Ubuntu Server, Windows Server | Wazuh SIEM | TCP 1514, 1515 | Log forwarding |
| Wazuh SIEM | All agents | TCP 55000 | Agent management |
| Prometheus | All hosts | TCP 9090 | Metrics scraping |
| Grafana | Prometheus | TCP 9090 | Dashboard data |
| Uptime Kuma | All hosts | ICMP / TCP | Availability checks |
| Security Onion | Network | Promiscuous mode | Passive traffic capture |
| Kali Linux | Lab hosts | Various | Attack simulation |

## Notes

- All devices are on a flat network with no VLANs. VLANs can be added in a later phase if network segmentation becomes a goal.
- Static IPs are assigned manually on each device. Update this file if any addresses change.
- Security Onion runs in promiscuous mode on the ThinkPad NIC to capture all traffic on the network segment.
- The Wazuh SIEM runs as a VM on the Proxmox host. Agents on Windows Server, Windows 11, and Ubuntu Server forward logs to it over the local network.