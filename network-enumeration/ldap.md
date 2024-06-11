# LDAP

```
ldapsearch -h 10.10.10.161 -p 389 -x -b "dc=htb,dc=local"


python windapsearch.py -d hb.local --dc-ip 10.10.10.161 -U

python windapsearch.py -d hb.local --dc-ip 10.10.10.161 --custom "objectClass=*"

GetNPUsers.py htb.local/svc-alfresco -dc-ip 10.10.10.161 -no-pass


```



