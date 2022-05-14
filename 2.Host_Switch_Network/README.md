# Host, Switch, Network

> Host

A computer that is connected to network. (e.g. Internet)

Host can be divided into two parts.
  1. The network itself → Switch (e.g. Router, Firewall, IPS)
  2. The entity using the network. → End-point (e.g. Peer, Server, Client)

> Switch

A computer, or a host, that is the network itself. (e.g. Router, Firewall, IPS)

Main role of Switch is switching, filtering and forwarding network packets from one device to another.<br>
In other words, Switch provides route selection, switching, for packets on network from start to designated computer.

One of goals of networking is finding an optimal route for packets.

There are many kinds of switcing depending on their purpose.<br>
Router is switch for purpose of finding routes.<br>
IPS or firewall is switch for security purpose, a.k.a security switch.<br>

```
// High Level ↑
                  Conceptual       Implementation          Identifier
                      OSI 7
                  Application
User              Presentation        Process
                  Session
_________________________________________________________________________
Kernel            Transport           TCP                     Port
                  Network             IP                      IP Address
_________________________________________________________________________
HW                Data Link      \   Ethernet (Wired)         MAC Address
                  Physical       /   802.11.xxx (Wireless)

// Low Level ↓
```

A switch using MAC address is called 'L2 switch'.
A switch using IP address is called 'L3 switch'.
A switch using Port is called 'L4 switch'.
A switch using Process is called 'L7 switch'.

The higher the level gets, the cost will increase as the data get more complex than lower level

### L2 Switch

For windows users, you can find physical address using 'ipconfig' command in command prompt. (MAC address)

L2 Access Switch<br>
The first switch that end-points encounter, or the closest switch of end-points.

L2 Distribution Switch<br>
A switch for L2 Access Switches, for communicating other end-points that is connected to different L2 Access Switchs.

```
E.g. (Uplink*)
L2 Access Switch = Room
L2 Distribution Switch = A floor of a building with a lot of rooms.

* Direction of network going from low level to higher level.

Link-up: Means 'connected' to network, usually shows green light on the NIC.
Link-down: Means 'not connected' to network.
```

```
The flow from an end-point to internet.

End-point → L2 Access Switch → L2 Distribution Switch → Router (L3, Role of Gateway) → Internet
```
If L2 Distibution Switch is a floor with multiple rooms, the router could be put as a building.



> Network

Here, network refers as Internet.<br>
Internet consists of routers and DNS.*<br>
Internet is a set of routers (L3 switch).<br>
```
Internet = Router + DNS(Domain Name System)

*DNS:
A system that gives you the IP address of the domain name that client have requested, usually at address bar of the browsers.
A big database of having domain name and IP address mapped. (E.g. Phonebook)
```

Routers communicate each other to find optimal routes for different incoming packets.<br>
Internet is desgined to be functional even thought a few routes could not be functional.

Routing table is used to find an optimal routes for packets<br>
This is like a road sign for packets and gives some standards for choosing/selecting routes for packets.