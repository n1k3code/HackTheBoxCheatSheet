# LDAP

## OPTIONS

```bash
ldapsearch:
-x: Simple authentication
-H: LDAP Uniform Resource Identifier(s)
-D: bind DN
-w: bind password (for simple authentication)
-s sub = The -s option specifies the search scope;sub means a subtree search, including the base DN and all its child entries. This is the most comprehensive search scope, as it traverses the entire directory tree below the base DN

(&(objectCategory=person)(objectClass=user)(!
(useraccountcontrol:1.2.840.113556.1.4.803:=2))) is an LDAP search filter to find all user 
objects that are not disabled

objectCategory=person : Searches for objects in the category "person
objectClass=user : Narrows down to objects with a class of "user".

!(useraccountcontrol:1.2.840.113556.1.4.803:=2) : Excludes disabled accounts. The 
userAccountControl attribute is a bit flag; this part of the filter excludes accounts with the 
second bit set (which indicates a disabled account).
```

**ldapsearch can now be used to query the Domain Controller for Active Directory UserAccountControl attributes of active accounts, and for other specific configurations that might be applied to them. A number of UserAccountControl attributes also have security relevance.**

```bash
ldapsearch -x -H 'ldap://10.10.10.100' -D 'SVC_TGS' -w 'GPPstillStandingStrong2k18' -b
"dc=active,dc=htb" -s sub "(&(objectCategory=person)(objectClass=user)(!
(useraccountcontrol:1.2.840.113556.1.4.803:=2)))" samaccountname | grep sAMAccountName
```

**We reuse the previous query and add a filter to catch SPNs, (serviceprincipalname=**_**/**_**) :**

```bash
ldapsearch -x -H 'ldap://10.10.10.100' -D 'SVC_TGS' -w 'GPPstillStandingStrong2k18' -b
"dc=active,dc=htb" -s sub "(&(objectCategory=person)(objectClass=user)(!
(useraccountcontrol:1.2.840.113556.1.4.803:=2))(serviceprincipalname=*/*))"
serviceprincipalname | grep -B 1 servicePrincipalName
```
