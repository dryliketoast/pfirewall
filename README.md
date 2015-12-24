# pfirewall
iptables python wrapper for easy firewall configuration on linux

## Setup
- Copy the files to your server
- Customise the configuration files (ending .txt)
- Make sure the script is executable `chmod +x firewall.python`
- Run the firewall.python script

## Load script on boot
To load the firewall before the network interface starts on debian/ubuntu, add this to your network block in the file /etc/network/interfaces
```
pre-up /your/path/to/pfirewall/firewall.python
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
        pre-up /your/path/to/pfirewall/firewall.python
```
