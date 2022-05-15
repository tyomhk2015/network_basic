# Inline & Out of Path

Most of the cases 'network device' means 'inline' devices, which handles packets' bypass / drop.

```
// Inline structure

PC → L2 Access Switch → L2 Distribution Switch → Router (Gateway) → Firewall →  Internet
|-----------------------LAN------------------------------|--------------WAN------------|
```

### Port Mirroring

Usually, L2 distribution switch handlers the port mirroring.<br>
L2 distribution switch copies the flows that passes itself to a specific port. Then set the specific port as read-only mode. The copied one is absolutely the same to the original one, thus it is called 'mirroring'.
Since the info of flows were mirrored to other port, this is called the 'port mirroring'.

Port mirroring requires intensive operation, the CPU (or NPU) inside a switch will heat up. Not many network engineers want to do port mirroring because this does not result in favorable way.

### Out of path / Sensor

The mirrored port has structure of read-only, it can be called as 'Out of path', isolated from original / main flow of network.<br>


Another name for devices or mechanics which are 'out of path' could be called as sensor.<br>
Depending on the role or what the 'out of path' is sensing, it can have different name.

```
e.g.)
* Out of path that inspects packets which can cause harm to the network, this can be called 'troubleshooting sensor'
* Out of path that inspects packets to detect if there is any intrusions, this is called IDS. (Intrusion Detection System)
```

### Tab Switch

A switch that specialized at copying the network flow.<br>
It lets packets to bypass, if the packets are met or sent to specific interface requirements.

