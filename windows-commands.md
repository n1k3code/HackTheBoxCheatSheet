# Windows Commands

Create user to domain

```
net user john abc123! /add /domain
```



Add user to group

```
net group "Exchange Windows Permissions" john /add
```



Add user to local group

```
net localgroup "Remote Management Users" john /add
```
