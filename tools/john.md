# john

Options

```bash
--wordlist[=FILE] --stdin  Wordlist mode, read words from FILE or stdin
                  --pipe   like --stdin, but bulk reads, and allows rules
--format=[NAME|CLASS][,..] Force hash of type NAME. The supported formats can
                           be seen with --list=formats and --list=subformats.
                           See also doc/OPTIONS for more advanced selection of
                           format(s), including using classes and wildcards.
```

Formats

```bash
--format=krb5asrep
--format=bcrypt
--format=NT
--format=raw-sha256
--format=raw-MD5
--format=Raw-SHA1
```

Example

```bash
john hashes --wordlist=/usr/share/wordlists/rockyou.txt
```



```bash
echo "webapi_user:\$1\$vVoNCsOl\$lMtBS6GL2upDbR4Owhzyc0" > hash
john --wordlist=/usr/share/wordlists/rockyou.txt hash
```
