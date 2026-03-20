🌐 Client/Server Model & Firewalls
🖥️ Client vs Server

Any networked device can act as a client, server, or both.

Server provides a service; client connects to use it.

Common servers:

Web: HTTP, HTTPS

Mail: SMTP(S), POP3(S), IMAP(S)

DNS: Name resolution

SSH: Remote access

Server listens on a known port, client initiates connection.

🔥 Firewall Fundamentals

A firewall controls incoming and outgoing network traffic.

Without a firewall:

Any client can connect to any server.

A compromised system can open listening ports and act as a server.

Firewalls enforce traffic filtering rules to reduce attack surface.

🛡️ Host-Based Firewall

Installed on a single system (not network-wide).

Controls:

Inbound traffic (what can enter)

Outbound traffic (what can leave)

Prevents attackers from exposing unauthorised services.

⚙️ Firewall Types
Stateless Firewall

Filters packets based only on header fields.

Does not track connections.

Can be bypassed by manipulating packet flags.

Stateful Firewall

Tracks active connections.

Filters based on:

Packet headers

Connection state

Provides stronger security than stateless filtering.

📡 Packet Filtering Fields

IP Header:

Source IP address

Destination IP address

TCP/UDP Header:

Source port

Destination port

⚠️ Filtering is based on ports, not processes.

🔐 Process-Level Control

Linux cannot filter by process using firewall alone.

Tools for finer control:

SELinux

AppArmor

Enforce per-process network access policies.

⚙️ Netfilter Framework
🧠 Netfilter

Core Linux kernel packet filtering system.

Requires front-ends:

iptables

nftables

🧾 iptables
Chains

INPUT → Incoming packets

OUTPUT → Outgoing packets

FORWARD → Routed packets

Example: Allow SSH (Port 22)
iptables -A INPUT -p tcp --dport 22 -j ACCEPT
iptables -A OUTPUT -p tcp --sport 22 -j ACCEPT
Default Deny Policy
iptables -A INPUT -j DROP
iptables -A OUTPUT -j DROP
Reset Rules
iptables -F
⚡ nftables

Modern replacement for iptables.

Improved performance and scalability.

Requires manual creation of tables and chains.

Setup Example
nft add table fwfilter
nft add chain fwfilter fwinput { type filter hook input priority 0 \; }
nft add chain fwfilter fwoutput { type filter hook output priority 0 \; }
Allow SSH
nft add rule fwfilter fwinput tcp dport 22 accept
nft add rule fwfilter fwoutput tcp sport 22 accept
View Rules
nft list table fwfilter
🧰 UFW (Uncomplicated Firewall)

Simplified front-end for firewall management.

Easier than iptables/nftables.

Allow SSH
ufw allow 22/tcp
Check Status
ufw status
📋 Firewall Policy Design
🔒 Policy Approaches

Deny All + Allow Exceptions

Strong security

Harder to manage

Allow All + Block Exceptions

Easier usability

Weaker security

🎯 Example Policy

Allow only:

DNS (53)

HTTP (80)

HTTPS (443)

Blocks all other traffic.

⚠️ Limitation:

Non-standard ports will be blocked, requiring rule exceptions.
