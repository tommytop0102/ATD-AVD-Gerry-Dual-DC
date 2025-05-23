# s1-spine1 Commands Output

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
Et2                            up             up                 P2P_LINK_TO_S1-LEAF1_Ethernet2
Et3                            up             up                 P2P_LINK_TO_S1-LEAF2_Ethernet2
Et4                            up             up                 P2P_LINK_TO_S1-LEAF3_Ethernet2
Et5                            up             up                 P2P_LINK_TO_S1-LEAF4_Ethernet2
Et6                            up             up                 
Et7                            down           down               
Et8                            down           down               
Lo0                            up             up                 EVPN_Overlay_Peering
Ma0                            up             up
```
## show ip interface brief

```
Address
Interface       IP Address           Status     Protocol         MTU    Owner  
--------------- -------------------- ---------- ------------ ---------- -------
Ethernet2       172.30.255.0/31      up         up              1500           
Ethernet3       172.30.255.4/31      up         up              1500           
Ethernet4       172.30.255.8/31      up         up              1500           
Ethernet5       172.30.255.12/31     up         up              1500           
Loopback0       192.0.255.1/32       up         up             65535           
Management0     192.168.0.10/24      up         up              1500
```
## show lldp neighbors

```
Last table change time   : 7:45:18 ago
Number of table inserts  : 8
Number of table deletes  : 2
Number of table drops    : 0
Number of table age-outs : 0

Port          Neighbor Device ID       Neighbor Port ID    TTL
---------- ------------------------ ---------------------- ---
Et1           s1-spine2.atd.lab        Ethernet1           120
Et2           s1-leaf1.atd.lab         Ethernet2           120
Et3           s1-leaf2.atd.lab         Ethernet2           120
Et4           s1-leaf3.atd.lab         Ethernet2           120
Et5           s1-leaf4.atd.lab         Ethernet2           120
Et6           s1-spine2.atd.lab        Ethernet6           120
```
## show running-config

```
! Command: show running-config
! device: s1-spine1 (cEOSLab, EOS-4.33.0F-39050855.4330F (engineering build))
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
hostname s1-spine1
ip name-server vrf default 8.8.8.8
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
   description P2P_LINK_TO_S1-LEAF1_Ethernet2
   mtu 1500
   no switchport
   ip address 172.30.255.0/31
!
interface Ethernet3
   description P2P_LINK_TO_S1-LEAF2_Ethernet2
   mtu 1500
   no switchport
   ip address 172.30.255.4/31
!
interface Ethernet4
   description P2P_LINK_TO_S1-LEAF3_Ethernet2
   mtu 1500
   no switchport
   ip address 172.30.255.8/31
!
interface Ethernet5
   description P2P_LINK_TO_S1-LEAF4_Ethernet2
   mtu 1500
   no switchport
   ip address 172.30.255.12/31
!
interface Ethernet6
!
interface Ethernet7
!
interface Ethernet8
!
interface Loopback0
   description EVPN_Overlay_Peering
   ip address 192.0.255.1/32
!
interface Management0
   description oob_management
   ip address 192.168.0.10/24
!
ip routing
!
ip prefix-list PL-LOOPBACKS-EVPN-OVERLAY
   seq 10 permit 192.0.255.0/24 eq 32
!
ip route 0.0.0.0/0 192.168.0.1
!
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
router bgp 65001
   router-id 192.0.255.1
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
   neighbor EVPN-OVERLAY-PEERS password 7 q+VNViP5i4rVjW1cxFv2wA==
   neighbor EVPN-OVERLAY-PEERS send-community
   neighbor EVPN-OVERLAY-PEERS maximum-routes 0
   neighbor IPv4-UNDERLAY-PEERS peer group
   neighbor IPv4-UNDERLAY-PEERS password 7 AQQvKeimxJu+uGQ/yYvv9w==
   neighbor IPv4-UNDERLAY-PEERS send-community
   neighbor IPv4-UNDERLAY-PEERS maximum-routes 12000
   neighbor 172.30.255.1 peer group IPv4-UNDERLAY-PEERS
   neighbor 172.30.255.1 remote-as 65101
   neighbor 172.30.255.1 description s1-leaf1_Ethernet2
   neighbor 172.30.255.5 peer group IPv4-UNDERLAY-PEERS
   neighbor 172.30.255.5 remote-as 65101
   neighbor 172.30.255.5 description s1-leaf2_Ethernet2
   neighbor 172.30.255.9 peer group IPv4-UNDERLAY-PEERS
   neighbor 172.30.255.9 remote-as 65102
   neighbor 172.30.255.9 description s1-leaf3_Ethernet2
   neighbor 172.30.255.13 peer group IPv4-UNDERLAY-PEERS
   neighbor 172.30.255.13 remote-as 65102
   neighbor 172.30.255.13 description s1-leaf4_Ethernet2
   neighbor 192.0.255.3 peer group EVPN-OVERLAY-PEERS
   neighbor 192.0.255.3 remote-as 65101
   neighbor 192.0.255.3 description s1-leaf1
   neighbor 192.0.255.4 peer group EVPN-OVERLAY-PEERS
   neighbor 192.0.255.4 remote-as 65101
   neighbor 192.0.255.4 description s1-leaf2
   neighbor 192.0.255.5 peer group EVPN-OVERLAY-PEERS
   neighbor 192.0.255.5 remote-as 65102
   neighbor 192.0.255.5 description s1-leaf3
   neighbor 192.0.255.6 peer group EVPN-OVERLAY-PEERS
   neighbor 192.0.255.6 remote-as 65102
   neighbor 192.0.255.6 description s1-leaf4
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
Serial number: s1-spine1
Hardware MAC address: 001c.73c0.c610
System MAC address: 001c.73c0.c610

Software image version: 4.33.0F-39050855.4330F (engineering build)
Architecture: i686
Internal build version: 4.33.0F-39050855.4330F
Internal build ID: ff38b52c-4b4f-4a3f-b591-ef310b5ac8ca
Image format version: 1.0
Image optimization: None

Kernel version: 5.14.0-503.21.1.el9_5.x86_64

Uptime: 5 hours and 33 minutes
Total memory: 49062196 kB
Free memory: 3219156 kB
```
