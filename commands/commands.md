# Commands Used

## Display network information

```bash
ip a
```

---

## Check SSH service status

```bash
sudo systemctl status ssh
```

---

## Restart SSH service

```bash
sudo systemctl restart ssh
```

---

## Display failed SSH login attempts

```bash
sudo grep "Failed password" /var/log/auth.log
```

---

## Count failed login attempts by source IP

```bash
sudo grep "Failed password" /var/log/auth.log | grep -oE "from [0-9.]+" | sort | uniq -c
```

---

## Count failed login attempts by username

```bash
sudo grep "Failed password" /var/log/auth.log | grep -oE "for [a-zA-Z0-9-]+" | sort | uniq -c
```

---

## Detect invalid usernames

```bash
sudo grep "Invalid user" /var/log/auth.log
```

---

## Search for failed root login attempts

```bash
sudo grep "Failed password for root" /var/log/auth.log
```

---

## Block the suspicious IP

```bash
sudo iptables -A INPUT -s 192.168.150.128 -j DROP
```

---

## Verify firewall rules

```bash
sudo iptables -L -n -v
```
