# Hashcat

**We use hashcat with the rockyou.txt wordlist to crack the hash and obtain the password**

```bash
hashcat -m 13100 hash /usr/share/wordlists/rockyou.txt --force --potfile-disable
```
