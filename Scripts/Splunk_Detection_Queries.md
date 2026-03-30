# 🛡️ Splunk Detection Queries (Lab 1)

### 1. Basic Network Connection Discovery (Event ID 3)
* **Goal:** Identify all inbound network traffic captured by Sysmon.
```splunk
index="main" sourcetype="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational" EventCode=3
| table _time, Image, SourceIp, SourcePort, DestinationIp, DestinationPort

---

index="main" EventCode=3 DestinationPort=445
| stats count by SourceIp, Image
| sort - count

---

index="main" 
| rex field=_raw "DestinationPort\">(?<Dest_Port>\d+)"
| search Dest_Port=445
| table _time, SourceIp, Dest_Port

---
