# Week 5 Notes — The Grid: Addresses, Names, Ports, and Diagnostics

## Key Concepts

- **IP Address:** Identifies a device's network interface and allows communication across networks.
- **Subnet Mask:** Determines which IP addresses belong to the same local network. A `/24` prefix corresponds to `255.255.255.0`.
- **Default Gateway:** Routes traffic from the local network to other networks.
- **Private vs. Public IP Addresses:** Private IPv4 ranges include `10.0.0.0/8`, `172.16.0.0/12`, and `192.168.0.0/16`. Public addresses are globally routable.
- **DNS:** Translates domain names into IP addresses. NXDOMAIN indicates a nonexistent DNS name, while successful resolution does not guarantee connectivity.
- **DHCP:** Automatically assigns IP addresses and other network settings through leases.
- **Ports:** Identify specific network services, including SSH (22), DNS (53), HTTP (80), HTTPS (443), RDP (3389), and SMTP (25).
- **TCP vs. UDP:** TCP provides reliable, connection-oriented communication, while UDP sends datagrams without guaranteed delivery.
- **TCP Handshake:** Establishes a connection through SYN → SYN-ACK → ACK, demonstrated in Lab 03.
- **Network Diagnostics:** `ping` tests ICMP responses, `traceroute` examines network hops, and `dig` performs DNS lookups. Missing responses do not necessarily indicate network failure.
- **The Ladder Rule:** Check local configuration → gateway → target hostname → target IP → trace the path.

## Command Reference

| Task | Bash / Linux | PowerShell |
|---|---|---|
| Show IP address | `ip addr` | `ipconfig` |
| Show default gateway | `ip route` | `Get-NetRoute` |
| Test reachability | `ping` | `Test-Connection` |
| Trace network path | `traceroute` | `Test-NetConnection -TraceRoute` |
| DNS lookup | `dig` | `Resolve-DnsName` |

## Understanding Network Configuration

An IP address identifies a device on a network. The subnet mask determines which devices are on the same local network, while the default gateway connects the device to other networks.

## DNS and Connectivity

DNS translates domain names into IP addresses. NXDOMAIN means the requested name does not exist in DNS, while a name that resolves but does not respond may indicate a connectivity, firewall, or service issue rather than a DNS lookup failure.

## Ports and Network Security

An IP address identifies the destination device, while a port identifies the service receiving traffic. Defenders monitor open ports because unnecessary or vulnerable services can create security risks.

## The Ladder Rule

1. Check my own network configuration.
2. Check the default gateway.
3. Test the target by hostname.
4. Test the target by IP address.
5. Trace the network path.

Following this order helps narrow down connectivity issues systematically instead of guessing or troubleshooting the wrong component.

## DHCP and Address Assignment

DHCP automatically assigns IP addresses and network settings, allowing my laptop to connect without manual configuration. Servers like `grid-dns` use static addresses or DHCP reservations so other devices can reliably locate them.

## Additional Practice: Traceroute

I used macOS Terminal to run `traceroute wikipedia.org`. The command continued to its default maximum of 64 hops, with later probes returning `* * *`.

This reinforced that unanswered probes do not necessarily indicate a network outage. Firewalls, filtering, and router configurations can affect diagnostic responses.

## Key Takeaway

Week 5 strengthened my understanding of network communication, addressing, and troubleshooting. I learned the importance of following a structured diagnostic process and interpreting command output carefully before identifying a potential network issue.

---

*CyberVisionaries Institute — Cyber Foundations, Tier I*

---

*CyberVisionaries Institute · Cyber Foundations · Tier I*
