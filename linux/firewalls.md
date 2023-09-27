# Firewalls

### Firewalld <a href="#firewalld" id="firewalld"></a>

firewalls are systems to monitor and control traffic flowing through a network. Firewalld is a firewall service that makes doing this much easier.

**Basic Setup**

* `apt install firewalld` install firewalld
* `systemctl enable firewalld.service` enable service
* `systemctl start firewalld.service` start service
* `systemctl status firewalld` get service status
* `systemctl restart firewalld.service` restart service (do this after changing rules)
* `systemctl stop firewalld.service` stop the service
* `systemctl dissable firewalld.service` dissable the service

### Rules <a href="#rules" id="rules"></a>

* `firewall-cmd --list-all` list rules
* `firewall-cmd --zone=external --list-services` establish zones _default is public_

To make a rule perminate ad the `--permanet` flag to the end of it.

The two most common protocols are `tcp` and `udp`.

**Block By Service**

* List services`sudo firewall-cmd --get-services`
* enable service\
  `sudo firewall-cmd --zone=public --add-service=<service>`
* disable services`sudo firewall-cmd --zone=public --remove-service=<service>`

**Block By Port**\
\- Allow traffic on specified port\
`sudo firewall-cmd --zone=public --add-port=<port>/<protocol>`

* list allowed ports\
  `sudo firewall-cmd --zone=public --list-ports`
* Block Port\
  `sudo firewall-cmd --zone=public --remove-port=<port>/<protocol>`
* Allow Range of Ports\
  `firewall-cmd --add-port=<1stPort>-<lastPort>/<protocol>`
* Deny range of ports\
  `firewall-cmd --remove-port=<1stPort>-<lastPort>/<protocol>`

**Block by IP**

* whitelist an ip `sudo firewall-cmd --permanent --add-source=<ip>`
* blacklist an ip `sudo firewall-cmd --permanent --add-rich-rule="rule family='ipv4' source address='<ip>' reject"` (change family to `ipv6` for ipv6 addr)

Both of these can also be used to block or allow subnets by changing `address='<ip>/<subnet>'`
