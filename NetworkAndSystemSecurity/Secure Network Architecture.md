##Secure Segmentation Notes 🔐
# Why Subnetting Is Not Enough

Subnets separate networks at Layer 3 using IP addresses.

Subnetting improves routing and organization but does not automatically provide security.

If routes exist, devices can still communicate across subnets.

Infected or unmanaged devices, such as in BYOD (Bring Your Own Device) environments, can move through the network and reach sensitive systems.

# Why VLANs Are Used

VLANs (Virtual LANs) segment a network at Layer 2.

VLANs separate devices into different logical groups on the same switch infrastructure.

This helps reduce unnecessary communication between devices and improves control of network traffic.

# VLAN Tagging

VLANs use 802.1Q (Dot1Q) tagging.

A tag is added to an Ethernet frame to show which VLAN the traffic belongs to.

802.1Q is a standard, so different vendors can understand the same VLAN tags.

# Basic Open vSwitch VLAN Commands
Show Switch Configuration
ovs-vsctl show
Assign a VLAN Tag to a Port
ovs-vsctl set port <interface> tag=<vlan-id>
# Native VLAN

The Native VLAN is used for traffic that arrives without a tag.

Untagged traffic is placed into a default VLAN.

This ensures unknown or untagged traffic is still classified.

# Configure Native VLAN
ovs-vsctl set port eth0 tag=10 vlan_mode=native-untagged
# Trunk Links

A trunk carries traffic for multiple VLANs over one physical link.

Trunks are commonly used between switches and routers.

VLAN tags allow the receiving device to keep traffic separated.

Example Trunk Configuration
ovs-vsctl add-br br0
ovs-vsctl add-port br0 eth0 tag=10
# Inter-VLAN Routing

Devices in different VLANs cannot communicate directly.

A router is needed to move traffic between VLANs.

This process is called Inter-VLAN Routing.

# Router on a Stick (ROAS)

ROAS allows one router interface to handle multiple VLANs.

The router uses sub-interfaces to separate VLAN traffic.

Each sub-interface is usually linked to one VLAN.

Sub-Interface Format
<interface>.<vlan-id>
VyOS Example
set interfaces ethernet eth0 vif 10 description 'VLAN 10'
set interfaces ethernet eth0 vif 10 address '192.168.100.1/24'
Important Security Point

VLANs provide logical separation, not complete security.

If routing is allowed between VLANs, devices can still communicate.

VLANs alone are not a full security boundary.

# Secure Design Idea

Use ACLs, firewall rules, and zoning to control communication between VLANs.

Sensitive systems should be placed in separate VLANs with restricted access.
