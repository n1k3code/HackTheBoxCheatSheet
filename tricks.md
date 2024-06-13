# Tricks

## Web Server: <a href="#web-server" id="web-server"></a>

**listening localhost:80**

```bash
php -S 0.0.0.0:80
```

## host resolver <a href="#host-resolver" id="host-resolver"></a>

**add to /etc/hosts**

```bash
echo "10.10.10.215 academy.htb" >> /etc/hosts
```

#### add to /etc/hosts

```bash
echo "10.10.10.100 active.htb" | sudo tee -a /etc/hosts
```

#### smbclient can now be used to enumerate any available file shares.

```bash
smbclient -L //10.10.10.100
```













