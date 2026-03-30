🛡️ SOC Analyst Detection Lab: Telemetry & SIEM Engineering

📝 Project Executive Summary
Coming from a background in Tactical Intelligence (SWAT) and Systemic Problem Solving (Amazon), I architected this isolated SOC environment to master the full lifecycle of a digital threat—from initial reconnaissance to SIEM visualization. This lab demonstrates my ability to engineer high-fidelity telemetry and troubleshoot complex infrastructure hurdles.

📁 Project Structure
🏗️ Network Diagram - Visual layout of the isolated VMware environment.

📜 Configuration Scripts - Sysmon XML templates and Splunk SPL queries.

📊 Attack Evidence - Screenshots of Splunk Dashboards and PowerShell fixes.

📖 Technical Writeup - Deep dive into the investigative process.

🏗️ Lab Architecture & Design
Environment Specifications:
Virtualization: VMware Workstation Pro (Isolated Layer 2 LAN Segment).

Attacker Node: Kali Linux (192.168.242.130) - Executing Nmap Reconnaissance.

Victim Node: Windows 10 (192.168.242.128) - Hardened with Microsoft Sysmon.

SIEM Node: Ubuntu 22.04 (192.168.242.129) - Splunk Enterprise Indexer.

🛠️ Technical Wins & Troubleshooting
The "ObjectNotFound" Resolution
While deploying the telemetry agents, I encountered a PowerShell ItemNotFoundException regarding the Sysmon binary.

Investigation: Utilized Get-ChildItem -Recurse to identify the absolute directory of the executable.

Resolution: Corrected the execution path to ensure the Universal Forwarder and Sysmon services initiated successfully.

Evidence: PowerShell Fix Screenshot

Telemetry Engineering
I deployed a customized Sysmon configuration (Event ID 3) to capture granular network connection data, specifically focusing on Port 445 (SMB) to identify lateral movement signatures.

📊 Detection Results
Simulated Attack: Nmap Stealth Scan
Using the Kali node, I executed a service-level scan against the Windows Target.

SIEM Analysis
Using Splunk SPL and manual Regex (rex) field extraction, I successfully isolated the reconnaissance traffic.

Key Finding: Identified a high-volume spike from the Attacker IP targeting SMB ports.

Evidence: View Splunk Detection Dashboard

🔑 Key Skills Acquired
SIEM Mastery: Splunk Search Processing Language (SPL), Dashboard Visualization.

Endpoint Visibility: Sysmon XML Deployment, Windows Event Log Management.

Infrastructure Admin: VMware Network Isolation, PowerShell Troubleshooting.

Analytical Mindset: Applying Tactical Intelligence (AAR) to Cyber Defense.
