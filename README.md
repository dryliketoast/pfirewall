# pfirewall
iptables python wrapper for easy firewall configuration on linux

## Setup
- Create the folder `mkdir /root/firewall/`
- Copy/Extract the scripts and config files to that folder
- Customise the configuration files
- Make sure the `firewall.python` script is executable
- Run the firewall.python script

## Load script on boot
To load the firewall before the network interface starts on debian/ubuntu, add this to your network block in the file /etc/network/interfaces
```
pre-up /root/firewall/firewall.python
```

## Example
```
# The primary network interface
auto eth0
iface eth0 inet static
        address x.x.x.x
        netmask 255.255.255.0
        gateway x.x.x.x
        dns-nameservers 8.8.8.8 8.8.4.4
        pre-up /root/firewall/firewall.python
```
