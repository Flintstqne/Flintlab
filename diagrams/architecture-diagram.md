# Cybersecurity Homelab — Architecture Diagram

**Network:** 192.168.1.0/24

```mermaid
graph LR
    Router["Home Router\n192.168.1.1"]

    Router --> L1["Main Laptop\nProxmox — 192.168.1.10"]
    Router --> TP["ThinkPad\n192.168.1.20"]
    Router --> PI["Raspberry Pi\n192.168.1.30"]

    L1 --> WS["Windows Server 2022\nAD · DNS · DHCP · GPO"]
    L1 --> W11["Windows 11\nWorkstation"]
    L1 --> UB["Ubuntu Server"]
    L1 --> SIEM["Wazuh SIEM"]

    WS -.-> SIEM
    W11 -.-> SIEM
    UB -.-> SIEM

    TP --> SO["Security Onion\nSuricata · Zeek · Kibana"]
    TP --> KL["Kali Linux\nAtomic Red Team"]
    TP --> ATT["MITRE ATT&CK\nmapping"]

    PI --> PROM["Prometheus\nMetrics collection"]
    PI --> GRAF["Grafana\nDashboards"]
    PI --> KUMA["Uptime Kuma\nAvailability"]

    PROM -.->|scrapes| L1
    SO -.->|monitors| Router
    KL -.->|simulates attacks| L1

    style Router fill:#f0f0f0,stroke:#999,color:#111
    style L1 fill:#ddeaf6,stroke:#7aafd4,color:#1a3a52
    style WS fill:#edf4fb,stroke:#7aafd4,color:#1a3a52
    style W11 fill:#edf4fb,stroke:#7aafd4,color:#1a3a52
    style UB fill:#edf4fb,stroke:#7aafd4,color:#1a3a52
    style SIEM fill:#e8e4f8,stroke:#7b6cc4,color:#3c2e82
    style TP fill:#fae7e0,stroke:#d4896a,color:#5a2210
    style SO fill:#fdf0eb,stroke:#d4896a,color:#5a2210
    style KL fill:#fdf0eb,stroke:#d4896a,color:#5a2210
    style ATT fill:#fce8f0,stroke:#b05080,color:#6a1a38
    style PI fill:#d8f0e6,stroke:#5aaa82,color:#0a4428
    style PROM fill:#ecf8f2,stroke:#5aaa82,color:#0a4428
    style GRAF fill:#ecf8f2,stroke:#5aaa82,color:#0a4428
    style KUMA fill:#ecf8f2,stroke:#5aaa82,color:#0a4428
```

## Device inventory

| Device | Role | IP | Key software |
|---|---|---|---|
| Main Laptop (Proxmox) | Enterprise environment | 192.168.1.10 | Windows Server 2022, Windows 11, Ubuntu Server, Wazuh SIEM |
| ThinkPad | Attack simulation and NSM | 192.168.1.20 | Security Onion, Kali Linux, Atomic Red Team |
| Raspberry Pi | Monitoring | 192.168.1.30 | Grafana, Prometheus, Uptime Kuma |

## Traffic key

| Line | Meaning |
|---|---|
| Solid arrow | Direct control or data flow |
| Dashed arrow | Monitoring or simulated attack traffic |