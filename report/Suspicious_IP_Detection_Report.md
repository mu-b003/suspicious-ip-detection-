# Suspicious IP Detection Report

**Author:** Mubarak Bashr  
**Project:** Suspicious IP Detection  
**Date:** July 2026

---

# Executive Summary

This project demonstrates a basic Security Operations Center (SOC) investigation focused on detecting a suspicious IP address through SSH authentication log analysis on an Ubuntu Linux system.

A simulated attacker from a Kali Linux machine generated multiple failed SSH login attempts against the target server. Authentication logs were analyzed to identify the attack source, targeted user accounts, failed login attempts, and invalid usernames. After confirming the suspicious activity, a firewall rule was applied using iptables to block the source IP.

---

# Objective

The objective of this investigation was to:

- Detect suspicious SSH authentication activity.
- Analyze Linux authentication logs.
- Identify the source IP address.
- Determine the targeted user accounts.
- Detect invalid usernames.
- Apply a containment action using iptables.
- Document the investigation process.

---

# Lab Environment

| Component | Description |
|-----------|-------------|
| Attacker Machine | Kali Linux |
| Target Machine | Ubuntu Linux |
| Service | OpenSSH |
| Log File | /var/log/auth.log |
| Firewall | iptables |

---

# Investigation Process

## Step 1 – Verify Network Configuration

The network configuration was verified using the following command:

```bash
ip a
```

The target machine was assigned the IP address:

```
192.168.150.129
```

---

## Step 2 – Verify SSH Service

The SSH service was checked to confirm that it was running and accepting connections.

```bash
sudo systemctl status ssh
```

---

## Step 3 – Simulate Failed SSH Logins

Multiple failed SSH login attempts were generated from the Kali Linux machine using different usernames.

Targeted usernames included:

- admin
- developer
- IT-support

---

## Step 4 – Analyze Authentication Logs

Authentication logs were reviewed using:

```bash
sudo grep "Failed password" /var/log/auth.log
```

The logs confirmed multiple failed authentication attempts.

---

## Step 5 – Detect the Source IP

The following command was used:

```bash
sudo grep "Failed password" /var/log/auth.log | grep -oE "from [0-9.]+" | sort | uniq -c
```

Result:

```
9 from 192.168.150.128
```

The investigation confirmed that all failed login attempts originated from a single IP address.

---

## Step 6 – Identify Targeted User Accounts

The following command was executed:

```bash
sudo grep "Failed password" /var/log/auth.log | grep -oE "for [a-zA-Z0-9-]+" | sort | uniq -c
```

The investigation identified multiple targeted accounts.

---

## Step 7 – Detect Invalid Usernames

Authentication logs were searched for invalid usernames.

```bash
sudo grep "Invalid user" /var/log/auth.log
```

The logs confirmed that the attacker attempted to authenticate using the non-existent account:

```
admin
```

---

## Step 8 – Containment

The suspicious IP was blocked using iptables.

```bash
sudo iptables -A INPUT -s 192.168.150.128 -j DROP
```

The firewall rule was verified successfully.

---

# Investigation Findings

| Finding | Result |
|---------|--------|
| Source IP | 192.168.150.128 |
| Service Targeted | SSH |
| Failed Login Attempts | 9 |
| Invalid Username | admin |
| Additional Accounts | developer, IT-support |
| Successful Login | None |
| Containment | IP Blocked using iptables |

---

# Indicators of Compromise (IOCs)

**Source IP**

```
192.168.150.128
```

**Target Service**

```
SSH
```

**Observed Events**

- Failed Password
- Invalid User
- Multiple Authentication Failures

**Log Source**

```
/var/log/auth.log
```

---

# Mitigation

The following defensive action was taken:

- Blocked the suspicious IP address using iptables.

Recommended security improvements include:

- Enable Fail2Ban.
- Use SSH key authentication.
- Disable remote root login.
- Monitor authentication logs regularly.
- Use strong passwords.
- Keep OpenSSH updated.

---

# Conclusion

This investigation successfully demonstrated the process of detecting suspicious SSH authentication activity through Linux log analysis. Authentication logs were used to identify the attacking IP address, determine the targeted accounts, detect invalid usernames, and verify that no unauthorized access was achieved.

The incident was successfully contained by applying an iptables firewall rule to block the suspicious IP address. This project demonstrates fundamental SOC Level 1 skills, including log analysis, incident investigation, indicator identification, and basic containment techniques.

---
**End of Report**
