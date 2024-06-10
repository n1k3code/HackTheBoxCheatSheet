
List shares
```bash
smbclient --no-pass -L //10.10.11.222
Sharename       Type
---------       ----
ADMIN$          Disk
C$              Disk
Department Shares Disk
Development     Disk
Comment
-------
Remote Admin
Default share
Remote IPC
Logon server share
Logon server share
IPC$
NETLOGON
SYSVOL
IPC Disk Disk
SMB1 disabled -- no workgroup available
```

Connect to share
```bash
smbclient //10.10.11.222/Development -N
Try "help" to get a list of possible commands.
smb: \> ls
  .                                   D
  ..                                  D
  Automation                          D
0  Fri Mar 17 09:20:38 2023
0  Fri Mar 17 09:20:38 2023
0  Fri Mar 17 09:20:40 2023
6412543 blocks of size 4096. 1559126 blocks available
```

Recursive download
```bash
smbclient //10.10.11.222/Development -N -c 'prompt OFF;recurse ON;lcd
'~/Desktop/HTB_work/Content/Boxes/Authority/smb_contents/';mget *'
```