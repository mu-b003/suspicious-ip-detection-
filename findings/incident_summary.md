# Incident Summary

## Incident Name

Suspicious IP Detection via SSH Authentication Logs

---

## Incident Type

Multiple Failed SSH Login Attempts

---

## Summary

During log analysis, multiple failed SSH authentication attempts were detected against the Ubuntu server. The activity originated from a single source IP address and targeted several user accounts. One of the usernames did not exist on the system, indicating possible username enumeration or password guessing.

The investigation focused on identifying the source IP, reviewing authentication logs, detecting targeted accounts, and applying a firewall rule to block the suspicious host.

---

## Findings

- Service Targeted: SSH
- Source IP: 192.168.150.128
- Failed Login Attempts: 9
- Targeted Accounts:
  - admin (invalid user)
  - developer
  - IT-support
- Successful Logins: None
- Containment Action: Blocked the source IP using iptables

---

## Status

Incident Successfully Investigated and Contained
