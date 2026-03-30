# 🛡️ SOC Analyst Detection Lab: Telemetry & SIEM Engineering

---

## 📝 Project Executive Summary
Coming from a background in **Tactical Intelligence (SWAT)** and **Systemic Problem Solving (Amazon)**, I architected this isolated SOC environment to master the full lifecycle of a digital threat. This lab demonstrates my ability to engineer high-fidelity telemetry, troubleshoot complex infrastructure, and visualize attack data in a SIEM.

---

## 📁 Project Structure
| Folder | Contents |
| :--- | :--- |
| **[🏗️ Diagrams](Diagrams/)** | Network Topology & Architecture Maps |
| **[📜 Scripts](Scripts/)** | Sysmon XML Configs & Splunk SPL Queries |
| **[📊 Evidence](Evidence/)** | Dashboard Screenshots & Error Resolutions |
| **[📖 Documentation](Documentation/)** | Full Technical After-Action Reports (AAR) |

---

## 🏗️ Lab Architecture & Design
* **Virtualization:** VMware Workstation Pro (Isolated Layer 2 LAN Segment)
* **Attacker Node:** Kali Linux (192.168.242.130) 
* **Victim Node:** Windows 10 (192.168.242.128) - Hardened with **Sysmon**
* **SIEM Node:** Ubuntu 22.04 (192.168.242.129) - **Splunk Enterprise**

---

## 🛠️ Technical Wins & Troubleshooting

### **The "ObjectNotFound" Resolution**
While deploying telemetry agents, I encountered a **PowerShell `ItemNotFoundException`**.
* **Investigation:** Utilized `Get-ChildItem -Recurse` to identify the absolute directory of the binary.
* **Resolution:** Corrected the execution path to ensure the **Universal Forwarder** and **Sysmon** services initiated successfully.
* **Evidence:** [View Resolution Screenshot](Evidence/PowerShell_ObjectNotFound_Resolution.png)

---

## 📊 Detection Results: Nmap Reconnaissance
Successfully identified a high-volume connection spike on **Port 445 (SMB)** originating from the Kali Linux attacker node.

* **Telemetry Source:** Sysmon Event ID 3 (Network Connection)
* **SIEM Platform:** Splunk Enterprise
* **Key Finding:** Identified stealth scanning patterns targeting Windows File Sharing services.
* **Evidence:** [View Splunk Detection Dashboard](Evidence/Splunk_Nmap_Detection_Dashboard.png)

---

## 🔑 Key Skills Acquired
* **SIEM Mastery:** Splunk Search Processing Language (SPL) & Data Visualization.
* **Endpoint Visibility:** Sysmon XML Deployment & Windows Event Log Management.
* **Infrastructure Admin:** VMware Network Isolation & PowerShell Troubleshooting.
* **Analytical Mindset:** Applying Tactical Intelligence (AAR) to Cyber Defense.

