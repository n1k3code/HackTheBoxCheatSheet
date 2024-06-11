# SMB

Enumerate Samba shares

```bash
enum4linux 10.10.10.123
```



Connect to share

```bash
smbclient -N \\\\10.10.10.123\\general
smb: /> ls
smb: /> get creds.txt
```
