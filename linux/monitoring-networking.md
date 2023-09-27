# Monitoring Networking

**watch can be added before many commands to have them automatically update with changes**\
e.x: `watch netstat -tulpin`

### IP <a href="#ip" id="ip"></a>

* `ip a` - display ip address and related info
* `ip r` - display routing table
* `ip neigh` - show neighbor objects (arp table)

### Netstat <a href="#netstat" id="netstat"></a>

_Netstat is Depriciated but still exsists on many systems_

* `netstat -tulpn` - show tcp, udp, listening, program, numeric address
* `netstat -at` - show active tcp connections including port#
* `netstat -tl` - show listening tcp ports
* `netstat -au` - show all active udp connectons
* `netstat -s` - show network statistics
* `netstat -ap` - show all network connections and associated processes

### SS <a href="#ss" id="ss"></a>

Socket Statistics

* `ss -a` - show all sockets (listening and nonlistening)
* `ss -e` - show detailed socket info
* `ss -p` - show processes using sockets
* `ss -tulpn` - tcp, udp, listenng, program, numeric
* `ss -ap` - show processes using internet sockets
* `ss -x` - show all unix sockets
* `ss -uln` - show all udp sockets
* `ss -tan` - show all established tcp connections
* `ss -tln` - show all listening tcp connections

### Dig <a href="#dig" id="dig"></a>

used to gather DNS information

**USAGE:**\
`dig <server> <name> <type>`\
server - server is the IP or Hostname\
name - address of a specific dns server e.x: `@8.8.8.8`\
type - query type\
`+trace` - trace route to dns server\
`NS` - find nameserver of a domain\
`ANY` - as much info as possiable

**Other**\
reverse dns lookup: `dig -x <ip>`

### lsof <a href="#lsof" id="lsof"></a>

Used to find open files

* `sudo lsof -i4` - ipv4 network files
* `sudo lsof -i6` - ipv6 network files
* `lsof -i` - open sockets
* `lsof -Pnl +M -i4` - listening ports
* `lsof -i TCP:<port#>` - which program is using x port
* `lsof -i@<ip>` - connections to a spescific host
* `lsof -c <command>` - all network connections of a spescific command

### Tcpdump <a href="#tcpdump" id="tcpdump"></a>

* `sudo tcpdump -i any -c <num>` - run tcp dump capturing on all interfaces for `<num>` packets
* `-n` flag to dissable tcpdump name resolution
* `-nn` flag to dissable tcpdump port resolution
* `-c <num>` for number of packets to capture (remove for continued run)
* `-i <interface>` select interface, use any for all

Add a protocol to the end to capture that protocols packets\
e.x:`sudo tcpdump icmp`

Add `port <num>` for packets on x port\
e.x: `sudo tcpdump port 80`

SHOWING PACKET CONTENT\
`-a` shows packet content in ascci\
`-x` shows packet content in hex

SAVING TO A FILE\
add `-w <fileName>.pcap` flag to save capture to a file

### Ping <a href="#ping" id="ping"></a>

check connectivity to a domain\
`ping <ip>`

### Load a Spescific Interface <a href="#load-a-spescific-interface" id="load-a-spescific-interface"></a>

`nload <interfaceName>`\
e.x. interface name: eth0
