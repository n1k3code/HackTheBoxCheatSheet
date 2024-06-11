# Password Cracking

Drupal 7

```bash
sudo hashcat -m 7900 -a 0 -o cracked.txt hash /usr/share/wordlists/rockyou.txt --force
```

