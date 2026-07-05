# Recommendations

To improve the security of the SSH service, the following recommendations are suggested:

- Enable Fail2Ban to automatically block repeated failed login attempts.
- Use SSH public key authentication instead of passwords.
- Disable remote root login.
- Use strong and unique passwords for all accounts.
- Regularly monitor authentication logs.
- Remove unused user accounts.
- Keep the operating system and OpenSSH updated.
- Restrict SSH access to trusted IP addresses whenever possible.
- Review firewall rules periodically.
- Generate alerts for repeated authentication failures.

---

## Future Improvements

- Deploy a SIEM solution for centralized log monitoring.
- Automate suspicious IP detection.
- Integrate firewall automation for faster incident response.
- Configure email or dashboard alerts for SSH attacks.
