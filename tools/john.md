# john

Options

```
--wordlist[=FILE] --stdin  Wordlist mode, read words from FILE or stdin
                  --pipe   like --stdin, but bulk reads, and allows rules
--format=[NAME|CLASS][,..] Force hash of type NAME. The supported formats can
                           be seen with --list=formats and --list=subformats.
                           See also doc/OPTIONS for more advanced selection of
                           format(s), including using classes and wildcards.
```

Formats

```
--format=krb5asrep
--format=bcrypt
--format=NT
--format=raw-sha256
--format=raw-MD5
--format=Raw-SHA1
```

Example

```
john hashes --wordlist=/usr/share/wordlists/rockyou.txt
```
