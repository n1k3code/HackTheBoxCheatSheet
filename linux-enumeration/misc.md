# Misc

## OPTIONS:

```bash
MDB-TOOLS:
mdb-tables {file} = show tables
mdb-export {file} auth_user = export tables , which reveals usernames and plaintext passwords; auth_user is the table name

7z:
l: List contents of archive
-slt: show technical information for l (List) command
x: eXtract files with full paths

readpst:
-tea: -t[eajc] - Set the output type list. e = email, a = attachment, j = journal, c = contact
-m: as with -e, but write .msg files also
```



**The command "file backup.mdb" confirms that this is a Microsoft Access database, which can be examined using "mdb-tools"**

```bash
mdb-tables backup.mdb | grep --color=auto user
mdb-export backup.mdb auth_user
```

**If logging of TTY input is enabled, any input including passwords are stored hex-encoded inside /var/log/audit/audit.log . We can decode these values manually or use the aureport utility to query and retrieve records of TTY input. Learn more about PAM TTY**

```bash
aureport --tty
```

**"unzip" command fails due to it being compressed using an unsupported format. 7z is used to examine the Zip file, which shows that it was encrypted using the AES-256 algorithm. AES-256 is supported by 7z and WinZip.**

```bash
7z l -slt {path}\ {file}.zip
```

**extract file**

```bash
7z x {path}\ {file}.zip
```

**examine Microsoft Outlook Personal Folder(pst) file**

```bash
readpst -tea -m {path}\ {file}.pst
```









