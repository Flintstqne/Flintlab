# FlintLab

A personal home SOC environment built to develop hands-on skills in enterprise IT, security monitoring, threat detection, and incident response. Each phase has a specific focus and a clear set of things I want to walk away knowing how to do.

---

## Repository structure

```
/diagrams            architecture diagrams
/documentation       network layout, asset inventory, setup notes
/incident-reports    one report per attack simulation
/detection-rules     custom Wazuh and Suricata rules
/screenshots         evidence and portfolio material
```

---

## Phase 0: Planning and documentation

Before touching any hardware, I want to have a clear picture of what I'm building and why. This phase is about getting organized so I'm not making decisions on the fly later.

What I want to walk away with:
- A GitHub repo I can point to from day one
- An architecture diagram that accurately reflects my setup
- A documented network layout and asset inventory I can maintain as the lab grows
- A clear understanding of what each phase is trying to teach me

---

## Phase 1: Enterprise environment

Most companies run Windows Server, Active Directory, and a mix of Windows and Linux endpoints. I want to get comfortable administering these systems before I ever have to touch them in a professional setting.

What I want to walk away with:
- The ability to set up and manage an Active Directory domain from scratch
- An understanding of how DNS and DHCP work in an enterprise context
- Confidence working with Group Policy to control user and machine settings
- Basic Linux administration skills alongside Windows

---

## Phase 2: Centralized monitoring

Monitoring is something I've had no real exposure to. I want to understand how infrastructure health is tracked in real environments and what it looks like when something goes wrong before an alert fires.

What I want to walk away with:
- The ability to set up Grafana and Prometheus and connect them to real hosts
- An understanding of what metrics matter and why
- Custom dashboards I built myself showing CPU, memory, and availability
- A feel for what "normal" looks like so I recognize when things deviate

---

## Phase 3: SIEM deployment

Log collection is at the core of almost every SOC role. I want to understand how logs are gathered, normalized, and searched so I'm not learning that on the job.

What I want to walk away with:
- A working Wazuh SIEM with agents deployed across Windows and Linux hosts
- An understanding of how Sysmon works and why it matters for Windows event collection
- The ability to search and investigate logs across multiple endpoints from one place
- Familiarity with the types of events that show up in a real SOC queue

---

## Phase 4: Network security monitoring

I want to see what network traffic actually looks like at a packet and flow level. Understanding what normal traffic looks like is the foundation of knowing what to hunt for.

What I want to walk away with:
- A working Security Onion deployment capturing live traffic on my network
- An understanding of how Suricata rules work and how to read IDS alerts
- The ability to use Zeek logs to reconstruct what happened on the network
- Hands-on experience analyzing DNS, HTTP, SMB, and authentication traffic

---

## Phase 5: Attack simulation

I want to run real attack techniques against my own environment and see what they look like from both sides. This is how I'll know whether my detections are actually working.

What I want to walk away with:
- Experience running ATT&CK-mapped techniques using Atomic Red Team
- An understanding of how common attacks like brute force, persistence, and credential access actually work at a technical level
- The ability to correlate what I did as an attacker with what showed up in my SIEM and NSM tools
- A more realistic picture of what a SOC analyst sees during an incident

---

## Phase 6: Incident response

Running attacks means nothing if I can't investigate them properly. I want to practice thinking through an incident the way a SOC analyst would, not just finding the alert but understanding the full story.

What I want to walk away with:
- 10 completed incident reports covering different attack types
- A repeatable process for working through an alert from start to finish
- The ability to identify indicators of compromise, establish a timeline, and document root cause
- Writing that is clear enough that someone else could read my reports and understand what happened

---

## Phase 7: Detection engineering

Consuming detections is one thing. Writing them is another. I want to understand what makes a good detection rule and how to tune out noise without missing real threats.

What I want to walk away with:
- Custom detection rules built for the attack techniques I ran in Phase 5
- Every rule mapped to a MITRE ATT&CK technique
- An understanding of how to balance false positive rates against detection coverage
- Experience tuning a SIEM so alerts are meaningful rather than overwhelming

---

## Phase 8: Portfolio development

Everything I build should be something I can show. This phase is about making sure the work I did across the previous phases is documented, presentable, and easy to understand by someone reviewing my GitHub.

What I want to walk away with:
- A GitHub profile with clearly documented projects for each major component
- Architecture diagrams, screenshots, detection rules, and incident reports published and organized
- The ability to talk through every part of this lab in an interview with specific examples
- A portfolio that reflects real skills, not just a list of tools I installed

---

## Target roles

SOC Analyst, Security Analyst, NOC Technician, Systems Administrator, Junior Cybersecurity