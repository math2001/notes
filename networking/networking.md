# Networking

## Example of protocol which use `tcp/ip`

- HTTP, HTTPS - for web browsing,
- FTP, TFTP, NFS - for file transfer,
- SMTP - for sending email messages,
- POP3 - for receiving email messages,
- IMAP - for managing email messages on the server,
- Telnet, rLogin - for accessing remote computers,
- SNMP - for network management,
- DNS - for finding IP addresses assigned to Web addresses,
- IRC - for online chats

Port numbers are 16 bits integers (0 to 65535)

## A list of networking commands

This list of Linux Networking commands and scripts, will receive ongoing
updates, similar to the other lists on this blog…

This list of Linux Networking commands and scripts, will receive ongoing updates, similar to the other lists on this blog…

- `arpwatch` – Ethernet Activity Monitor.
- `bmon` – bandwidth monitor and rate estimator.
- `bwm-ng` – live network bandwidth monitor.
- `curl` – transferring data with URLs. (or try httpie)
- `darkstat` – captures network traffic, usage statistics.
- `dhclient` – Dynamic Host Configuration Protocol Client
- `dig` – query DNS servers for information.
- `dstat` – replacement for vmstat, iostat, mpstat, netstat and ifstat.
- `ethtool` – utility for controlling network drivers and hardware.
- `gated` – gateway routing daemon.
- `host` – DNS lookup utility.
- `hping` – TCP/IP packet assembler/analyzer.
- `ibmonitor` – shows bandwidth and total data transferred.
- `ifstat` –  report network interfaces bandwidth.
- `iftop` – display bandwidth usage.
- `ip` (PDF file) – a command with more features that ifconfig (net-tools).
- `iperf3` – network bandwidth measurement tool. (above screenshot Stacklinux VPS)
- `iproute2` – collection of utilities for controlling TCP/IP.
- `iptables` – take control of network traffic.
- `IPTraf` – An IP Network Monitor.
- `iputils` – set of small useful utilities for Linux networking.
- `iw` – a new nl80211 based CLI configuration utility for wireless devices.
- `jwhois` (whois) – client for the whois service.
- `“lsof` -i” – reveal information about your network sockets.
- `mtr` – network diagnostic tool.
- `net-tools` – utilities include: arp, hostname, ifconfig, netstat, rarp, route, plipconfig, slattach, mii-tool, iptunnel and ipmaddr.
- `ncat` – improved re-implementation of the venerable netcat.
- `netcat` – networking utility for reading/writing network connections.
- `nethogs` – a small ‘net top’ tool.
- `Netperf` – Network bandwidth Testing.
- `netsniff-ng` – Swiss army knife for daily Linux network plumbing.
- `netstat` – Print network connections, routing tables, statistics, etc.
- `netwatch` – monitoring Network Connections.
- `ngrep` – grep applied to the network layer.
- `nload` – display network usage.
- `nmap` – network discovery and security auditing.
- `nmcli` – a command-line tool for controlling NetworkManager and reporting network status.
- `nmtui` – provides a text interface to configure networking by controlling NetworkManager.
- `nslookup` – query Internet name servers interactively.
- `ping` – send icmp echo_request to network hosts.
- `route` – show / manipulate the IP routing table.
- `slurm` – network load monitor.
- `snort` – Network Intrusion Detection and Prevention System.
- `smokeping` –  keeps track of your network latency.
- `socat` – establishes two bidirectional byte streams and transfers data between them.
- `speedometer` – Measure and display the rate of data across a network.
- `speedtest-cli` – test internet bandwidth using speedtest.net
- `ss` – utility to investigate sockets.
- `ssh` –  secure system administration and file transfers over insecure networks.
- `tcpdump` – command-line packet analyzer.
- `tcptrack` – Displays information about tcp connections on a network interface.
- `telnet` – user interface to the TELNET protocol.
- `tracepath` – very similar function to traceroute.
- `traceroute` – print the route packets trace to network host.
- `vnStat` – network traffic monitor.
- `websocat` – Connection forwarder from/to web sockets to/from usual sockets, in style of socat.
- `wget` –  retrieving files using HTTP, HTTPS, FTP and FTPS.
- `Wireless Tools for Linux` – includes iwconfig, iwlist, iwspy, iwpriv and ifrename.
- `Wireshark`` – network protocol analyzer.

> Collected from <https://haydenjames.io/linux-networking-commands-scripts/>

## Adding network interface

It looks like a network interface is the same as a network device (in the terms
of the linux manual). Hence,

```
$ ip addr
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
    inet6 ::1/128 scope host
       valid_lft forever preferred_lft forever
