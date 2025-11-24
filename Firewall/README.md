# 🔥 Windows Firewall Hardening Lab

A hands-on security engineering project demonstrating **host-based firewall rule design**, **traffic analysis**, **PowerShell automation**, and **security justification** for blocking high-risk services.

This lab simulates a real-world defensive environment and documents the entire workflow, including baseline network tests, rule creation, validation, and reporting.

---

## 📁 Repository Structure

    Windows-Firewall-Hardening-Lab/
    ├─ Diagram/
    │  └─ firewall_architecture.png
    ├─ Rules/
    │  ├─ firewall_rules.txt
    │  └─ test_rule.txt
    ├─ Tests/
    │  ├─ baseline_network_tests.txt
    │  └─ firewall_block_tests.txt
    ├─ Reports/
    │  └─ Windows_Firewall_Security_Report.docx
    └─ README.md   ← (You are here)


## 🛡️ Project Overview

This project was designed to simulate **enterprise firewall hardening** through:

- Creation of inbound & outbound firewall rules  
- Blocking high-risk legacy protocols  
- Preventing lateral movement & remote exploitation  
- Validating rule effectiveness through live tests  
- Documenting results in a security report  

This demonstrates practical skills needed for:

✔ SOC Analyst  
✔ Cybersecurity Engineer  
✔ Junior Penetration Tester  
✔ IT Security Support  
✔ Blue Team / Defensive Operations  

---

## 🧩 Firewall Architecture Diagram

### 🔽 Diagram Preview  
[Firewall/Diagram/Firewall diagram.png](https://github.com/ErnestoMPerez/Windows-Firewall-Hardening-Lab/blob/91792ffb8a946625a2312f507abef2934129eb8d/Firewall/Diagram/Firewall%20diagram.png)

---

## 🔐 Security Rules Implemented

### 🚫 Blocked High-Risk Services
| Service | Port | Reason |
|---------|------|--------|
| **Telnet** | 23 | Unencrypted credentials, remote exploitation risk |
| **FTP** | 21 | Cleartext credentials, easy MITM/sniffing |
| **SMB** | 445 | Lateral movement, ransomware propagation (EternalBlue) |
| **RDP** | 3389 | Remote control, brute-force entry vector |
| **Malicious IPs** | *varies* | Prevent C2 and suspicious outbound calls |

### ✅ Allowed Essential Services
| Service | Port | Purpose |
|---------|------|----------|
| **DNS** | 53 | Domain resolution |
| **HTTPS** | 443 | Secure browsing |
| **Windows Update** | varies | Patch management |

---

## 📜 Example PowerShell Firewall Rules

### Block Telnet
```powershell
New-NetFirewallRule `
  -DisplayName "Block Telnet" `
  -Direction Outbound `
  -Action Block `
  -Protocol TCP `
  -LocalPort 23
Block FTP
powershell
Copy code
New-NetFirewallRule `
  -DisplayName "Block FTP" `
  -Direction Outbound `
  -Action Block `
  -Protocol TCP `
  -LocalPort 21
Block SMB
powershell
Copy code
New-NetFirewallRule `
  -DisplayName "Block SMB" `
  -Direction Outbound `
  -Action Block `
  -Protocol TCP `
  -LocalPort 445
Block RDP
powershell
Copy code
New-NetFirewallRule `
  -DisplayName "Block RDP" `
  -Direction Outbound `
  -Action Block `
  -Protocol TCP `
  -LocalPort 3389
🧪 Network Tests Performed
1️⃣ Baseline Tests (Before Firewall Rules)
Stored in: Tests/baseline_network_tests.txt

Commands:
ping 8.8.8.8
ping google.com
tracert google.com
2️⃣ Firewall Rule Validation Tests
Stored in: Tests/firewall_block_tests.txt

Verification commands:
Test-NetConnection -Port 23   # Telnet
Test-NetConnection -Port 21   # FTP
Test-NetConnection -Port 445  # SMB
Test-NetConnection -Port 3389 # RDP

Expected Result:
TcpTestSucceeded : False
📘 Security Justification Summary
This hardening project prevents:

Credential theft via plaintext protocols

Worm propagation (SMB vulnerabilities)

Unauthorized remote access

Lateral movement inside a compromised network

Outbound C2 connections to malicious hosts

This setup reflects industry best practices for:

✔ Zero Trust Architecture
✔ CIS Benchmark Compliance
✔ Basic SOC/Blue-Team Hardening
✔ Enterprise Host Security

📝 Full Report
A detailed written report is included:

📄 Reports/Windows_Firewall_Security_Report.docx

This contains:

Findings

Analysis

Screenshots

Rule explanations

Risk reduction summary

🧰 Skills Demonstrated
Windows Defender Firewall configuration

Real-world recon & enumeration

PowerShell automation

Defensive security mindset

Documentation & reporting

Network traffic analysis

Rule testing & validation

🧑‍💻 Author
Ernesto Perez
📫 Email: ernestomperez1@gmail.com

⭐ Want to support?
Give this repository a ⭐ on GitHub!
