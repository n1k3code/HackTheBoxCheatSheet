# smbclient

## OPTIONS <a href="#options" id="options"></a>

```bash
smbclient:
-L: Get a list of shares available
-U: [DOMAIN/]USERNAME[%PASSWORD] Set the network username
smbmap:
-H: IP of host
-p: Password or NTLM hash
-d: Domain name (default WORKGROUP)
-u: Username, if omitted null session assumed
```

## OPERATIONS

<pre class="language-bash"><code class="lang-bash">allinfo <FILE>: The client will request that the server return all 
known information about a file or directory (including streams).

get <REMOTE FILE> <LOCAL FILE>: Copy the file called remote file name from 
the server to the machine running the client. If specified, name the local 
copy local file name. Note that all transfers in smbclient are binary.
</code></pre>



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

**smbclient can now be used to enumerate any available file shares.**

```bash
smbclient -L //10.10.10.10
```

**connect to enumerated share**

```bash
smbclient //10.10.10.100/Replication
```

**With valid credentials for the active.htb domain, further enumeration can be undertaken.**

```bash
smbmap -d active.htb -u SVC_TGS -p GPPstillStandingStrong2k18 -H 10.10.10.100
```

**connect to users shares with valid user%password**

```bash
smbclient -U SVC_TGS%GPPstillStandingStrong2k18 //10.10.10.100/Users
```