2: enp0s25: <NO-CARRIER,BROADCAST,MULTICAST,UP> mtu 1500 qdisc fq_codel state DOWN group default qlen 1000
    link/ether 00:21:5a:24:83:3a brd ff:ff:ff:ff:ff:ff
4: wlx78321bad891c: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc mq state UP group default qlen 1000
    link/ether 78:32:1b:ad:89:1c brd ff:ff:ff:ff:ff:ff
    inet 192.168.1.4/24 brd 192.168.1.255 scope global noprefixroute wlx78321bad891c
       valid_lft forever preferred_lft forever
    inet6 fdfc:3f7c:3a73:ee00:4d47:25e8:1dbc:928c/64 scope global temporary dynamic
       valid_lft 6993sec preferred_lft 3393sec
    inet6 fdfc:3f7c:3a73:ee00:f791:8d32:d323:d60a/64 scope global dynamic mngtmpaddr noprefixroute
       valid_lft 6993sec preferred_lft 3393sec
    inet6 fe80::d36f:248a:4d15:f3c3/64 scope link noprefixroute
       valid_lft forever preferred_lft forever
5: docker0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc noqueue state UP group default
    link/ether 02:42:04:16:c1:43 brd ff:ff:ff:ff:ff:ff
    inet 172.17.0.1/16 brd 172.17.255.255 scope global docker0
       valid_lft forever preferred_lft forever
    inet6 fe80::42:4ff:fe16:c143/64 scope link
       valid_lft forever preferred_lft forever
43: vethda92348@if42: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc noqueue master docker0 state UP group default
    link/ether 76:3b:73:5b:b9:d8 brd ff:ff:ff:ff:ff:ff link-netnsid 0
    inet6 fe80::743b:73ff:fe5b:b9d8/64 scope link
       valid_lft forever preferred_lft forever
```


`lo`, `enp0s25`, `wlx78321bad891c`, `docker0` and `vethda92348@if42` are all
network interfaces.

### Adding a network interface

```
sudo ip -c link add test0 type bridge
```

Seems to creates the interface. Now, `ip addr` gives one more entry:

```
44: test0: <BROADCAST,MULTICAST> mtu 1500 qdisc noop state DOWN group default qlen 1000
    link/ether 1a:8f:9b:61:70:6b brd ff:ff:ff:ff:ff:ff
```

```
sudo ip -c addr add 203.0.113.0/24 dev test0
```

Configure its ip range (mask?)

```
$ ip addr
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
    inet6 ::1/128 scope host
       valid_lft forever preferred_lft forever
2: enp0s25: <NO-CARRIER,BROADCAST,MULTICAST,UP> mtu 1500 qdisc fq_codel state DOWN group default qlen 1000
    link/ether 00:21:5a:24:83:3a brd ff:ff:ff:ff:ff:ff
4: wlx78321bad891c: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc mq state UP group default qlen 1000
    link/ether 78:32:1b:ad:89:1c brd ff:ff:ff:ff:ff:ff
    inet 192.168.1.4/24 brd 192.168.1.255 scope global noprefixroute wlx78321bad891c
       valid_lft forever preferred_lft forever
    inet6 fdfc:3f7c:3a73:ee00:4d47:25e8:1dbc:928c/64 scope global temporary dynamic
       valid_lft 6944sec preferred_lft 3344sec
    inet6 fdfc:3f7c:3a73:ee00:f791:8d32:d323:d60a/64 scope global dynamic mngtmpaddr noprefixroute
       valid_lft 6944sec preferred_lft 3344sec
    inet6 fe80::d36f:248a:4d15:f3c3/64 scope link noprefixroute
       valid_lft forever preferred_lft forever
