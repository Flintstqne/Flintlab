# Asset Inventory

**Network:** 192.168.1.0/24

## Physical devices
 
| Hostname | Device | Role | IP | OS |
|---|---|---|---|---|
| flintstqne-pc | Main Laptop | Proxmox hypervisor | 192.168.1.10 | Dual boot — Windows / MintOS (Proxmox VE) |
| flintstqne-work | ThinkPad | Attack simulation and NSM | 192.168.1.20 | Windows |
| log-monitor | Raspberry Pi | Monitoring stack | 192.168.1.30 | Raspberry Pi OS |


## Virtual machines

| Hostname | Device | Role | IP | OS |
|---|---|---|---|---|
| flintstqne-pc | Main Laptop | Proxmox hypervisor | 192.168.1.10 | Dual boot — Windows / Linux (Proxmox VE) |
| flintstqne-work | ThinkPad | Attack simulation and NSM | 192.168.1.20 | Dual boot |
| log-monitor | Raspberry Pi | Monitoring stack | 192.168.1.30 | Raspberry Pi OS 

## Software and services

| Service | Host | Purpose | Port(s) |
|---|---|---|---|
| Active Directory | win-server | Identity and access management | 389, 636 |
| DNS | win-server | Name resolution | 53 |
| DHCP | win-server | IP address assignment | 67, 68 |
| Wazuh SIEM | Main Laptop (Proxmox) | Log aggregation and alerting | 1514, 1515, 55000 |
| Security Onion | ThinkPad | Network security monitoring | — |
| Suricata | ThinkPad | Intrusion detection | — |
| Zeek | ThinkPad | Network analysis | — |
| Kibana | ThinkPad | Log visualization | 5601 |
| Kali Linux | ThinkPad | Attack simulation | — |
| Atomic Red Team | ThinkPad | ATT&CK-mapped attack simulation | — |
| Prometheus | Raspberry Pi | Metrics collection | 9090 |
| Grafana | Raspberry Pi | Dashboards and alerting | 3000 |
| Uptime Kuma | Raspberry Pi | Availability monitoring | 3001 |

## Notes

- IP addresses are placeholders. Update with actual assigned addresses as you build each phase.
- Ports listed are defaults. Update if you change them during setup.
- Add RAM, CPU, and storage specs to the physical devices table once confirmed.


