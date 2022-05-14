# Router

L3 Switch that uses packets.

One router has at least two network interfaces.
1. Linking to a L2 distribution switch
2. Connecting to internet

Routers do have their own IP address, which means they are also a sort of computer.

```
PC → L2 Access Switch → L2 Distribution Switch → Router → Internet
```

```
// High Level ↑, higher cost

User              Process
_________________________________________________________________________
Kernel            TCP
                  IP (L3)
_________________________________________________________________________
HW                NIC #1        NIC #2

// Low Level ↓, lower cost
```

Router is an '**inline** equipment'.<br>
The term 'inline' means something that bypasses or drops packets.<br>
The type of packets are '**bypassed**' and '**dropped**' packets.<br>
Therefore, inline equipments means a machine that bypasses or drops **inbound**/**outbound** packets.

```
Inbound:
  The signals that came from internet to LAN.
Outbound:
  The signals that going from LAN to internet.
```

When signals from network go beyond the border line of each layer, the cost of computing and dealing those signals gets higher.

Not only the cost of computing but also there will be some delays for the signals to be verified for their next steps.

If signals were transported form NIC #1 to #2, the computation cost and time for verifying the signals will much lower than any other layers. The signals are conveyed via hardwares, NIC, are also called 'hardware accelerated', something is done with support of hardwares.

The signals from network can be computed at three spots, at ①NIC, ②IP, and ③Process. The signals that is computed or had some logic operation in NIC is the quickest.

### ②IP
If there are more than 2 NICs connect to a router, the packets coming into layer 3 must decide a NIC, interface selection. 

In IP's perspective, when the packets are read, they have to be written to somewhere. At the point, the routers have to choose the interface, NIC. If the router cannot decide the interface for writing the packets, then the packets is **dropped**. In contrast, if the interface is decided, the packets are **bypassed**. The decision will be done by referring to IP address of packets.

### /End of ②IP

Inline equiments have responsibilities to either bypass or drop the inbounding/outbounding packets.

If the inline equipments only does the routings, the the equipment is called '**router**'.

If the inline equipments filter some packets due to security concerns, the this is called '**firewall**', packet filtering firewall.

The structure of the firewall and router almost the same.