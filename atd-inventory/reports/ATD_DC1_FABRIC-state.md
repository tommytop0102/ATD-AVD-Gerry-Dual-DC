# Validate State Report

**Table of Contents:**

- [Validate State Report](validate-state-report)
  - [Test Results Summary](#test-results-summary)
  - [Failed Test Results Summary](#failed-test-results-summary)
  - [All Test Results](#all-test-results)

## Test Results Summary

### Summary Totals

| Total Tests | Total Tests Passed | Total Tests Failed | Total Tests Skipped |
| ----------- | ------------------ | ------------------ | ------------------- |
| 240 | 214 | 2 | 24 |

### Summary Totals Device Under Test

| Device Under Test | Total Tests | Tests Passed | Tests Failed | Tests Skipped | Categories Failed | Categories Skipped |
| ------------------| ----------- | ------------ | ------------ | ------------- | ----------------- | ------------------ |
| s1-leaf1 | 46 | 42 | 0 | 4 | - | Hardware |
| s1-leaf2 | 46 | 42 | 0 | 4 | - | Hardware |
| s1-leaf3 | 47 | 42 | 1 | 4 | Interfaces | Hardware |
| s1-leaf4 | 47 | 42 | 1 | 4 | Interfaces | Hardware |
| s1-spine1 | 27 | 23 | 0 | 4 | - | Hardware |
| s1-spine2 | 27 | 23 | 0 | 4 | - | Hardware |

### Summary Totals Per Category

| Test Category | Total Tests | Tests Passed | Tests Failed | Tests Skipped |
| ------------- | ----------- | ------------ | ------------ | ------------- |
| BGP | 36 | 36 | 0 | 0 |
| Connectivity | 64 | 64 | 0 | 0 |
| Hardware | 24 | 0 | 0 | 24 |
| Interfaces | 68 | 66 | 2 | 0 |
| MLAG | 4 | 4 | 0 | 0 |
| Routing | 38 | 38 | 0 | 0 |
| System | 6 | 6 | 0 | 0 |

## Failed Test Results Summary

| ID | Device Under Test | Categories | Test | Description | Inputs | Result | Messages |
| -- | ----------------- | ---------- | ---- | ----------- | ------ | -------| -------- |
| 123 | s1-leaf3 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Port-Channel4 - s1-host2_PortChannel = 'up' | FAIL | The following interface(s) are not in the expected state: ['Port-Channel4 is down/lowerLayerDown'] |
| 170 | s1-leaf4 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Port-Channel4 - s1-host2_PortChannel = 'up' | FAIL | The following interface(s) are not in the expected state: ['Port-Channel4 is down/lowerLayerDown'] |

## All Test Results

| ID | Device Under Test | Categories | Test | Description | Inputs | Result | Messages |
| -- | ----------------- | ---------- | ---- | ----------- | ------ | -------| -------- |
| 1 | s1-leaf1 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP EVPN Peer: s1-spine1 (IP: 192.0.255.1) | PASS | - |
| 2 | s1-leaf1 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP EVPN Peer: s1-spine2 (IP: 192.0.255.2) | PASS | - |
| 3 | s1-leaf1 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP IPv4 Unicast Peer: s1-leaf2 (IP: 10.255.251.1) | PASS | - |
| 4 | s1-leaf1 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP IPv4 Unicast Peer: s1-spine1 (IP: 172.30.255.0) | PASS | - |
| 5 | s1-leaf1 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP IPv4 Unicast Peer: s1-spine2 (IP: 172.30.255.2) | PASS | - |
| 6 | s1-leaf1 | Connectivity | VerifyLLDPNeighbors | Verifies that the provided LLDP neighbors are connected properly. | Local: Ethernet1 - Remote: s1-leaf2 Ethernet1 | PASS | - |
| 7 | s1-leaf1 | Connectivity | VerifyLLDPNeighbors | Verifies that the provided LLDP neighbors are connected properly. | Local: Ethernet2 - Remote: s1-spine1 Ethernet2 | PASS | - |
| 8 | s1-leaf1 | Connectivity | VerifyLLDPNeighbors | Verifies that the provided LLDP neighbors are connected properly. | Local: Ethernet3 - Remote: s1-spine2 Ethernet2 | PASS | - |
| 9 | s1-leaf1 | Connectivity | VerifyLLDPNeighbors | Verifies that the provided LLDP neighbors are connected properly. | Local: Ethernet6 - Remote: s1-leaf2 Ethernet6 | PASS | - |
| 10 | s1-leaf1 | Connectivity | VerifyReachability | Test the network reachability to one or many destination IP(s). | Source: Loopback0 (IP: 192.0.255.3) - Destination: s1-leaf1 Loopback0 (IP: 192.0.255.3) | PASS | - |
| 11 | s1-leaf1 | Connectivity | VerifyReachability | Test the network reachability to one or many destination IP(s). | Source: Loopback0 (IP: 192.0.255.3) - Destination: s1-leaf2 Loopback0 (IP: 192.0.255.4) | PASS | - |
| 12 | s1-leaf1 | Connectivity | VerifyReachability | Test the network reachability to one or many destination IP(s). | Source: Loopback0 (IP: 192.0.255.3) - Destination: s1-leaf3 Loopback0 (IP: 192.0.255.5) | PASS | - |
| 13 | s1-leaf1 | Connectivity | VerifyReachability | Test the network reachability to one or many destination IP(s). | Source: Loopback0 (IP: 192.0.255.3) - Destination: s1-leaf4 Loopback0 (IP: 192.0.255.6) | PASS | - |
| 14 | s1-leaf1 | Connectivity | VerifyReachability | Test the network reachability to one or many destination IP(s). | Source: Loopback0 (IP: 192.0.255.3) - Destination: s1-spine1 Loopback0 (IP: 192.0.255.1) | PASS | - |
| 15 | s1-leaf1 | Connectivity | VerifyReachability | Test the network reachability to one or many destination IP(s). | Source: Loopback0 (IP: 192.0.255.3) - Destination: s1-spine2 Loopback0 (IP: 192.0.255.2) | PASS | - |
| 16 | s1-leaf1 | Connectivity | VerifyReachability | Test the network reachability to one or many destination IP(s). | Source: P2P Interface Ethernet2 (IP: 172.30.255.1) - Destination: s1-spine1 Ethernet2 (IP: 172.30.255.0) | PASS | - |
| 17 | s1-leaf1 | Connectivity | VerifyReachability | Test the network reachability to one or many destination IP(s). | Source: P2P Interface Ethernet3 (IP: 172.30.255.3) - Destination: s1-spine2 Ethernet2 (IP: 172.30.255.2) | PASS | - |
| 18 | s1-leaf1 | Hardware | VerifyEnvironmentCooling | Verifies the status of power supply fans and all fan trays. | Accepted States: 'ok' | SKIPPED | VerifyEnvironmentCooling test is not supported on cEOSLab. |
| 19 | s1-leaf1 | Hardware | VerifyEnvironmentPower | Verifies the power supplies status. | Accepted States: 'ok' | SKIPPED | VerifyEnvironmentPower test is not supported on cEOSLab. |
| 20 | s1-leaf1 | Hardware | VerifyTemperature | Verifies the device temperature. | - | SKIPPED | VerifyTemperature test is not supported on cEOSLab. |
| 21 | s1-leaf1 | Hardware | VerifyTransceiversManufacturers | Verifies if all transceivers come from approved manufacturers. | Accepted Manufacturers: 'Arista Networks', 'Arastra, Inc.', 'Not Present' | SKIPPED | VerifyTransceiversManufacturers test is not supported on cEOSLab. |
| 22 | s1-leaf1 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Ethernet1 - MLAG_PEER_s1-leaf2_Ethernet1 = 'up' | PASS | - |
| 23 | s1-leaf1 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Ethernet2 - P2P_LINK_TO_S1-SPINE1_Ethernet2 = 'up' | PASS | - |
| 24 | s1-leaf1 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Ethernet3 - P2P_LINK_TO_S1-SPINE2_Ethernet2 = 'up' | PASS | - |
| 25 | s1-leaf1 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Ethernet4 - teset etherent4 = 'up' | PASS | - |
| 26 | s1-leaf1 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Ethernet6 - MLAG_PEER_s1-leaf2_Ethernet6 = 'up' | PASS | - |
| 27 | s1-leaf1 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Loopback0 - EVPN_Overlay_Peering = 'up' | PASS | - |
| 28 | s1-leaf1 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Loopback1 - VTEP_VXLAN_Tunnel_Source = 'up' | PASS | - |
| 29 | s1-leaf1 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Loopback100 - Tenant_A_OP_Zone_VTEP_DIAGNOSTICS = 'up' | PASS | - |
| 30 | s1-leaf1 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Port-Channel1 - MLAG_PEER_s1-leaf2_Po1 = 'up' | PASS | - |
| 31 | s1-leaf1 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Vlan110 - Tenant_A_OP_Zone_1 = 'up' | PASS | - |
| 32 | s1-leaf1 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Vlan3009 - MLAG_PEER_L3_iBGP: vrf Tenant_A_OP_Zone = 'up' | PASS | - |
| 33 | s1-leaf1 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Vlan4093 - MLAG_PEER_L3_PEERING = 'up' | PASS | - |
| 34 | s1-leaf1 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Vlan4094 - MLAG_PEER = 'up' | PASS | - |
| 35 | s1-leaf1 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Vxlan1 = 'up' | PASS | - |
| 36 | s1-leaf1 | MLAG | VerifyMlagStatus | Verifies the health status of the MLAG configuration. | - | PASS | - |
| 37 | s1-leaf1 | Routing | VerifyRoutingProtocolModel | Verifies the configured routing protocol model. | Routing protocol model: multi-agent | PASS | - |
| 38 | s1-leaf1 | Routing | VerifyRoutingTableEntry | Verifies that the provided routes are present in the routing table of a specified VRF. | Route: 192.0.254.3 - Peer: s1-leaf1 | PASS | - |
| 39 | s1-leaf1 | Routing | VerifyRoutingTableEntry | Verifies that the provided routes are present in the routing table of a specified VRF. | Route: 192.0.254.5 - Peer: s1-leaf3 | PASS | - |
| 40 | s1-leaf1 | Routing | VerifyRoutingTableEntry | Verifies that the provided routes are present in the routing table of a specified VRF. | Route: 192.0.255.1 - Peer: s1-spine1 | PASS | - |
| 41 | s1-leaf1 | Routing | VerifyRoutingTableEntry | Verifies that the provided routes are present in the routing table of a specified VRF. | Route: 192.0.255.2 - Peer: s1-spine2 | PASS | - |
| 42 | s1-leaf1 | Routing | VerifyRoutingTableEntry | Verifies that the provided routes are present in the routing table of a specified VRF. | Route: 192.0.255.3 - Peer: s1-leaf1 | PASS | - |
| 43 | s1-leaf1 | Routing | VerifyRoutingTableEntry | Verifies that the provided routes are present in the routing table of a specified VRF. | Route: 192.0.255.4 - Peer: s1-leaf2 | PASS | - |
| 44 | s1-leaf1 | Routing | VerifyRoutingTableEntry | Verifies that the provided routes are present in the routing table of a specified VRF. | Route: 192.0.255.5 - Peer: s1-leaf3 | PASS | - |
| 45 | s1-leaf1 | Routing | VerifyRoutingTableEntry | Verifies that the provided routes are present in the routing table of a specified VRF. | Route: 192.0.255.6 - Peer: s1-leaf4 | PASS | - |
| 46 | s1-leaf1 | System | VerifyNTP | Verifies if NTP is synchronised. | - | PASS | - |
| 47 | s1-leaf2 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP EVPN Peer: s1-spine1 (IP: 192.0.255.1) | PASS | - |
| 48 | s1-leaf2 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP EVPN Peer: s1-spine2 (IP: 192.0.255.2) | PASS | - |
| 49 | s1-leaf2 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP IPv4 Unicast Peer: s1-leaf1 (IP: 10.255.251.0) | PASS | - |
| 50 | s1-leaf2 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP IPv4 Unicast Peer: s1-spine1 (IP: 172.30.255.4) | PASS | - |
| 51 | s1-leaf2 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP IPv4 Unicast Peer: s1-spine2 (IP: 172.30.255.6) | PASS | - |
| 52 | s1-leaf2 | Connectivity | VerifyLLDPNeighbors | Verifies that the provided LLDP neighbors are connected properly. | Local: Ethernet1 - Remote: s1-leaf1 Ethernet1 | PASS | - |
| 53 | s1-leaf2 | Connectivity | VerifyLLDPNeighbors | Verifies that the provided LLDP neighbors are connected properly. | Local: Ethernet2 - Remote: s1-spine1 Ethernet3 | PASS | - |
| 54 | s1-leaf2 | Connectivity | VerifyLLDPNeighbors | Verifies that the provided LLDP neighbors are connected properly. | Local: Ethernet3 - Remote: s1-spine2 Ethernet3 | PASS | - |
| 55 | s1-leaf2 | Connectivity | VerifyLLDPNeighbors | Verifies that the provided LLDP neighbors are connected properly. | Local: Ethernet6 - Remote: s1-leaf1 Ethernet6 | PASS | - |
| 56 | s1-leaf2 | Connectivity | VerifyReachability | Test the network reachability to one or many destination IP(s). | Source: Loopback0 (IP: 192.0.255.4) - Destination: s1-leaf1 Loopback0 (IP: 192.0.255.3) | PASS | - |
| 57 | s1-leaf2 | Connectivity | VerifyReachability | Test the network reachability to one or many destination IP(s). | Source: Loopback0 (IP: 192.0.255.4) - Destination: s1-leaf2 Loopback0 (IP: 192.0.255.4) | PASS | - |
| 58 | s1-leaf2 | Connectivity | VerifyReachability | Test the network reachability to one or many destination IP(s). | Source: Loopback0 (IP: 192.0.255.4) - Destination: s1-leaf3 Loopback0 (IP: 192.0.255.5) | PASS | - |
| 59 | s1-leaf2 | Connectivity | VerifyReachability | Test the network reachability to one or many destination IP(s). | Source: Loopback0 (IP: 192.0.255.4) - Destination: s1-leaf4 Loopback0 (IP: 192.0.255.6) | PASS | - |
| 60 | s1-leaf2 | Connectivity | VerifyReachability | Test the network reachability to one or many destination IP(s). | Source: Loopback0 (IP: 192.0.255.4) - Destination: s1-spine1 Loopback0 (IP: 192.0.255.1) | PASS | - |
| 61 | s1-leaf2 | Connectivity | VerifyReachability | Test the network reachability to one or many destination IP(s). | Source: Loopback0 (IP: 192.0.255.4) - Destination: s1-spine2 Loopback0 (IP: 192.0.255.2) | PASS | - |
| 62 | s1-leaf2 | Connectivity | VerifyReachability | Test the network reachability to one or many destination IP(s). | Source: P2P Interface Ethernet2 (IP: 172.30.255.5) - Destination: s1-spine1 Ethernet3 (IP: 172.30.255.4) | PASS | - |
| 63 | s1-leaf2 | Connectivity | VerifyReachability | Test the network reachability to one or many destination IP(s). | Source: P2P Interface Ethernet3 (IP: 172.30.255.7) - Destination: s1-spine2 Ethernet3 (IP: 172.30.255.6) | PASS | - |
| 64 | s1-leaf2 | Hardware | VerifyEnvironmentCooling | Verifies the status of power supply fans and all fan trays. | Accepted States: 'ok' | SKIPPED | VerifyEnvironmentCooling test is not supported on cEOSLab. |
| 65 | s1-leaf2 | Hardware | VerifyEnvironmentPower | Verifies the power supplies status. | Accepted States: 'ok' | SKIPPED | VerifyEnvironmentPower test is not supported on cEOSLab. |
| 66 | s1-leaf2 | Hardware | VerifyTemperature | Verifies the device temperature. | - | SKIPPED | VerifyTemperature test is not supported on cEOSLab. |
| 67 | s1-leaf2 | Hardware | VerifyTransceiversManufacturers | Verifies if all transceivers come from approved manufacturers. | Accepted Manufacturers: 'Arista Networks', 'Arastra, Inc.', 'Not Present' | SKIPPED | VerifyTransceiversManufacturers test is not supported on cEOSLab. |
| 68 | s1-leaf2 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Ethernet1 - MLAG_PEER_s1-leaf1_Ethernet1 = 'up' | PASS | - |
| 69 | s1-leaf2 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Ethernet2 - P2P_LINK_TO_S1-SPINE1_Ethernet3 = 'up' | PASS | - |
| 70 | s1-leaf2 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Ethernet3 - P2P_LINK_TO_S1-SPINE2_Ethernet3 = 'up' | PASS | - |
| 71 | s1-leaf2 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Ethernet4 - Routed_Interface_4 int_routed_host = 'up' | PASS | - |
| 72 | s1-leaf2 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Ethernet6 - MLAG_PEER_s1-leaf1_Ethernet6 = 'up' | PASS | - |
| 73 | s1-leaf2 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Loopback0 - EVPN_Overlay_Peering = 'up' | PASS | - |
| 74 | s1-leaf2 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Loopback1 - VTEP_VXLAN_Tunnel_Source = 'up' | PASS | - |
| 75 | s1-leaf2 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Loopback100 - Tenant_A_OP_Zone_VTEP_DIAGNOSTICS = 'up' | PASS | - |
| 76 | s1-leaf2 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Port-Channel1 - MLAG_PEER_s1-leaf1_Po1 = 'up' | PASS | - |
| 77 | s1-leaf2 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Vlan110 - Tenant_A_OP_Zone_1 = 'up' | PASS | - |
| 78 | s1-leaf2 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Vlan3009 - MLAG_PEER_L3_iBGP: vrf Tenant_A_OP_Zone = 'up' | PASS | - |
| 79 | s1-leaf2 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Vlan4093 - MLAG_PEER_L3_PEERING = 'up' | PASS | - |
| 80 | s1-leaf2 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Vlan4094 - MLAG_PEER = 'up' | PASS | - |
| 81 | s1-leaf2 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Vxlan1 = 'up' | PASS | - |
| 82 | s1-leaf2 | MLAG | VerifyMlagStatus | Verifies the health status of the MLAG configuration. | - | PASS | - |
| 83 | s1-leaf2 | Routing | VerifyRoutingProtocolModel | Verifies the configured routing protocol model. | Routing protocol model: multi-agent | PASS | - |
| 84 | s1-leaf2 | Routing | VerifyRoutingTableEntry | Verifies that the provided routes are present in the routing table of a specified VRF. | Route: 192.0.254.3 - Peer: s1-leaf1 | PASS | - |
| 85 | s1-leaf2 | Routing | VerifyRoutingTableEntry | Verifies that the provided routes are present in the routing table of a specified VRF. | Route: 192.0.254.5 - Peer: s1-leaf3 | PASS | - |
| 86 | s1-leaf2 | Routing | VerifyRoutingTableEntry | Verifies that the provided routes are present in the routing table of a specified VRF. | Route: 192.0.255.1 - Peer: s1-spine1 | PASS | - |
| 87 | s1-leaf2 | Routing | VerifyRoutingTableEntry | Verifies that the provided routes are present in the routing table of a specified VRF. | Route: 192.0.255.2 - Peer: s1-spine2 | PASS | - |
| 88 | s1-leaf2 | Routing | VerifyRoutingTableEntry | Verifies that the provided routes are present in the routing table of a specified VRF. | Route: 192.0.255.3 - Peer: s1-leaf1 | PASS | - |
| 89 | s1-leaf2 | Routing | VerifyRoutingTableEntry | Verifies that the provided routes are present in the routing table of a specified VRF. | Route: 192.0.255.4 - Peer: s1-leaf2 | PASS | - |
| 90 | s1-leaf2 | Routing | VerifyRoutingTableEntry | Verifies that the provided routes are present in the routing table of a specified VRF. | Route: 192.0.255.5 - Peer: s1-leaf3 | PASS | - |
| 91 | s1-leaf2 | Routing | VerifyRoutingTableEntry | Verifies that the provided routes are present in the routing table of a specified VRF. | Route: 192.0.255.6 - Peer: s1-leaf4 | PASS | - |
| 92 | s1-leaf2 | System | VerifyNTP | Verifies if NTP is synchronised. | - | PASS | - |
| 93 | s1-leaf3 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP EVPN Peer: s1-spine1 (IP: 192.0.255.1) | PASS | - |
| 94 | s1-leaf3 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP EVPN Peer: s1-spine2 (IP: 192.0.255.2) | PASS | - |
| 95 | s1-leaf3 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP IPv4 Unicast Peer: s1-leaf4 (IP: 10.255.251.5) | PASS | - |
| 96 | s1-leaf3 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP IPv4 Unicast Peer: s1-spine1 (IP: 172.30.255.8) | PASS | - |
| 97 | s1-leaf3 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP IPv4 Unicast Peer: s1-spine2 (IP: 172.30.255.10) | PASS | - |
| 98 | s1-leaf3 | Connectivity | VerifyLLDPNeighbors | Verifies that the provided LLDP neighbors are connected properly. | Local: Ethernet1 - Remote: s1-leaf4 Ethernet1 | PASS | - |
| 99 | s1-leaf3 | Connectivity | VerifyLLDPNeighbors | Verifies that the provided LLDP neighbors are connected properly. | Local: Ethernet2 - Remote: s1-spine1 Ethernet4 | PASS | - |
| 100 | s1-leaf3 | Connectivity | VerifyLLDPNeighbors | Verifies that the provided LLDP neighbors are connected properly. | Local: Ethernet3 - Remote: s1-spine2 Ethernet4 | PASS | - |
| 101 | s1-leaf3 | Connectivity | VerifyLLDPNeighbors | Verifies that the provided LLDP neighbors are connected properly. | Local: Ethernet6 - Remote: s1-leaf4 Ethernet6 | PASS | - |
| 102 | s1-leaf3 | Connectivity | VerifyReachability | Test the network reachability to one or many destination IP(s). | Source: Loopback0 (IP: 192.0.255.5) - Destination: s1-leaf1 Loopback0 (IP: 192.0.255.3) | PASS | - |
| 103 | s1-leaf3 | Connectivity | VerifyReachability | Test the network reachability to one or many destination IP(s). | Source: Loopback0 (IP: 192.0.255.5) - Destination: s1-leaf2 Loopback0 (IP: 192.0.255.4) | PASS | - |
| 104 | s1-leaf3 | Connectivity | VerifyReachability | Test the network reachability to one or many destination IP(s). | Source: Loopback0 (IP: 192.0.255.5) - Destination: s1-leaf3 Loopback0 (IP: 192.0.255.5) | PASS | - |
| 105 | s1-leaf3 | Connectivity | VerifyReachability | Test the network reachability to one or many destination IP(s). | Source: Loopback0 (IP: 192.0.255.5) - Destination: s1-leaf4 Loopback0 (IP: 192.0.255.6) | PASS | - |
| 106 | s1-leaf3 | Connectivity | VerifyReachability | Test the network reachability to one or many destination IP(s). | Source: Loopback0 (IP: 192.0.255.5) - Destination: s1-spine1 Loopback0 (IP: 192.0.255.1) | PASS | - |
| 107 | s1-leaf3 | Connectivity | VerifyReachability | Test the network reachability to one or many destination IP(s). | Source: Loopback0 (IP: 192.0.255.5) - Destination: s1-spine2 Loopback0 (IP: 192.0.255.2) | PASS | - |
| 108 | s1-leaf3 | Connectivity | VerifyReachability | Test the network reachability to one or many destination IP(s). | Source: P2P Interface Ethernet2 (IP: 172.30.255.9) - Destination: s1-spine1 Ethernet4 (IP: 172.30.255.8) | PASS | - |
| 109 | s1-leaf3 | Connectivity | VerifyReachability | Test the network reachability to one or many destination IP(s). | Source: P2P Interface Ethernet3 (IP: 172.30.255.11) - Destination: s1-spine2 Ethernet4 (IP: 172.30.255.10) | PASS | - |
| 110 | s1-leaf3 | Hardware | VerifyEnvironmentCooling | Verifies the status of power supply fans and all fan trays. | Accepted States: 'ok' | SKIPPED | VerifyEnvironmentCooling test is not supported on cEOSLab. |
| 111 | s1-leaf3 | Hardware | VerifyEnvironmentPower | Verifies the power supplies status. | Accepted States: 'ok' | SKIPPED | VerifyEnvironmentPower test is not supported on cEOSLab. |
| 112 | s1-leaf3 | Hardware | VerifyTemperature | Verifies the device temperature. | - | SKIPPED | VerifyTemperature test is not supported on cEOSLab. |
| 113 | s1-leaf3 | Hardware | VerifyTransceiversManufacturers | Verifies if all transceivers come from approved manufacturers. | Accepted Manufacturers: 'Arista Networks', 'Arastra, Inc.', 'Not Present' | SKIPPED | VerifyTransceiversManufacturers test is not supported on cEOSLab. |
| 114 | s1-leaf3 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Ethernet1 - MLAG_PEER_s1-leaf4_Ethernet1 = 'up' | PASS | - |
| 115 | s1-leaf3 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Ethernet2 - P2P_LINK_TO_S1-SPINE1_Ethernet4 = 'up' | PASS | - |
| 116 | s1-leaf3 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Ethernet3 - P2P_LINK_TO_S1-SPINE2_Ethernet4 = 'up' | PASS | - |
| 117 | s1-leaf3 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Ethernet4 - s1-host2_Eth1 = 'up' | PASS | - |
| 118 | s1-leaf3 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Ethernet6 - MLAG_PEER_s1-leaf4_Ethernet6 = 'up' | PASS | - |
| 119 | s1-leaf3 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Loopback0 - EVPN_Overlay_Peering = 'up' | PASS | - |
| 120 | s1-leaf3 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Loopback1 - VTEP_VXLAN_Tunnel_Source = 'up' | PASS | - |
| 121 | s1-leaf3 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Loopback100 - Tenant_A_OP_Zone_VTEP_DIAGNOSTICS = 'up' | PASS | - |
| 122 | s1-leaf3 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Port-Channel1 - MLAG_PEER_s1-leaf4_Po1 = 'up' | PASS | - |
| 123 | s1-leaf3 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Port-Channel4 - s1-host2_PortChannel = 'up' | FAIL | The following interface(s) are not in the expected state: ['Port-Channel4 is down/lowerLayerDown'] |
| 124 | s1-leaf3 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Vlan110 - Tenant_A_OP_Zone_1 = 'up' | PASS | - |
| 125 | s1-leaf3 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Vlan3009 - MLAG_PEER_L3_iBGP: vrf Tenant_A_OP_Zone = 'up' | PASS | - |
| 126 | s1-leaf3 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Vlan4093 - MLAG_PEER_L3_PEERING = 'up' | PASS | - |
| 127 | s1-leaf3 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Vlan4094 - MLAG_PEER = 'up' | PASS | - |
| 128 | s1-leaf3 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Vxlan1 = 'up' | PASS | - |
| 129 | s1-leaf3 | MLAG | VerifyMlagStatus | Verifies the health status of the MLAG configuration. | - | PASS | - |
| 130 | s1-leaf3 | Routing | VerifyRoutingProtocolModel | Verifies the configured routing protocol model. | Routing protocol model: multi-agent | PASS | - |
| 131 | s1-leaf3 | Routing | VerifyRoutingTableEntry | Verifies that the provided routes are present in the routing table of a specified VRF. | Route: 192.0.254.3 - Peer: s1-leaf1 | PASS | - |
| 132 | s1-leaf3 | Routing | VerifyRoutingTableEntry | Verifies that the provided routes are present in the routing table of a specified VRF. | Route: 192.0.254.5 - Peer: s1-leaf3 | PASS | - |
| 133 | s1-leaf3 | Routing | VerifyRoutingTableEntry | Verifies that the provided routes are present in the routing table of a specified VRF. | Route: 192.0.255.1 - Peer: s1-spine1 | PASS | - |
| 134 | s1-leaf3 | Routing | VerifyRoutingTableEntry | Verifies that the provided routes are present in the routing table of a specified VRF. | Route: 192.0.255.2 - Peer: s1-spine2 | PASS | - |
| 135 | s1-leaf3 | Routing | VerifyRoutingTableEntry | Verifies that the provided routes are present in the routing table of a specified VRF. | Route: 192.0.255.3 - Peer: s1-leaf1 | PASS | - |
| 136 | s1-leaf3 | Routing | VerifyRoutingTableEntry | Verifies that the provided routes are present in the routing table of a specified VRF. | Route: 192.0.255.4 - Peer: s1-leaf2 | PASS | - |
| 137 | s1-leaf3 | Routing | VerifyRoutingTableEntry | Verifies that the provided routes are present in the routing table of a specified VRF. | Route: 192.0.255.5 - Peer: s1-leaf3 | PASS | - |
| 138 | s1-leaf3 | Routing | VerifyRoutingTableEntry | Verifies that the provided routes are present in the routing table of a specified VRF. | Route: 192.0.255.6 - Peer: s1-leaf4 | PASS | - |
| 139 | s1-leaf3 | System | VerifyNTP | Verifies if NTP is synchronised. | - | PASS | - |
| 140 | s1-leaf4 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP EVPN Peer: s1-spine1 (IP: 192.0.255.1) | PASS | - |
| 141 | s1-leaf4 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP EVPN Peer: s1-spine2 (IP: 192.0.255.2) | PASS | - |
| 142 | s1-leaf4 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP IPv4 Unicast Peer: s1-leaf3 (IP: 10.255.251.4) | PASS | - |
| 143 | s1-leaf4 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP IPv4 Unicast Peer: s1-spine1 (IP: 172.30.255.12) | PASS | - |
| 144 | s1-leaf4 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP IPv4 Unicast Peer: s1-spine2 (IP: 172.30.255.14) | PASS | - |
| 145 | s1-leaf4 | Connectivity | VerifyLLDPNeighbors | Verifies that the provided LLDP neighbors are connected properly. | Local: Ethernet1 - Remote: s1-leaf3 Ethernet1 | PASS | - |
| 146 | s1-leaf4 | Connectivity | VerifyLLDPNeighbors | Verifies that the provided LLDP neighbors are connected properly. | Local: Ethernet2 - Remote: s1-spine1 Ethernet5 | PASS | - |
| 147 | s1-leaf4 | Connectivity | VerifyLLDPNeighbors | Verifies that the provided LLDP neighbors are connected properly. | Local: Ethernet3 - Remote: s1-spine2 Ethernet5 | PASS | - |
| 148 | s1-leaf4 | Connectivity | VerifyLLDPNeighbors | Verifies that the provided LLDP neighbors are connected properly. | Local: Ethernet6 - Remote: s1-leaf3 Ethernet6 | PASS | - |
| 149 | s1-leaf4 | Connectivity | VerifyReachability | Test the network reachability to one or many destination IP(s). | Source: Loopback0 (IP: 192.0.255.6) - Destination: s1-leaf1 Loopback0 (IP: 192.0.255.3) | PASS | - |
| 150 | s1-leaf4 | Connectivity | VerifyReachability | Test the network reachability to one or many destination IP(s). | Source: Loopback0 (IP: 192.0.255.6) - Destination: s1-leaf2 Loopback0 (IP: 192.0.255.4) | PASS | - |
| 151 | s1-leaf4 | Connectivity | VerifyReachability | Test the network reachability to one or many destination IP(s). | Source: Loopback0 (IP: 192.0.255.6) - Destination: s1-leaf3 Loopback0 (IP: 192.0.255.5) | PASS | - |
| 152 | s1-leaf4 | Connectivity | VerifyReachability | Test the network reachability to one or many destination IP(s). | Source: Loopback0 (IP: 192.0.255.6) - Destination: s1-leaf4 Loopback0 (IP: 192.0.255.6) | PASS | - |
| 153 | s1-leaf4 | Connectivity | VerifyReachability | Test the network reachability to one or many destination IP(s). | Source: Loopback0 (IP: 192.0.255.6) - Destination: s1-spine1 Loopback0 (IP: 192.0.255.1) | PASS | - |
| 154 | s1-leaf4 | Connectivity | VerifyReachability | Test the network reachability to one or many destination IP(s). | Source: Loopback0 (IP: 192.0.255.6) - Destination: s1-spine2 Loopback0 (IP: 192.0.255.2) | PASS | - |
| 155 | s1-leaf4 | Connectivity | VerifyReachability | Test the network reachability to one or many destination IP(s). | Source: P2P Interface Ethernet2 (IP: 172.30.255.13) - Destination: s1-spine1 Ethernet5 (IP: 172.30.255.12) | PASS | - |
| 156 | s1-leaf4 | Connectivity | VerifyReachability | Test the network reachability to one or many destination IP(s). | Source: P2P Interface Ethernet3 (IP: 172.30.255.15) - Destination: s1-spine2 Ethernet5 (IP: 172.30.255.14) | PASS | - |
| 157 | s1-leaf4 | Hardware | VerifyEnvironmentCooling | Verifies the status of power supply fans and all fan trays. | Accepted States: 'ok' | SKIPPED | VerifyEnvironmentCooling test is not supported on cEOSLab. |
| 158 | s1-leaf4 | Hardware | VerifyEnvironmentPower | Verifies the power supplies status. | Accepted States: 'ok' | SKIPPED | VerifyEnvironmentPower test is not supported on cEOSLab. |
| 159 | s1-leaf4 | Hardware | VerifyTemperature | Verifies the device temperature. | - | SKIPPED | VerifyTemperature test is not supported on cEOSLab. |
| 160 | s1-leaf4 | Hardware | VerifyTransceiversManufacturers | Verifies if all transceivers come from approved manufacturers. | Accepted Manufacturers: 'Arista Networks', 'Arastra, Inc.', 'Not Present' | SKIPPED | VerifyTransceiversManufacturers test is not supported on cEOSLab. |
| 161 | s1-leaf4 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Ethernet1 - MLAG_PEER_s1-leaf3_Ethernet1 = 'up' | PASS | - |
| 162 | s1-leaf4 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Ethernet2 - P2P_LINK_TO_S1-SPINE1_Ethernet5 = 'up' | PASS | - |
| 163 | s1-leaf4 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Ethernet3 - P2P_LINK_TO_S1-SPINE2_Ethernet5 = 'up' | PASS | - |
| 164 | s1-leaf4 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Ethernet4 - s1-host2_Eth2 = 'up' | PASS | - |
| 165 | s1-leaf4 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Ethernet6 - MLAG_PEER_s1-leaf3_Ethernet6 = 'up' | PASS | - |
| 166 | s1-leaf4 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Loopback0 - EVPN_Overlay_Peering = 'up' | PASS | - |
| 167 | s1-leaf4 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Loopback1 - VTEP_VXLAN_Tunnel_Source = 'up' | PASS | - |
| 168 | s1-leaf4 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Loopback100 - Tenant_A_OP_Zone_VTEP_DIAGNOSTICS = 'up' | PASS | - |
| 169 | s1-leaf4 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Port-Channel1 - MLAG_PEER_s1-leaf3_Po1 = 'up' | PASS | - |
| 170 | s1-leaf4 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Port-Channel4 - s1-host2_PortChannel = 'up' | FAIL | The following interface(s) are not in the expected state: ['Port-Channel4 is down/lowerLayerDown'] |
| 171 | s1-leaf4 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Vlan110 - Tenant_A_OP_Zone_1 = 'up' | PASS | - |
| 172 | s1-leaf4 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Vlan3009 - MLAG_PEER_L3_iBGP: vrf Tenant_A_OP_Zone = 'up' | PASS | - |
| 173 | s1-leaf4 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Vlan4093 - MLAG_PEER_L3_PEERING = 'up' | PASS | - |
| 174 | s1-leaf4 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Vlan4094 - MLAG_PEER = 'up' | PASS | - |
| 175 | s1-leaf4 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Vxlan1 = 'up' | PASS | - |
| 176 | s1-leaf4 | MLAG | VerifyMlagStatus | Verifies the health status of the MLAG configuration. | - | PASS | - |
| 177 | s1-leaf4 | Routing | VerifyRoutingProtocolModel | Verifies the configured routing protocol model. | Routing protocol model: multi-agent | PASS | - |
| 178 | s1-leaf4 | Routing | VerifyRoutingTableEntry | Verifies that the provided routes are present in the routing table of a specified VRF. | Route: 192.0.254.3 - Peer: s1-leaf1 | PASS | - |
| 179 | s1-leaf4 | Routing | VerifyRoutingTableEntry | Verifies that the provided routes are present in the routing table of a specified VRF. | Route: 192.0.254.5 - Peer: s1-leaf3 | PASS | - |
| 180 | s1-leaf4 | Routing | VerifyRoutingTableEntry | Verifies that the provided routes are present in the routing table of a specified VRF. | Route: 192.0.255.1 - Peer: s1-spine1 | PASS | - |
| 181 | s1-leaf4 | Routing | VerifyRoutingTableEntry | Verifies that the provided routes are present in the routing table of a specified VRF. | Route: 192.0.255.2 - Peer: s1-spine2 | PASS | - |
| 182 | s1-leaf4 | Routing | VerifyRoutingTableEntry | Verifies that the provided routes are present in the routing table of a specified VRF. | Route: 192.0.255.3 - Peer: s1-leaf1 | PASS | - |
| 183 | s1-leaf4 | Routing | VerifyRoutingTableEntry | Verifies that the provided routes are present in the routing table of a specified VRF. | Route: 192.0.255.4 - Peer: s1-leaf2 | PASS | - |
| 184 | s1-leaf4 | Routing | VerifyRoutingTableEntry | Verifies that the provided routes are present in the routing table of a specified VRF. | Route: 192.0.255.5 - Peer: s1-leaf3 | PASS | - |
| 185 | s1-leaf4 | Routing | VerifyRoutingTableEntry | Verifies that the provided routes are present in the routing table of a specified VRF. | Route: 192.0.255.6 - Peer: s1-leaf4 | PASS | - |
| 186 | s1-leaf4 | System | VerifyNTP | Verifies if NTP is synchronised. | - | PASS | - |
| 187 | s1-spine1 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP EVPN Peer: s1-leaf1 (IP: 192.0.255.3) | PASS | - |
| 188 | s1-spine1 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP EVPN Peer: s1-leaf2 (IP: 192.0.255.4) | PASS | - |
| 189 | s1-spine1 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP EVPN Peer: s1-leaf3 (IP: 192.0.255.5) | PASS | - |
| 190 | s1-spine1 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP EVPN Peer: s1-leaf4 (IP: 192.0.255.6) | PASS | - |
| 191 | s1-spine1 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP IPv4 Unicast Peer: s1-leaf1 (IP: 172.30.255.1) | PASS | - |
| 192 | s1-spine1 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP IPv4 Unicast Peer: s1-leaf2 (IP: 172.30.255.5) | PASS | - |
| 193 | s1-spine1 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP IPv4 Unicast Peer: s1-leaf3 (IP: 172.30.255.9) | PASS | - |
| 194 | s1-spine1 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP IPv4 Unicast Peer: s1-leaf4 (IP: 172.30.255.13) | PASS | - |
| 195 | s1-spine1 | Connectivity | VerifyLLDPNeighbors | Verifies that the provided LLDP neighbors are connected properly. | Local: Ethernet2 - Remote: s1-leaf1 Ethernet2 | PASS | - |
| 196 | s1-spine1 | Connectivity | VerifyLLDPNeighbors | Verifies that the provided LLDP neighbors are connected properly. | Local: Ethernet3 - Remote: s1-leaf2 Ethernet2 | PASS | - |
| 197 | s1-spine1 | Connectivity | VerifyLLDPNeighbors | Verifies that the provided LLDP neighbors are connected properly. | Local: Ethernet4 - Remote: s1-leaf3 Ethernet2 | PASS | - |
| 198 | s1-spine1 | Connectivity | VerifyLLDPNeighbors | Verifies that the provided LLDP neighbors are connected properly. | Local: Ethernet5 - Remote: s1-leaf4 Ethernet2 | PASS | - |
| 199 | s1-spine1 | Connectivity | VerifyReachability | Test the network reachability to one or many destination IP(s). | Source: P2P Interface Ethernet2 (IP: 172.30.255.0) - Destination: s1-leaf1 Ethernet2 (IP: 172.30.255.1) | PASS | - |
| 200 | s1-spine1 | Connectivity | VerifyReachability | Test the network reachability to one or many destination IP(s). | Source: P2P Interface Ethernet3 (IP: 172.30.255.4) - Destination: s1-leaf2 Ethernet2 (IP: 172.30.255.5) | PASS | - |
| 201 | s1-spine1 | Connectivity | VerifyReachability | Test the network reachability to one or many destination IP(s). | Source: P2P Interface Ethernet4 (IP: 172.30.255.8) - Destination: s1-leaf3 Ethernet2 (IP: 172.30.255.9) | PASS | - |
| 202 | s1-spine1 | Connectivity | VerifyReachability | Test the network reachability to one or many destination IP(s). | Source: P2P Interface Ethernet5 (IP: 172.30.255.12) - Destination: s1-leaf4 Ethernet2 (IP: 172.30.255.13) | PASS | - |
| 203 | s1-spine1 | Hardware | VerifyEnvironmentCooling | Verifies the status of power supply fans and all fan trays. | Accepted States: 'ok' | SKIPPED | VerifyEnvironmentCooling test is not supported on cEOSLab. |
| 204 | s1-spine1 | Hardware | VerifyEnvironmentPower | Verifies the power supplies status. | Accepted States: 'ok' | SKIPPED | VerifyEnvironmentPower test is not supported on cEOSLab. |
| 205 | s1-spine1 | Hardware | VerifyTemperature | Verifies the device temperature. | - | SKIPPED | VerifyTemperature test is not supported on cEOSLab. |
| 206 | s1-spine1 | Hardware | VerifyTransceiversManufacturers | Verifies if all transceivers come from approved manufacturers. | Accepted Manufacturers: 'Arista Networks', 'Arastra, Inc.', 'Not Present' | SKIPPED | VerifyTransceiversManufacturers test is not supported on cEOSLab. |
| 207 | s1-spine1 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Ethernet2 - P2P_LINK_TO_S1-LEAF1_Ethernet2 = 'up' | PASS | - |
| 208 | s1-spine1 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Ethernet3 - P2P_LINK_TO_S1-LEAF2_Ethernet2 = 'up' | PASS | - |
| 209 | s1-spine1 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Ethernet4 - P2P_LINK_TO_S1-LEAF3_Ethernet2 = 'up' | PASS | - |
| 210 | s1-spine1 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Ethernet5 - P2P_LINK_TO_S1-LEAF4_Ethernet2 = 'up' | PASS | - |
| 211 | s1-spine1 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Loopback0 - EVPN_Overlay_Peering = 'up' | PASS | - |
| 212 | s1-spine1 | Routing | VerifyRoutingProtocolModel | Verifies the configured routing protocol model. | Routing protocol model: multi-agent | PASS | - |
| 213 | s1-spine1 | System | VerifyNTP | Verifies if NTP is synchronised. | - | PASS | - |
| 214 | s1-spine2 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP EVPN Peer: s1-leaf1 (IP: 192.0.255.3) | PASS | - |
| 215 | s1-spine2 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP EVPN Peer: s1-leaf2 (IP: 192.0.255.4) | PASS | - |
| 216 | s1-spine2 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP EVPN Peer: s1-leaf3 (IP: 192.0.255.5) | PASS | - |
| 217 | s1-spine2 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP EVPN Peer: s1-leaf4 (IP: 192.0.255.6) | PASS | - |
| 218 | s1-spine2 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP IPv4 Unicast Peer: s1-leaf1 (IP: 172.30.255.3) | PASS | - |
| 219 | s1-spine2 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP IPv4 Unicast Peer: s1-leaf2 (IP: 172.30.255.7) | PASS | - |
| 220 | s1-spine2 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP IPv4 Unicast Peer: s1-leaf3 (IP: 172.30.255.11) | PASS | - |
| 221 | s1-spine2 | BGP | VerifyBGPSpecificPeers | Verifies the health of specific BGP peer(s). | BGP IPv4 Unicast Peer: s1-leaf4 (IP: 172.30.255.15) | PASS | - |
| 222 | s1-spine2 | Connectivity | VerifyLLDPNeighbors | Verifies that the provided LLDP neighbors are connected properly. | Local: Ethernet2 - Remote: s1-leaf1 Ethernet3 | PASS | - |
| 223 | s1-spine2 | Connectivity | VerifyLLDPNeighbors | Verifies that the provided LLDP neighbors are connected properly. | Local: Ethernet3 - Remote: s1-leaf2 Ethernet3 | PASS | - |
| 224 | s1-spine2 | Connectivity | VerifyLLDPNeighbors | Verifies that the provided LLDP neighbors are connected properly. | Local: Ethernet4 - Remote: s1-leaf3 Ethernet3 | PASS | - |
| 225 | s1-spine2 | Connectivity | VerifyLLDPNeighbors | Verifies that the provided LLDP neighbors are connected properly. | Local: Ethernet5 - Remote: s1-leaf4 Ethernet3 | PASS | - |
| 226 | s1-spine2 | Connectivity | VerifyReachability | Test the network reachability to one or many destination IP(s). | Source: P2P Interface Ethernet2 (IP: 172.30.255.2) - Destination: s1-leaf1 Ethernet3 (IP: 172.30.255.3) | PASS | - |
| 227 | s1-spine2 | Connectivity | VerifyReachability | Test the network reachability to one or many destination IP(s). | Source: P2P Interface Ethernet3 (IP: 172.30.255.6) - Destination: s1-leaf2 Ethernet3 (IP: 172.30.255.7) | PASS | - |
| 228 | s1-spine2 | Connectivity | VerifyReachability | Test the network reachability to one or many destination IP(s). | Source: P2P Interface Ethernet4 (IP: 172.30.255.10) - Destination: s1-leaf3 Ethernet3 (IP: 172.30.255.11) | PASS | - |
| 229 | s1-spine2 | Connectivity | VerifyReachability | Test the network reachability to one or many destination IP(s). | Source: P2P Interface Ethernet5 (IP: 172.30.255.14) - Destination: s1-leaf4 Ethernet3 (IP: 172.30.255.15) | PASS | - |
| 230 | s1-spine2 | Hardware | VerifyEnvironmentCooling | Verifies the status of power supply fans and all fan trays. | Accepted States: 'ok' | SKIPPED | VerifyEnvironmentCooling test is not supported on cEOSLab. |
| 231 | s1-spine2 | Hardware | VerifyEnvironmentPower | Verifies the power supplies status. | Accepted States: 'ok' | SKIPPED | VerifyEnvironmentPower test is not supported on cEOSLab. |
| 232 | s1-spine2 | Hardware | VerifyTemperature | Verifies the device temperature. | - | SKIPPED | VerifyTemperature test is not supported on cEOSLab. |
| 233 | s1-spine2 | Hardware | VerifyTransceiversManufacturers | Verifies if all transceivers come from approved manufacturers. | Accepted Manufacturers: 'Arista Networks', 'Arastra, Inc.', 'Not Present' | SKIPPED | VerifyTransceiversManufacturers test is not supported on cEOSLab. |
| 234 | s1-spine2 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Ethernet2 - P2P_LINK_TO_S1-LEAF1_Ethernet3 = 'up' | PASS | - |
| 235 | s1-spine2 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Ethernet3 - P2P_LINK_TO_S1-LEAF2_Ethernet3 = 'up' | PASS | - |
| 236 | s1-spine2 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Ethernet4 - P2P_LINK_TO_S1-LEAF3_Ethernet3 = 'up' | PASS | - |
| 237 | s1-spine2 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Ethernet5 - P2P_LINK_TO_S1-LEAF4_Ethernet3 = 'up' | PASS | - |
| 238 | s1-spine2 | Interfaces | VerifyInterfacesStatus | Verifies the status of the provided interfaces. | Interface Loopback0 - EVPN_Overlay_Peering = 'up' | PASS | - |
| 239 | s1-spine2 | Routing | VerifyRoutingProtocolModel | Verifies the configured routing protocol model. | Routing protocol model: multi-agent | PASS | - |
| 240 | s1-spine2 | System | VerifyNTP | Verifies if NTP is synchronised. | - | PASS | - |
