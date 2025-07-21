# Task 2 – SOC Alert Monitoring and Incident Response Simulation

As part of the Future Interns Cybersecurity Internship (June–July 2025), this project involved monitoring and analyzing simulated SOC logs using the Elastic Stack (ELK). The goal was to identify suspicious events, evaluate their impact, and propose appropriate incident response actions.

---

## 🔧 Tools & Technologies
- **Filebeat** – log shipper configured on Ubuntu VM
- **Elasticsearch** – stores indexed logs
- **Kibana** – log visualization and filtering
- **Ubuntu VM on Azure** – environment for log collection and analysis

---

## 🗂️ Dataset Used
- Sample logs ingested from `SOC_Task2_Sample_Logs.txt`
- Logs included a mix of user activity, malware detection, and access events

---

## ⚙️ Configuration Summary
- Filebeat was configured to monitor both `/var/log/auth.log` and the sample log file
- Kibana index pattern `.ds-filebeat-*` was created
- Logs were filtered using the **Discover** tab and searched with queries such as:
  - `message: "2025-07-03"`
  - `user: bob`
  - `action: malware detected`

---

## 🚨 Key Findings – 5 Suspicious Events
Each of these events was analyzed in the full report:

| No. | Timestamp | User    | IP Address     | Action             | Severity |
|-----|-----------|---------|----------------|--------------------|----------|
| 1   | 07:51:14  | eve     | 10.0.0.5       | Malware: Rootkit   | High     |
| 2   | 09:10:14  | bob     | 172.16.0.3     | Malware: Ransomware| High     |
| 3   | 04:53:14  | alice   | 203.0.113.77   | File Accessed      | High     |
| 4   | 07:22:14  | charlie | 192.168.1.101  | Connection Attempt | Medium   |
| 5   | 06:01:14  | bob     | 172.16.0.3     | File Accessed      | Medium   |

---

## ✅ Suggested Remediation Actions
- Isolate infected hosts and contain malware
- Block malicious IP addresses and strengthen authentication
- Enforce least privilege and access control
- Monitor for lateral movement and brute force attempts
- Deploy endpoint protection and intrusion detection

---

## 📄 Report Files
- [Incident_Report_Task2.md](./Incident_Report_Task2.md) – Markdown version
- [Incident_Report_Task2.pdf](./Incident_Report_Task2.pdf) – PDF version

---

## 🎯 Learning Objectives Achieved
- Hands-on log analysis in Kibana
- Real-world alert filtering using Elastic Stack
- Writing an incident report with technical findings and remediation
- Improved critical thinking and cybersecurity threat mapping
