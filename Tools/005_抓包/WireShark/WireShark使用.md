

[wireshark - docs](https://www.wireshark.org/docs/wsug_html_chunked/index.html)



常见协议

* ARP

* ICMP

* TCP

* UDP

* DNS

* HTTP

    



# ifconfig介绍

* [stackoverflow - ifconfig](https://stackoverflow.com/questions/29958143/what-are-en0-en1-p2p-and-so-on-that-are-displayed-after-executing-ifconfig)

```bash
$ ifconfig                                                                                                                                       
lo0: flags=8049<UP,LOOPBACK,RUNNING,MULTICAST> mtu 16384
	options=1203<RXCSUM,TXCSUM,TXSTATUS,SW_TIMESTAMP>
	inet 127.0.0.1 netmask 0xff000000
	inet6 ::1 prefixlen 128
	inet6 fe80::1%lo0 prefixlen 64 scopeid 0x1
	nd6 options=201<PERFORMNUD,DAD>
gif0: flags=8010<POINTOPOINT,MULTICAST> mtu 1280
stf0: flags=0<> mtu 1280
anpi2: flags=8863<UP,BROADCAST,SMART,RUNNING,SIMPLEX,MULTICAST> mtu 1500
	options=400<CHANNEL_IO>
	ether 9e:99:d9:bd:3a:47
	inet6 fe80::9c99:d9ff:febd:3a47%anpi2 prefixlen 64 scopeid 0x4
	nd6 options=201<PERFORMNUD,DAD>
	media: none
	status: inactive
anpi0: flags=8863<UP,BROADCAST,SMART,RUNNING,SIMPLEX,MULTICAST> mtu 1500
	options=400<CHANNEL_IO>
	ether 9e:99:d9:bd:3a:45
	inet6 fe80::9c99:d9ff:febd:3a45%anpi0 prefixlen 64 scopeid 0x5
	nd6 options=201<PERFORMNUD,DAD>
	media: none
	status: inactive
anpi1: flags=8863<UP,BROADCAST,SMART,RUNNING,SIMPLEX,MULTICAST> mtu 1500
	options=400<CHANNEL_IO>
	ether 9e:99:d9:bd:3a:46
	inet6 fe80::9c99:d9ff:febd:3a46%anpi1 prefixlen 64 scopeid 0x6
	nd6 options=201<PERFORMNUD,DAD>
	media: none
	status: inactive
en4: flags=8863<UP,BROADCAST,SMART,RUNNING,SIMPLEX,MULTICAST> mtu 1500
	options=400<CHANNEL_IO>
	ether 9e:99:d9:bd:3a:25
	nd6 options=201<PERFORMNUD,DAD>
	media: none
	status: inactive
en5: flags=8863<UP,BROADCAST,SMART,RUNNING,SIMPLEX,MULTICAST> mtu 1500
	options=400<CHANNEL_IO>
	ether 9e:99:d9:bd:3a:26
	nd6 options=201<PERFORMNUD,DAD>
	media: none
	status: inactive
en6: flags=8863<UP,BROADCAST,SMART,RUNNING,SIMPLEX,MULTICAST> mtu 1500
	options=400<CHANNEL_IO>
	ether 9e:99:d9:bd:3a:27
	nd6 options=201<PERFORMNUD,DAD>
	media: none
	status: inactive
en1: flags=8963<UP,BROADCAST,SMART,RUNNING,PROMISC,SIMPLEX,MULTICAST> mtu 1500
	options=460<TSO4,TSO6,CHANNEL_IO>
	ether 36:63:02:90:b7:40
	media: autoselect <full-duplex>
	status: inactive
en2: flags=8963<UP,BROADCAST,SMART,RUNNING,PROMISC,SIMPLEX,MULTICAST> mtu 1500
	options=460<TSO4,TSO6,CHANNEL_IO>
	ether 36:63:02:90:b7:44
	media: autoselect <full-duplex>
	status: inactive
en3: flags=8963<UP,BROADCAST,SMART,RUNNING,PROMISC,SIMPLEX,MULTICAST> mtu 1500
	options=460<TSO4,TSO6,CHANNEL_IO>
	ether 36:63:02:90:b7:48
	media: autoselect <full-duplex>
	status: inactive
ap1: flags=8843<UP,BROADCAST,RUNNING,SIMPLEX,MULTICAST> mtu 1500
	options=6463<RXCSUM,TXCSUM,TSO4,TSO6,CHANNEL_IO,PARTIAL_CSUM,ZEROINVERT_CSUM>
	ether 7e:e9:1e:b2:06:1f
	inet6 fe80::7ce9:1eff:feb2:61f%ap1 prefixlen 64 scopeid 0xd
	nd6 options=201<PERFORMNUD,DAD>
	media: autoselect
en0: flags=8863<UP,BROADCAST,SMART,RUNNING,SIMPLEX,MULTICAST> mtu 1500
	options=6463<RXCSUM,TXCSUM,TSO4,TSO6,CHANNEL_IO,PARTIAL_CSUM,ZEROINVERT_CSUM>
	ether 5c:e9:1e:b2:06:1f
	inet6 fe80::892:c40d:ee29:fc0a%en0 prefixlen 64 secured scopeid 0xe
	inet 192.168.110.127 netmask 0xffffff00 broadcast 192.168.110.255
	nd6 options=201<PERFORMNUD,DAD>
	media: autoselect
	status: active
bridge0: flags=8863<UP,BROADCAST,SMART,RUNNING,SIMPLEX,MULTICAST> mtu 1500
	options=63<RXCSUM,TXCSUM,TSO4,TSO6>
	ether 36:63:02:90:b7:40
	Configuration:
		id 0:0:0:0:0:0 priority 0 hellotime 0 fwddelay 0
		maxage 0 holdcnt 0 proto stp maxaddr 100 timeout 1200
		root id 0:0:0:0:0:0 priority 0 ifcost 0 port 0
		ipfilter disabled flags 0x0
	member: en1 flags=3<LEARNING,DISCOVER>
	        ifmaxaddr 0 port 10 priority 0 path cost 0
	member: en2 flags=3<LEARNING,DISCOVER>
	        ifmaxaddr 0 port 11 priority 0 path cost 0
	member: en3 flags=3<LEARNING,DISCOVER>
	        ifmaxaddr 0 port 12 priority 0 path cost 0
	nd6 options=201<PERFORMNUD,DAD>
	media: <unknown type>
	status: inactive
awdl0: flags=8843<UP,BROADCAST,RUNNING,SIMPLEX,MULTICAST> mtu 1500
	options=6463<RXCSUM,TXCSUM,TSO4,TSO6,CHANNEL_IO,PARTIAL_CSUM,ZEROINVERT_CSUM>
	ether 16:1f:b7:3b:6c:a2
	inet6 fe80::141f:b7ff:fe3b:6ca2%awdl0 prefixlen 64 scopeid 0x10
	nd6 options=201<PERFORMNUD,DAD>
	media: autoselect
	status: active
llw0: flags=8863<UP,BROADCAST,SMART,RUNNING,SIMPLEX,MULTICAST> mtu 1500
	options=400<CHANNEL_IO>
	ether 16:1f:b7:3b:6c:a2
	inet6 fe80::141f:b7ff:fe3b:6ca2%llw0 prefixlen 64 scopeid 0x11
	nd6 options=201<PERFORMNUD,DAD>
	media: autoselect
	status: inactive
utun0: flags=8051<UP,POINTOPOINT,RUNNING,MULTICAST> mtu 2000
	inet6 fe80::21a3:856e:843b:37ca%utun0 prefixlen 64 scopeid 0x12
	nd6 options=201<PERFORMNUD,DAD>
utun1: flags=8051<UP,POINTOPOINT,RUNNING,MULTICAST> mtu 1380
	inet6 fe80::b72b:1692:da40:505d%utun1 prefixlen 64 scopeid 0x13
	nd6 options=201<PERFORMNUD,DAD>
utun2: flags=8051<UP,POINTOPOINT,RUNNING,MULTICAST> mtu 1000
	inet6 fe80::ce81:b1c:bd2c:69e%utun2 prefixlen 64 scopeid 0x14
	nd6 options=201<PERFORMNUD,DAD>
utun3: flags=8051<UP,POINTOPOINT,RUNNING,MULTICAST> mtu 1380
	inet6 fe80::5e4c:f0e1:f625:7626%utun3 prefixlen 64 scopeid 0x15
	nd6 options=201<PERFORMNUD,DAD>
utun4: flags=8051<UP,POINTOPOINT,RUNNING,MULTICAST> mtu 1380
	inet6 fe80::fd3b:ee4c:5961:1c1d%utun4 prefixlen 64 scopeid 0x16
	nd6 options=201<PERFORMNUD,DAD>
en7: flags=8822<BROADCAST,SMART,SIMPLEX,MULTICAST> mtu 1500 constrained
	options=400<CHANNEL_IO>
	ether da:dc:40:5a:ef:fc
	media: autoselect <full-duplex>
	status: inactive
en9: flags=8863<UP,BROADCAST,SMART,RUNNING,SIMPLEX,MULTICAST> mtu 1500
	options=400<CHANNEL_IO>
	ether da:dc:40:5a:ef:03
	inet6 fe80::1893:c6e3:4a21:2b56%en9 prefixlen 64 secured scopeid 0x18
	inet 169.254.153.227 netmask 0xffff0000 broadcast 169.254.255.255
	nd6 options=201<PERFORMNUD,DAD>
	media: autoselect (100baseTX <full-duplex>)
	status: active
en8: flags=8863<UP,BROADCAST,SMART,RUNNING,SIMPLEX,MULTICAST> mtu 1500
	options=400<CHANNEL_IO>
	ether 22:ec:90:f4:3a:27
	inet6 fe80::20ec:90ff:fef4:3a27%en8 prefixlen 64 scopeid 0x19
	nd6 options=201<PERFORMNUD,DAD>
	media: autoselect
	status: active
```





## lo0

> lo0: loopback 回环地址一般是127.0.0.1
>
> loopback指本地环回接口（或地址），亦称回送地址()。此类接口是应用最为广泛的一种虚接口，几乎在每台路由器上都会使用。



## gif0

>  gif0: software Network Interface



## stf0





# wireshark过滤器



















