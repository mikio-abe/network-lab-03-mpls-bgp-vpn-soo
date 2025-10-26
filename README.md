# MPLS BGP VPN with SOO

![Topology](./topology.jpg)

## Summary

MPLS L3VPN configuration supporting same customer AS number (AS 65000) at both sites. Site of Origin (SOO) prevents routing loops with unique site identifiers, while AS-OVERRIDE enables same-AS communication by replacing customer AS in BGP updates.

## Lab Environment

**Emulation Platform:**
- Hypervisor: VMware Workstation Pro
- Network Emulator: EVE-NG Community Edition
- Base OS: Ubuntu 22.04 LTS
- Router Platform: Cisco IOL (IOS on Linux)
- IOS Version: 15.x

**Topology:**
See topology.png for network diagram and device connections.
All configurations have been tested and verified in this environment.


## Configs

- [CE1.cfg](CE1.cfg) - Customer Edge 1 (AS 65000)
- [PE1.cfg](PE1.cfg) - Provider Edge 1 (VRF + SOO + AS-OVERRIDE)
- [PE2.cfg](PE2.cfg) - Provider Edge 2 (VRF + SOO + AS-OVERRIDE)
- [CE2.cfg](CE2.cfg) - Customer Edge 2 (AS 65000)

## Verification

```
show bgp vpnv4 unicast vrf ISP_A
show ip bgp vrf ISP_A 192.168.2.0
ping vrf ISP_A 192.168.2.1 source 192.168.1.1
```

**Blog:** [Medium Article](link)
