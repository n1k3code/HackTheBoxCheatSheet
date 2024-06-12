# nmap

### Options

```bash
-sC:                equivalent to --script=default
-Pn:                Treat all hosts as online -- skip host discovery
-p <port ranges>:   Only scan specified ports
-sS/sT/sA/sW/sM:    TCP SYN/Connect()/ACK/Window/Maimon scans
-sV:                Probe open ports to determine service/version info
-sn:                Ping Scan - disable port scan
-n/-R:              Never do DNS resolution/Always resolve [default: sometimes]
```

### Declare IP

```bash
ip=10.129.128.171
```

### One Line no IP

```bash
nmap $ip -sV -sC -p $(sudo nmap -p- -sS -T4 -Pn $ip | grep ^[0-9] | cut -d '/' -f 1 | tr '\n', ',' | sed 's/,$//')
```

### One Line with IP

```bash
ip=10.129.128.171;nmap $ip -sV -sC -p $(sudo nmap -p- -sS -T4 -Pn $ip | grep ^[0-9] | cut -d '/' -f 1 | tr '\n', ',' | sed 's/,$//')
```



**Scan all ports with min-rate**

```bash
ports=$(nmap -p- --min-rate=1000 -T4 10.10.10.215 | grep ^[0-9] | cut -d '/' -f 1 | tr '\n' ',' | sed s/,$//) 
nmap -p$ports -sC -sV 10.10.10.215
```

\






