# MPLS BGP VPN with SOO

![Topology](./images/topology.png)

## Summary

MPLS L3VPN configuration supporting same customer AS number (AS 65000) at both sites. Site of Origin (SOO) prevents routing loops with unique site identifiers, while AS-OVERRIDE enables same-AS communication by replacing customer AS in BGP updates.

## Configs

- [CE1-A.cfg](./configs/CE1-A.cfg) - Customer Edge 1 (AS 65000)
- [PE1.cfg](./configs/PE1.cfg) - Provider Edge 1 (VRF + SOO + AS-OVERRIDE)
- [PE2.cfg](./configs/PE2.cfg) - Provider Edge 2 (VRF + SOO + AS-OVERRIDE)
- [CE2-A.cfg](./configs/CE2-A.cfg) - Customer Edge 2 (AS 65000)

## Verification

```
show bgp vpnv4 unicast vrf ISP_A
show ip bgp vrf ISP_A 192.168.2.0
ping vrf ISP_A 192.168.2.1 source 192.168.1.1
```

**Blog:** [Medium Article](link)
