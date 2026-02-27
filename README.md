# Design and Implementation SOC using open source technologies SIEM for Industries
 # 📖Project Overview
This project presents the design and implementation of a Security Operations Center (SOC) using open-source technologies for industrial environments.

 The system integrates:
 
- **Suricata (Network Intrusion Detection System)**
- **Wazuh (SIEM & HIDS)**
- **Kali Linux (Attacker simulation)**
- **Ubuntu (Monitoring agent)**
- **Windows 10 (Endpoint agent)**
- **VMware Workstation (Virtual Lab Environment)**

The objective is to build a cost-effective, scalable, real-time SOC architecture capable of detecting and analyzing cyber attacks in industrial networks.

# 🎯 Objectives
* Design a practical SOC architecture using open-source tools
* Implement Network IDS (NIDS) and Host IDS (HIDS)
* Detect:
   * Enumeration (Port Scanning)
   * Brute Force Attacks
   * DDoS Attacks
* Centralize logs using SIEM
* Create custom detection rules
* Provide real-time monitoring dashboard

# 🚨 Problem Statement

**Modern industries face:**
- Advanced persistent threats
- Brute-force authentication attacks
- Port scanning reconnaissance
- Distributed Denial-of-Service (DDoS)
- High-cost commercial SIEM solutions

Small and medium industries cannot afford expensive SOC platforms.

This project provides a low-cost alternative using open-source technologies.

# 🏗️ Proposed SOC Architecture
<img width="1013" height="817" alt="lab" src="https://github.com/user-attachments/assets/8f9f0373-4026-4355-85ab-bf2c47644d37" />

🔹 Network Flow

Attacker (Kali Linux)
-->
Router 
-->
Firewall
-->
Switch (NIC)
-->
Suricata (Promiscuous Mode Monitoring)
-->
Wazuh Agent
-->
Wazuh Server
-->
Wazuh Dashboard (SIEM)
# 🛠️ Technologies Used
| Tool               | Purpose                     |
| ------------------ | --------------------------- |
| Suricata           | Network Intrusion Detection |
| Wazuh              | SIEM & Log Correlation      |
| Kali Linux         | Attack Simulation           |
| Hydra              | Brute Force Attack          |
| Nmap               | Enumeration                 |
| DDoS-Ripper        | DDoS Simulation             |
| Ubuntu             | Monitoring Agent            |
| Windows 10         | Monitoring Agent            |
| VMware Workstation | Virtual Lab Setup           |

# ⚙️ Implementation Steps
**Lab Setup**

* Installed VMware Workstation

**Created virtual machines:**
- Kali Linux (Attacker)
- Ubuntu Desktop (Wazuh Agent + Suricata)
- Windows 10 (Wazuh Agent)
- Wazuh OVA (SIEM Server)

# Suricata Configuration

* Installed Suricata IDS
* Configured in promiscuous mode
* Set:
  * HOME_NET
  * EXTERNAL_NET
* Integrated Suricata with Wazuh via eve.json

 # Wazuh Configuration
* Deployed Wazuh OVA
* Registered Ubuntu and Windows agents
* Created custom rule for brute-force detection
  # 🔥 Attacks Simulated
**Enumeration (Port Scanning)**

Tool: Nmap

Command:

*nmap -sS -sV 192.168.58.136*

Detected by:
  * Suricata NIDS
  * Wazuh Dashboard

<img width="1867" height="396" alt="nmap2" src="https://github.com/user-attachments/assets/5d64e8ad-f76e-4d8e-b6b5-25139b4cb707" />

<img width="731" height="902" alt="nmap3" src="https://github.com/user-attachments/assets/178d7800-a6ec-416d-ab7a-6a22855c61ce" />
<img width="835" height="722" alt="nmap4" src="https://github.com/user-attachments/assets/06a6a66e-fac0-4f46-a8a9-44bfb79df9e2" />


# Brute Force Attack

Tool: **Hydra**

Command:

*hydra -L user.txt -P password.txt ssh://192.168.58.136*

**Detected as:**

<img width="950" height="905" alt="brutef2" src="https://github.com/user-attachments/assets/2cdbe181-01ac-42a7-a558-b4648884259a" />
<img width="952" height="902" alt="brutef3" src="https://github.com/user-attachments/assets/37538dd8-2a0c-4b3b-b96b-de513a6dc828" />
<img width="1142" height="900" alt="brutef4" src="https://github.com/user-attachments/assets/ce8265d0-3f2f-43a7-a0a1-b574b09aa7eb" />
<img width="1887" height="982" alt="brute5" src="https://github.com/user-attachments/assets/83f138ff-d227-4ff8-8f2f-174b96c2131f" />
