# Proxy
(Application Proxy)

> Proxy
<a href="https://www.google.com/search?q=proxy+meaning&rlz=1C1MRIB_koJP962JP962&oq=proxy+meaning&aqs=chrome..69i57.1399j0j7&sourceid=chrome&ie=UTF-8">(From google search)</a>
* The authority to represent someone else, especially in voting.
* A figure that can be used to represent the value of something in a calculation.

To simplifiy the term of proxy, it can be an 'agent' or something that represents the original.

```
// Network flow without proxy
PC → Internet → Google

// Network flow with proxy
PC → PC-2 → Internet → Google
```

In PC-2's perspective, it listens for inbound from one of its sockets, and send the inbound packets/streams to other sockets for outbound.

```
// High Level ↑
                  HTTP        Process ← Runs proxy
User              SSL         Socket_1  Socket_2
                              (Listen)  (Transfer)
_________________________________________________________________________
Kernel            TCP
                  IP
_________________________________________________________________________
HW                NIC
                  (Physical)

// Low Level ↓
```

If there is a proxy in application layer or in process, it could be called as 'user mode application proxy', uses sockets and streams for communication.