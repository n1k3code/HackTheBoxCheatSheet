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



List shares

```bash
smbclient -L \\\\<IP>\\
```

```bash
 smbclient -L \\\\10.129.178.26\\
```

Connect to share

```bash
smbclient -L \\\\<IP>\\<SHARE_NAME>
```

```bash
smbclient \\\\10.129.178.26\\support-tools
```
