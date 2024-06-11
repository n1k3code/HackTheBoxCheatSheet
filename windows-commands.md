# Windows Commands

Create user to domain

```powershell
net user john abc123! /add /domain
```



Add user to group

```powershell
net group "Exchange Windows Permissions" john /add
```



Add user to local group

```powershell
net localgroup "Remote Management Users" john /add
```
