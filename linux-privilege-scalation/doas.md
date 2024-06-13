# Doas

```
luanne$ sh linpeas.sh -a
<SNIP>
[+] Checking doas.conf 
permit r.michaels as root
```

```
luanne$ doas sh
Password:
# whoami
root
```
