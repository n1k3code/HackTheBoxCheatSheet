# Powershell

**Typically "runas /savecred" is used to create a shortcut, which the user clicks to run the desired application. The commands below are used to enumerate all the accessible shortcut (.lnk) files on the system, and examine them for the presence of the "runas" command.**

```bash
 Get-ChildItem "C:\" *.lnk -Recurse -Force | ft fullname | Out-File shortcuts.txt
> ForEach($file in gc .\shortcuts.txt) { Write-Output $file; gc $file | Select-String runas }
```





