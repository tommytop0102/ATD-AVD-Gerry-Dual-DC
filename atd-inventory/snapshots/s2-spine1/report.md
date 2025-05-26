# s2-spine1 Commands Output

## Table of Contents

- [show lldp neighbors](#show-lldp-neighbors)
- [show ip interface brief](#show-ip-interface-brief)
- [show interfaces description](#show-interfaces-description)
- [show version](#show-version)
- [show running-config](#show-running-config)
## show interfaces description

```
Interface                      Status         Protocol           Description
Et1                            up             up                 
Et2                            up             up                 P2P_LINK_TO_S2-LEAF1_Ethernet2
Et3                            up             up                 P2P_LINK_TO_S2-LEAF2_Ethernet2
Et4                            up             up                 P2P_LINK_TO_S2-LEAF3_Ethernet2
Et5                            up             up                 P2P_LINK_TO_S2-LEAF4_Ethernet2
Et6                            up             up                 
Et7                            up             up                 P2P_LINK_TO_S2-BRDR1_Ethernet2
Et8                            up             up                 P2P_LINK_TO_S2-BRDR2_Ethernet2
Lo0                            up             up                 EVPN_Overlay_Peering
Ma0                            up             up
```
## show ip interface brief

```
Address
Interface       IP Address            Status     Protocol         MTU   Owner  
--------------- --------------------- ---------- ------------ --------- -------
Ethernet2       172.32.255.200/31     up         up              1500          
Ethernet3       172.32.255.204/31     up         up              1500          
Ethernet4       172.32.255.208/31     up         up              1500          
Ethernet5       172.32.255.212/31     up         up              1500          
Ethernet7       172.32.255.216/31     up         up              1500          
Ethernet8       172.32.255.220/31     up         up              1500          
Loopback0       192.2.255.1/32        up         up             65535          
Management0     192.168.0.20/24       up         up              1500
```
## show lldp neighbors

```
Last table change time   : 6:23:06 ago
Number of table inserts  : 11
Number of table deletes  : 3
Number of table drops    : 0
Number of table age-outs : 0

Port          Neighbor Device ID       Neighbor Port ID    TTL
---------- ------------------------ ---------------------- ---
Et1           s2-spine2.atd.lab        Ethernet1           120
Et2           s2-leaf1.atd.lab         Ethernet2           120
Et3           s2-leaf2.atd.lab         Ethernet2           120
Et4           s2-leaf3.atd.lab         Ethernet2           120
Et5           s2-leaf4.atd.lab         Ethernet2           120
Et6           s2-spine2.atd.lab        Ethernet6           120
Et7           s2-brdr1.atd.lab         Ethernet2           120
Et8           s2-brdr2.atd.lab         Ethernet2           120
```
## show running-config

```
! Command: show running-config
! device: s2-spine1 (cEOSLab, EOS-4.33.0F-39050855.4330F (engineering build))
!
no aaa root
!
username admin privilege 15 role network-admin secret 5 $1$5O85YVVn$HrXcfOivJEnISTMb6xrJc.
username arista privilege 15 role network-admin secret 5 $1$4VjIjfd1$XkUVulbNDESHFzcxDU.Tk1
username arista ssh-key ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQCyut6vmeyYq3uPXAhQsye2YsSIeKoONAw9Y0/mY7cKdJkkWdq83GZAkiqGTb8W5THHYbGNqJTHfCm7oM2+qp3AcDZbNs2i1v09FNz7U2uLqeyZx1UZTtD+ww/qQr/u0+Y0HnOxb8QoXBX9YkvLA4xJ4vlVk4QsKf4ikLPHJzRVMwvI8BjlkL3RB/y6NvZKt3WqU7G2q+8Gwl+R2V35oygfFrzDVBPhvkHkBtgdHYaz7ML5Sg6E+RU6DyubfKTTt7WmoXheRRaKrrbabmSoS5Nk/07DSYYxR1ei4XEx8aciaCjJ4UrF3IearfydjeYqI3x4gXSGrHn+L+Cc0KVsZp4R arista@avd-gerry-1-f3158c0b-eos
!
management api http-commands
   no shutdown
   !
   vrf default
      no shutdown
!
daemon TerminAttr
   exec /usr/bin/TerminAttr -cvcompression=gzip -smashexcludes=ale,flexCounter,hardware,kni,pulse,strata -ingestexclude=/Sysdb/cell/1/agent,/Sysdb/cell/2/agent -cvaddr=192.168.0.5:9910 -cvauth=token,/tmp/token -cvvrf=default -taillogs -disableaaa
   no shutdown
!
vlan internal order ascending range 1006 1199
!
no service interface inactive port-id allocation disabled
!
transceiver qsfp default-mode 4x10G
!
service routing protocols model multi-agent
!
hostname s2-spine1
ip name-server vrf default 8.8.8.8
ip name-server vrf default 168.95.1.1
ip name-server vrf default 192.168.2.1
dns domain atd.lab
!
spanning-tree mode none
!
system l1
   unsupported speed action error
   unsupported error-correction action error
!
radius-server host 192.168.0.1 key 7 0207165218120E
!
aaa group server radius atds
   server 192.168.0.1
!
aaa authentication login default group atds local
aaa authorization exec default group atds local
aaa authorization commands all default local
!
interface Ethernet1
!
interface Ethernet2
   description P2P_LINK_TO_S2-LEAF1_Ethernet2
   mtu 1500
   no switchport
   ip address 172.32.255.200/31
!
interface Ethernet3
   description P2P_LINK_TO_S2-LEAF2_Ethernet2
   mtu 1500
   no switchport
   ip address 172.32.255.204/31
!
interface Ethernet4
   description P2P_LINK_TO_S2-LEAF3_Ethernet2
   mtu 1500
   no switchport
   ip address 172.32.255.208/31
!
interface Ethernet5
   description P2P_LINK_TO_S2-LEAF4_Ethernet2
   mtu 1500
   no switchport
   ip address 172.32.255.212/31
!
interface Ethernet6
!
interface Ethernet7
   description P2P_LINK_TO_S2-BRDR1_Ethernet2
   mtu 1500
   no switchport
   ip address 172.32.255.216/31
!
interface Ethernet8
   description P2P_LINK_TO_S2-BRDR2_Ethernet2
   mtu 1500
   no switchport
   ip address 172.32.255.220/31
!
interface Loopback0
   description EVPN_Overlay_Peering
   ip address 192.2.255.1/32
!
interface Management0
   description oob_management
   ip address 192.168.0.20/24
!
ip routing
!
ip prefix-list PL-LOOPBACKS-EVPN-OVERLAY
   seq 10 permit 192.2.255.0/24 eq 32
!
ip route 0.0.0.0/0 192.168.0.1
!
ntp server 10.70.32.146 prefer iburst
ntp server 10.70.32.147 prefer iburst
ntp server 192.168.0.1 iburst source Management0
!
ip radius source-interface Management0
!
route-map RM-CONN-2-BGP permit 10
   match ip address prefix-list PL-LOOPBACKS-EVPN-OVERLAY
!
router bfd
   multihop interval 1200 min-rx 1200 multiplier 3
!
router bgp 65002
   router-id 192.2.255.1
   no bgp default ipv4-unicast
   distance bgp 20 200 200
   graceful-restart restart-time 300
   graceful-restart
   maximum-paths 4 ecmp 4
   neighbor EVPN-OVERLAY-PEERS peer group
   neighbor EVPN-OVERLAY-PEERS next-hop-unchanged
   neighbor EVPN-OVERLAY-PEERS update-source Loopback0
   neighbor EVPN-OVERLAY-PEERS bfd
   neighbor EVPN-OVERLAY-PEERS ebgp-multihop 3
   neighbor EVPN-OVERLAY-PEERS send-community
   neighbor EVPN-OVERLAY-PEERS maximum-routes 0
   neighbor IPv4-UNDERLAY-PEERS peer group
   neighbor IPv4-UNDERLAY-PEERS send-community
   neighbor IPv4-UNDERLAY-PEERS maximum-routes 12000
   neighbor 172.32.255.201 peer group IPv4-UNDERLAY-PEERS
   neighbor 172.32.255.201 remote-as 65201
   neighbor 172.32.255.201 description s2-leaf1_Ethernet2
   neighbor 172.32.255.205 peer group IPv4-UNDERLAY-PEERS
   neighbor 172.32.255.205 remote-as 65201
   neighbor 172.32.255.205 description s2-leaf2_Ethernet2
   neighbor 172.32.255.209 peer group IPv4-UNDERLAY-PEERS
   neighbor 172.32.255.209 remote-as 65202
   neighbor 172.32.255.209 description s2-leaf3_Ethernet2
   neighbor 172.32.255.213 peer group IPv4-UNDERLAY-PEERS
   neighbor 172.32.255.213 remote-as 65202
   neighbor 172.32.255.213 description s2-leaf4_Ethernet2
   neighbor 172.32.255.217 peer group IPv4-UNDERLAY-PEERS
   neighbor 172.32.255.217 remote-as 65203
   neighbor 172.32.255.217 description s2-brdr1_Ethernet2
   neighbor 172.32.255.221 peer group IPv4-UNDERLAY-PEERS
   neighbor 172.32.255.221 remote-as 65203
   neighbor 172.32.255.221 description s2-brdr2_Ethernet2
   neighbor 192.2.255.53 peer group EVPN-OVERLAY-PEERS
   neighbor 192.2.255.53 remote-as 65201
   neighbor 192.2.255.53 description s2-leaf1
   neighbor 192.2.255.54 peer group EVPN-OVERLAY-PEERS
   neighbor 192.2.255.54 remote-as 65201
   neighbor 192.2.255.54 description s2-leaf2
   neighbor 192.2.255.55 peer group EVPN-OVERLAY-PEERS
   neighbor 192.2.255.55 remote-as 65202
   neighbor 192.2.255.55 description s2-leaf3
   neighbor 192.2.255.56 peer group EVPN-OVERLAY-PEERS
   neighbor 192.2.255.56 remote-as 65202
   neighbor 192.2.255.56 description s2-leaf4
   neighbor 192.2.255.57 peer group EVPN-OVERLAY-PEERS
   neighbor 192.2.255.57 remote-as 65203
   neighbor 192.2.255.57 description s2-brdr1
   neighbor 192.2.255.58 peer group EVPN-OVERLAY-PEERS
   neighbor 192.2.255.58 remote-as 65203
   neighbor 192.2.255.58 description s2-brdr2
   redistribute connected route-map RM-CONN-2-BGP
   !
   address-family evpn
      neighbor EVPN-OVERLAY-PEERS activate
   !
   address-family ipv4
      no neighbor EVPN-OVERLAY-PEERS activate
      neighbor IPv4-UNDERLAY-PEERS activate
!
router multicast
   ipv4
      routing
      software-forwarding sfe
   !
   ipv6
      software-forwarding kernel
!
end
```
## show version

```
Arista cEOSLab
Hardware version: 
Serial number: s2-spine1
Hardware MAC address: 001c.73c0.c620
System MAC address: 001c.73c0.c620

Software image version: 4.33.0F-39050855.4330F (engineering build)
Architecture: i686
Internal build version: 4.33.0F-39050855.4330F
Internal build ID: ff38b52c-4b4f-4a3f-b591-ef310b5ac8ca
Image format version: 1.0
Image optimization: None

Kernel version: 5.14.0-503.21.1.el9_5.x86_64

Uptime: 1 hour and 5 minutes
Total memory: 49062200 kB
Free memory: 3947440 kB
```
