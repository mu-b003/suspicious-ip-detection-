# Indicators of Compromise (IOCs)

## Suspicious IP Address

192.168.150.128

---

## Target Service

SSH

---

## Targeted User Accounts

- admin (Invalid User)
- developer
- IT-support

---

## Observed Events

- Failed Password
- Invalid User
- Multiple Authentication Failures

---

## Log Source

/var/log/auth.log

---

## Containment

Firewall rule added using iptables to block the source IP.
