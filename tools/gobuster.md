# Gobuster

Options

```bash
dir                                   Uses directory/file enumeration mode
-u, --url string                      The target URL
-w, --wordlist string                 Path to the wordlist
vhost                                 Uses VHOST enumeration mode
-q, --quiet                           Don't print the banner and other noise
-t, --threads int                     Number of concurrent threads (default 10)
-e, --expanded                        Expanded mode, print full URLs
-x, --extensions string               File extension(s) to search for
-b, --status-codes-blacklist string   Negative status codes (will override status-codes if set) (default "404")
-k, --no-tls-validation               Skip TLS certificate verification
--proxy string                        Proxy to use for requests [http(s)://host:port]
```

Wordlists

```bash
-w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt
-w /usr/share/wordlists/dirb/common.txt
```

Sintax

```bash
gobuster dir -u <target> -w <wordlist>
```

Filter extensions

```bash
gobuster dir -u <target> -w /usr/share/wordlists/dirb/common.txt -x txt,pdf,php
```

Example

```bash
gobuster dir -u http://superpass.htb/ -w /usr/share/wordlists/dirb/common.txt
```

Virtual Host

```bash
gobuster vhost -u 'http://hat-valley.htb' -w /usr/share/wordlists/vhosts.txt
```

50 Threads

```bash
gobuster -t 50 -k -u <target> -w <wordlist> -x php
```
