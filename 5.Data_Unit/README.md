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

> Segment / Datagram (L4)

Consist of packets.<br>
Divided size of data from user layer.<br>
Maximum segment size, MSS.

> Packet (L3)

A devided fixed size of segment to transfer via internet.<br>
Maximum Transport Unit, MTU.<br>
The size of each packets' MTU is normally 1,500 bytes.

E.g. <br>
If the size of 'sushi.jpg' is 1.5MB and to transfer this on the internet, there will be more than 1000 packets to be delievered.

### Creation of Packets

Packet consists of Header and Payload.<br>
Header consists of IP and TCP headers, 20 bytes respectively.<br>
Think the header as the label stuck on the parcel, and the payload as the content of the parcel.

```
// Packet Header

L3  | L4  |...(L5+)
IP  | TCP |...(Higher level header)
```
One packet will normally have 1,460 bytes, the maximum segment size (MSS).

The segment will be chains of 1,460 payloads with a 40 byte header.

Action of looking inside a packet's payload is called DPI, deep packet inspection.<br>
China utilizes this for monitoring the network and the contents.

> ↓ Encapsulation

Packing segment into a packet, literally just like the action of packing a parcel.

> Frame (L2)

Imagine the frame as a cargo or a truck that is packed with a lot of packets.

> Bit / Symbol