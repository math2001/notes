```
$ ip -c addr
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
       valid_lft 7057sec preferred_lft 3457sec
    inet6 fdfc:3f7c:3a73:ee00:f791:8d32:d323:d60a/64 scope global dynamic mngtmpaddr noprefixroute
       valid_lft 7057sec preferred_lft 3457sec
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
