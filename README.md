# Azure-Honeynet-SOC-Lab
# Building a Honeynet + SOC in Azure (Live Traffic)  
## Cloud Honeynet / SOC — by Andon

---
<img src="https://github.com/user-attachments/assets/2f38616c-62fb-47ee-852d-b58b58e521fe" alt="Cloud Honeynet / SOC" width="600"/>



### 📘 Introduction

This project was inspired by my mentor, Eric Noga, who laid the blueprint for building a strong cybersecurity portfolio. Following his guidance, I developed my own compact honeynet in Microsoft Azure and integrated various log sources into a Log Analytics Workspace. 

The environment is used in tandem with **Microsoft Sentinel** to build attack maps, generate alerts, and monitor incidents. I captured and analyzed metrics over 24-hour periods *before and after* implementing security controls to highlight the impact of proper hardening.

---

### 🧩 Key Metrics Captured

| Metric | Description |
|--------|-------------|
| `SecurityEvent` | Windows Event Logs |
| `Syslog` | Linux Event Logs |
| `SecurityAlert` | Alerts triggered in Sentinel |
| `SecurityIncident` | Incidents created in Sentinel |
| `AzureNetworkAnalytics_CL` | Network flows into the honeynet |

---

### 🏗️ Architecture Overview

#### Before Hardening




- Open NSGs and firewalls
- All public endpoints
- VMs exposed to internet traffic

#### After Hardening

- NSG rules limited to admin IP
- Private endpoints used
- Built-in firewalls enabled

**Components Used**:
- Microsoft Sentinel
- Microsoft Entra
- Microsoft Defender for Cloud
- Virtual Network (VNet)
- Network Security Group (NSG)
- Azure Key Vault
- Virtual Machines (2 Windows, 1 Linux)
- Log Analytics Workspace
- Azure Storage Account

---

### 📉 Attack Maps Before Security Controls

- NSG allowed inbound malicious flows
- Linux Syslog authentication failures
- Windows RDP/SMB brute force attempts

---

### 📊 Metrics: Before vs After Security Implementation

#### Before

| Metric | Count |
|--------|-------|
| SecurityEvent | 23073 |
| Syslog | 2547 |
| SecurityAlert | 6 |
| SecurityIncident | 235 |
| AzureNetworkAnalytics_CL | 2389 |

#### After

| Metric | Count |
|--------|-------|
| SecurityEvent | 22779 |
| Syslog | 43 |
| SecurityAlert | 0 |
| SecurityIncident | 10 |
| AzureNetworkAnalytics_CL | 152 |

---

### 🔍 Conclusion

By constructing a honeynet in Microsoft Azure and integrating Microsoft Sentinel, I was able to visualize and respond to simulated attacks in real time. This project strengthened my understanding of SIEM, NSG policies, and Azure security configurations. Based on NIST 800-53 and 800-61, the hardened setup showed a substantial drop in threat exposure and alert volume.

---

### 👤 Author

**Andon - Aspiring SOC Analyst**

Inspired by: [Eric Noga](https://www.linkedin.com/in/ericnoga/)  
Connect with me: [LinkedIn](https://www.linkedin.com/in/YOUR-LINK-HERE)

---

