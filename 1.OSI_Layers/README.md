<a href="https://github.com/tyomhk2015/network_basic">Previous</a>

# <a href="https://en.wikipedia.org/wiki/OSI_model">OSI 7 Layers</a>

### TLDR

* Conceptual and standard flows, mechanisms, or protocols of communication between digital devices. <br>
* Describes how the data, or signals, from computers, or other digital devices have network function embedded, are transferred to other computers.

An example of the term 'conceptual' could be similar to 'MVC', Model-View-Controller, which is a concept of organizing and managing the flows and logics of web services.

※ The name and the classification varies on different fields. (<a href="https://en.wikipedia.org/wiki/Internet_protocol_suite#Layer_names_and_number_of_layers_in_the_literature">Link</a>)

```
// High Level ↑
                          Conceptual                Implementation
                      OSI 7            DOD
                  Application
User              Presentation      Application         Process
                  Session
Application SW                                          (Socket)
_________________________________________________________________________
Kernel            Transport         Transport           TCP
                  Network           Interet             IP
System SW                                               Driver
_________________________________________________________________________
HW                Data Link         Network Access      NIC
                  Physical

// Low Level ↓
```
### Legend

* User: End-users using and interacting with computers.
  * Application S/W: Software that are built on a platform, and used by end users. (e.g. Video games)
* <a href="https://en.wikipedia.org/wiki/Kernel_(operating_system)">Kernel</a>: A program in the core of OS that enables softwares and hardwares to communicate with each other.
* S/W: 
  * System S/W: Software that provides a platform. (e.g. OS)
* H/W:

### Terms

* User:
  * Socket: An interface, or a file, for allowing processes to use, access, and communcate with protocols that are in the 'Transport' layer, TCP.
* Kernel:
  * Driver: A device that allows to take control of H/W.
* H/W:
  * NIC: Network Interface Card (e.g. LAN card)


Personal Notes 🤔<br>
Don't start and get obsessed with OSI 7 Layer at the very beginning of your journey to network.This is not an implementation, it is just a concept.
For example, if you are planning to learn about TCP/IP which is not a concept and has tangible implementation, start with that first.
You can come back to OSI 7 layers later when situation needs the concept.

<hr>

# Identifier of each layers

```
// High Level ↑
                    Conceptual      Implementation    Identifier
                       DOD
User                Application       Process
Application SW                        (Socket)
_________________________________________________________________________
Kernel              Transport         TCP               Port
                    Interet           IP                IP
System SW                             Driver
_________________________________________________________________________
HW                  Network Access    NIC               MAC

// Low Level ↓
```

* Port
* IP address
* MAC address

> Port

　Identifier for TCP layer.<br>
　The definition of 'port' varies on different fields.

* S/W developers'perspective:
  * Process number
* L3, L4 network developers' perspective:
  * Service number
* H/W network developers' perspective:
  * Interface number, the numbers describing slots on router machines.


> IP Address

Identifier for Host.

　Host: <br>
　　A name for a device or computer that is connected to network, Internet.<br>
　　One device can have more than one IP address that bind with one NIC.<br>

> MAC Address

Identifier for NIC.

　NIC: Netowrk Interface Card<br>
　　Two types of NICs exist; wired LAN card, and wireless LAN card.<br>
　　One MAC address for one NIC.<br>
　　Sometimes called as a 'hardware address', and can be modified.