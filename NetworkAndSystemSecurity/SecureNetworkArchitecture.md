## Security Zones and VLAN Design 🛡️
# Why Network Design Changes with VLANs

VLANs make security an important part of network design.

A good network design should balance:

Security

Optimization

Redundancy

These should be implemented without weakening one another.

# Security Zones

Security zones are used to make VLANs more secure.

A security zone defines:

What devices or users are in a VLAN

How traffic can enter or leave that VLAN

Security zones help turn VLANs into a real security boundary.

## Common Security Zones
# External

Includes all devices and entities outside the organization’s control.

Represents untrusted outside networks and users.

# DMZ (Demilitarized Zone)

Separates untrusted traffic from internal resources.

Used for systems that must be reachable without exposing the internal network.

# Trusted

Contains normal internal devices and networks.

Used when systems do not store highly sensitive data.

# Restricted

Contains high-risk or highly sensitive systems.

Access should be tightly controlled.

# Management

Contains systems used for device or network administration.

May include management platforms and infrastructure services.

Sometimes grouped with the audit zone.

# Audit

Contains systems used for security monitoring and logging.

Supports visibility, monitoring, and security operations.

Sometimes grouped with the management zone.

# Why Security Zones Matter

Security zones control how traffic moves between parts of the network.

They reduce unnecessary access between devices and systems.

They help protect sensitive resources from lower-trust areas.

# Controlling External and Remote Access

Not all traffic remains outside the network.

Some users or devices may need access to internal resources.

Access can be controlled using rules based on:

MAC address

IP address

Other access conditions

These rules are enforced through network security controls.

 #Access and Policy

Traffic movement is not only decided by technology.

It is also controlled by:

Security policy

Compliance requirements

Access permissions

These determine what users and devices are allowed to reach.