5: docker0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc noqueue state UP group default
    link/ether 02:42:04:16:c1:43 brd ff:ff:ff:ff:ff:ff
    inet 172.17.0.1/16 brd 172.17.255.255 scope global docker0
       valid_lft forever preferred_lft forever
    inet6 fe80::42:4ff:fe16:c143/64 scope link
       valid_lft forever preferred_lft forever
43: vethda92348@if42: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc noqueue master docker0 state UP group default
    link/ether 76:3b:73:5b:b9:d8 brd ff:ff:ff:ff:ff:ff link-netnsid 0
    inet6 fe80::743b:73ff:fe5b:b9d8/64 scope link
       valid_lft forever preferred_lft forever
44: test0: <BROADCAST,MULTICAST> mtu 1500 qdisc noop state DOWN group default qlen 1000
    link/ether 1a:8f:9b:61:70:6b brd ff:ff:ff:ff:ff:ff
    inet 203.0.113.0/24 scope global test0
       valid_lft forever preferred_lft forever
```

```
$ sudo ip -c link set test0 up
```

Brings the interface up (don't even know what that means). I just know that
when the wifi interface is down, the wifi doesn't work. So I guess it's an
on/off switch

```
$ ip addr
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
    inet6 ::1/128 scope host
       valid_lft forever preferred_lft forever
2: enp0s25: <NO-CARRIER,BROADCAST,MULTICAST,UP> mtu 1500 qdisc fq_codel state DOWN group default qlen 1000
    link/ether 00:21:5a:24:83:3a brd ff:ff:ff:ff:ff:ff
4: wlx78321bad891c: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc mq state UP group default qlen 1000
    link/ether 78:32:1b:ad:89:1c brd ff:ff:ff:ff:ff:ff
    inet 192.168.1.4/24 brd 192.168.1.255 scope global noprefixroute wlx78321bad891c
       valid_lft forever preferred_lft forever
    inet6 fdfc:3f7c:3a73:ee00:4d47:25e8:1dbc:928c/64 scope global temporary dynamic
       valid_lft 7198sec preferred_lft 3598sec
    inet6 fdfc:3f7c:3a73:ee00:f791:8d32:d323:d60a/64 scope global dynamic mngtmpaddr noprefixroute
       valid_lft 7198sec preferred_lft 3598sec
    inet6 fe80::d36f:248a:4d15:f3c3/64 scope link noprefixroute
       valid_lft forever preferred_lft forever
5: docker0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc noqueue state UP group default
    link/ether 02:42:04:16:c1:43 brd ff:ff:ff:ff:ff:ff
    inet 172.17.0.1/16 brd 172.17.255.255 scope global docker0
       valid_lft forever preferred_lft forever
    inet6 fe80::42:4ff:fe16:c143/64 scope link
       valid_lft forever preferred_lft forever
43: vethda92348@if42: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc noqueue master docker0 state UP group default
    link/ether 76:3b:73:5b:b9:d8 brd ff:ff:ff:ff:ff:ff link-netnsid 0
    inet6 fe80::743b:73ff:fe5b:b9d8/64 scope link
       valid_lft forever preferred_lft forever
44: test0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc noqueue state UNKNOWN group default qlen 1000
    link/ether 1a:8f:9b:61:70:6b brd ff:ff:ff:ff:ff:ff
    inet 203.0.113.0/24 scope global test0
       valid_lft forever preferred_lft forever
    inet6 fe80::188f:9bff:fe61:706b/64 scope link
       valid_lft forever preferred_lft forever
```

state is `UNKNOWN`, not `UP`.

Source: <http://jpetazzo.github.io/2013/10/16/configure-docker-bridge-network/>

Gonna try to delete it now:

```
$ ip link delete test0
```

Seems to bring everything back to normal

## Check open sockets with `ss`

```
$ ss # all sockets
$ ss -tl # tcp listening sockets
```


