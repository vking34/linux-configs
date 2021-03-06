## dpkg status database is locked by another process:
```
sudo rm /var/lib/dpkg/lock
sudo dpkg --configure -a
```
#

## run google as root:

Open the file ``opt/google/chrome/google-chrome`` and replace
```
exec -a "$0" "$HERE/chrome" "$@"
```
with
```
exec -a "$0" "$HERE/chrome" "$@" --user-data-dir --no-sandbox
```
#

## Configure static IP:
1. Edit interface script file in ```/etc/sysconfig/network-scripts/```. For example, ```ifcfg-eth0```
```
DEVICE=eth0
ONBOOT=yes
BOOTPROTO=static
IPADDR=192.168.1.15
NETMASK=255.255.255.0
GATEWAY=192.168.1.1
DNS1=8.8.8.8
DNS2=8.8.4.4
```
2. Restart network services
```
# service network restart
```

## SSH: REMOTE HOST IDENTIFICATION HAS CHANGED!
Replace the invalid key:
```
ssh-keygen -R "ip.address"
```
#

## Autostart 
Create a desktop file
```
[Desktop Entry]
Type=Application
Exec=/usr/bin/conky
Hidden=false
NoDisplay=false
X-GNOME-Autostart-enabled=true
Name=conky
Comment=
```
#
