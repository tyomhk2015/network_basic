# Port

### TLDR

(From S/W developers' perspective)<br>
A road sign for directing incoming packets' destination.


```
// High Level ↑
User        Process

            File/Socket (Port is one of the many attachments to socket)
_________________________________________________________________________
Kernel      TCP
            IP

            Driver
_________________________________________________________________________
HW          NIC

// Low Level ↓
```

Port:
  * One of the many attachments to a socket
  * 16 bit (2^16)
  * Theoratically 0 ~ 65535 can be expressed, but 0 and 65535 is forbidden to be used.
  * Identifier for processes (Devs' perspective)
  * A road sign for directing incoming packets'* destination

*Packet: A unit of some data from network.

Packets, incoming from outside of the host, initially arrive and H/W, then move to Kernel, and finally reach their designated application process.

```
(Network) → H/W → Kernel → User
(Network) → NIC → Driver → IP → TCP → (Socket) → Process
```

During the TCP stages, packets final destination will depend on the port number that is described in the socket from TCP/IP.