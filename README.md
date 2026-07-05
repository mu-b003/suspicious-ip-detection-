# Suspicious IP Detection

## Overview

This project demonstrates a basic SOC investigation by detecting a suspicious IP address through SSH authentication logs on an Ubuntu Linux system. A simulated attacker generated failed SSH login attempts from a Kali Linux machine. The investigation identifies the source IP, targeted accounts, failed login events, and applies a firewall rule to block the suspicious IP.

---

## Objective

- Detect suspicious SSH login activity.
- Analyze authentication logs.
- Identify the attacking IP address.
- Investigate targeted user accounts.
- Block the malicious IP using iptables.
- Document the investigation process.

---

## Lab Environment

| Component | Description |
|-----------|-------------|
| Attacker | Kali Linux |
| Target | Ubuntu Server |
| Service | OpenSSH |
| Log File | /var/log/auth.log |
| Firewall | iptables |

---

## Investigation Steps

1. Verify network configuration.
2. Check SSH service status.
3. Generate failed SSH login attempts.
4. Analyze authentication logs.
5. Detect the suspicious IP.
6. Identify targeted accounts.
7. Detect invalid usernames.
8. Block the suspicious IP using iptables.

---

## Skills Demonstrated

- Linux Log Analysis
- SSH Investigation
- Authentication Log Analysis
- Suspicious IP Detection
- Basic Incident Response
- Firewall Rule Management
- SOC Level 1 Investigation

---

## Tools Used

- Ubuntu Linux
- Kali Linux
- OpenSSH
- grep
- awk
- sort
- uniq
- iptables

---

## Repository Structure

```
.
├── README.md
├── LICENSE
├── DISCLAIMER.md
├── Suspicious_IP_Detection_Report.pdf
├── commands.md
└── evidence/
```

---

## Disclaimer

This project was conducted in a private laboratory environment for educational purposes only.
