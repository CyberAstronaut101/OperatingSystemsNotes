# Raspberry Pi Networking


## eth0 Static IP Address

`ifconfig` to view your network interfaces

`sudo cp /etc/dhcpcd.conf /etc/dhcdcp.backup` to create a backup of the configuration file

edit `/etc/dhcpcd.conf` and add an interface definition to the end of the file:

```
interface eth0
static ip_address=192.168.0.100/24
static router=192.168.0.1
static domaint_name_servers=192.168.0.11 8.8.8.8
```

`interface eth0` defines that we are talking about the Ethernet port

`static ip_address` is the IP address you want the pi to have

`static router` is your router IP. *NOTE that your network might be different

`static domain_name_servers` are the DNS servers that you would like to use, in order of precedience, seperated with spaces


Bring down the Ethernet interface:
`sudo ifdown eth0`

Bring the interface back up:
`sudo ifup eth0`



