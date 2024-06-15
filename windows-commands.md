# Windows Commands

Create user and add to domain

```powershell
net user <USER> abc123! /add /domain
```

Add user to group

```powershell
net group "Exchange Windows Permissions" <USER> /add
```

Add user to local group

```powershell
net localgroup "Remote Management Users" <USER> /add
#Tip: the administrators localgroup have the admin rights! =D
```