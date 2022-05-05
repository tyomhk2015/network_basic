# Data Unit

(From network's prespecive)

Data unit in network

```
// High Level ↑
                  OSI 7             Data Unit                  Transform
                  Application
User              Presentation      Stream / Data
                  Session                                      ↓ Segmentation
_________________________________________________________________________
Kernel            Transport         Segment / Datagram (TCP)
                  Network           Packet (IP)                ↓ Encapsulation
_________________________________________________________________________
HW                Data Link         Frame
                  Physical          Bit / Symbol

// Low Level ↓
```

## Terms

> Stream / Data

A data from user layer that may have unfixed size.

> ↓ Segmentation

Process of dividing stream/data into small fixed sizes, segment.<br>
To send a data via network, segmentation is a must.

> Segment / Datagram

Consist of packets.<br>
Divided size of data from user layer.<br>
Maximum segment size, MSS.

> Packet

A devided fixed size of segment to transfer via internet.<br>
Maximum Transport Unit, MTU.<br>
The size of each packets' MTU is normally 1,500 bytes.

E.g. <br>
If the size of 'sushi.jpg' is 1.5MB and to transfer this on the internet, there will be more than 1000 packets to be delievered.


> ↓ Encapsulation

> Frame

> Bit / Symbol