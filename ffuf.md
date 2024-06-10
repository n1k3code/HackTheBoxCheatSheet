# FFUF

## Options

```bash
    -u                  Target URL
    -H                  Header `"Name: Value"`, separated by colon. Multiple -H flags are accept
    -w                  Wordlist file path and (optional) keyword separated by colon. eg. '/path/to/wordlist:KEYWORD'
    -mc                 Match HTTP status codes, or "all" for everything. (default: 200-299,301,302,307,401,403,405,500)
    -fs                 Filter HTTP response size. Comma separated list of sizes and ranges
    -fw                 Filter by amount of words in response. Comma separated list of word counts and ranges
    -fl                 Filter by amount of lines in response. Comma separated list of line counts and ranges
    -t                  Number of concurrent threads. (default: 40)
    -c                  Colorize output. (default: false)
    -ic                 Ignore wordlist comments (default: false)
    -X                  HTTP method to use
    -b                  Cookie data `"NAME1=VALUE1; NAME2=VALUE2"` for copy as curl functionality.
    -x                  Proxy URL (SOCKS5 or HTTP). For example: http://127.0.0.1:8080 or socks5://127.0.0.1:8080

```


Basic enumeration
```bash
ffuf -u https://10.10.10.210/FUZZ -w /usr/share/wordlists/dirb/common.txt
```
