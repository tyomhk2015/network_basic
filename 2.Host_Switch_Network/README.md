# Host, Switch, Network

> Host

A computer that is connected to network. (e.g. Internet)

Host can be divided into two parts.
  1. The network itself → Switch (e.g. Router, Firewall, IPS)
  2. The entity using the network. → End-point (e.g. Peer, Server, Client)

> Switch

A computer, or a host, that is the network itself. (e.g. Router, Firewall, IPS)

Main role of Switch is switching, filtering and forwarding network packets from one device to another.

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

> Network

Here, network refers as Internet.<br>
Internet consists of routers and DNS.<br>
```
Internet = Router + DNS(Domain Name System)
```


