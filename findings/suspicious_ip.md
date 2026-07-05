# Suspicious IP

## Source IP

192.168.150.128

---

## Detection Method

Authentication log analysis using:

- grep
- sort
- uniq

---

## Observed Activity

- Multiple failed SSH login attempts
- Repeated authentication failures
- Attempt to authenticate using an invalid username
- Targeted multiple user accounts

---

## Risk Assessment

Medium

The activity is consistent with password guessing against an SSH service.

---

## Response

The suspicious IP address was blocked using an iptables firewall rule.
