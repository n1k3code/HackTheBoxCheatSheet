# Misc

**scan all ports with masscan, regex and nmap**

```bash
masscan -p1-65535,U:1-65535 10.10.10.98 --rate=1000 -p1-65535,U:1-65535 -e tun0 > ports
ports=$(cat ports | awk -F " " '{print $4}' | awk -F "/" '{print $1}' | sort -n | tr '\n'
',' | sed 's/,$//')
nmap -Pn -sV -sC -p$ports 10.10.10.98
```
