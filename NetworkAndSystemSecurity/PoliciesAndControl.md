## Traffic Filtering and ACL Notes 🛡️📄
# Enforcing Segmentation

VLANs and security zones separate network areas, but policies are needed to control traffic between them.

If routes exist between VLANs, traffic must be explicitly allowed or denied.

This enforcement is done through traffic filtering and access control policies.

# Policies

Policies define how network traffic is handled.

They determine whether traffic is allowed, denied, prioritized, or redirected.

Policies are used before or alongside normal routing decisions.

They support security, control, and segmentation.

# IEEE and Network Policy Standards

IEEE standardizes some traffic and access control methods.

One example is QoS (Quality of Service) under 802.11e.

Many traffic control methods are also vendor-specific but still follow common security goals.

# Traffic Filtering

Traffic filtering is the process of controlling network traffic based on defined rules.

It improves:

Security

Validation

Segmentation

Filtering decisions are based on criteria such as:

Source address

Destination address

Protocol

Port

# ACLs (Access Control Lists)

An ACL is a rule-based method used to filter traffic.

It acts as a structured list of conditions that decide whether traffic is permitted or denied.

ACLs are widely used across different vendors and platforms.

# ACEs (Access Control Entries)

An ACL contains ACEs, which are the individual rules inside the list.

Each ACE defines:

Action such as permit or deny

Match criteria such as source or destination

Address or range to match against

# VyOS ACL Structure

VyOS uses an access-list policy as a basic filtering method.

It supports filtering with ACLs or prefix lists.

ACL Creation
set policy access-list <acl_number>
Add Description
set policy access-list <acl_number> description <text>
Add Rule Action
set policy access-list <acl_number> rule <1-65535> action <permit|deny>
Define Rule Criteria
set policy access-list <acl_number> rule <1-65535> <destination|source> <any|host|inverse-mask|network>
# ACL Logic

The ACL number identifies the access list.

The rule number identifies a specific ACE.

The action decides whether matching traffic is allowed or dropped.

The source or destination field defines what packet detail is checked.

The router enforces the rule when traffic matches the defined criteria.

# What ACLs Can Do

Permit traffic from approved hosts or networks.

Deny traffic to protected systems.

Support segmentation between VLANs and zones.

Control basic access at the router level.

# ACL Limitations

Router ACLs provide only limited security control.

They are useful for basic filtering but are not always flexible enough for advanced policy enforcement.

More detailed security needs may require:

Firewalls

Application-aware filtering

Protocol-specific controls

Key Security Idea

VLAN separation alone is not enough.

ACLs and policies enforce how traffic moves between VLANs and zones.

Strong segmentation depends on both:

Network design

Traffic control rules
