# chisel



Forwarding 8888 service port found on windows to linux

```bash
# On Linux
./chisel server -p 9999 --reverse

# On Windows
chisel.exe client 10.10.14.2:9999 R:8888:127.0.0.1:8888
```
