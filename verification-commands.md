# Verification Commands

## VRF
Check VRF configuration and routing table
```
show ip vrf
show ip route vrf ISP_A
```

## SOO (Site of Origin)
Check SOO extended community on routes
```
show bgp vpnv4 unicast vrf ISP_A
show bgp vpnv4 unicast vrf ISP_A 192.168.1.0/24
show bgp vpnv4 unicast vrf ISP_A 192.168.2.0/24
```

## AS-OVERRIDE
Check AS_PATH modification by AS-OVERRIDE
```
show ip bgp vrf ISP_A
show ip bgp vrf ISP_A 192.168.2.0
show ip bgp vrf ISP_A neighbors 10.101.1.2 advertised-routes
```

## MP-BGP
Check VPNv4 route exchange
```
show ip bgp vpnv4 all summary
show ip bgp vpnv4 vrf ISP_A
```

## MPLS
Check LDP neighbor and label forwarding
```
show mpls ldp neighbor
show mpls forwarding-table vrf ISP_A
```

## Same-AS Communication
Test connectivity between same AS sites
```
ping vrf ISP_A 192.168.2.1 source 192.168.1.1
traceroute vrf ISP_A 192.168.2.1 source 192.168.1.1
```

## CE Verification
Check BGP on CE routers
```
show ip bgp
show ip bgp 192.168.2.0
show ip bgp summary
```
