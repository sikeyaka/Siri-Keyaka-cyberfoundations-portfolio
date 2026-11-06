# Week 5: Networking Fundamentals

## Overview

Week 5 of the CyberVisionaries Cyber Foundations program focused on networking fundamentals, network communication, and troubleshooting connectivity issues.

Through practical labs, I explored how devices communicate across networks, how network infrastructure supports connectivity, and how common networking tools can help investigate network behavior.

## Labs Completed

### Lab 01: Finding Your Place
Explored network identification and addressing concepts to better understand how devices are identified and communicate within a network.

[View Lab 01](labs/lab-01-finding-your-place.md)

### Lab 02: The Grid Outage
Investigated network connectivity and troubleshooting concepts, focusing on identifying potential causes of communication failures.

[View Lab 02](labs/lab-02-the-grid-outage.md)

### Lab 03: Reading the Grid's Mail
Explored how network communication and related information can be examined to better understand activity across connected systems.

[View Lab 03](labs/lab-03-reading-the-grids-mail.md)

## Key Concepts & Skills

- IP addressing and network identification
- Network connectivity and communication
- Routers and packet forwarding
- Basic network troubleshooting
- Interpreting diagnostic command output
- Understanding network timeouts and filtering

## Tools & Commands

- **macOS Terminal:** Command-line environment for networking exercises
- **traceroute:** Examining the path network probes take toward a destination
- **ping:** Testing ICMP Echo responses and basic reachability

## Additional Practice: Traceroute Investigation

As part of my networking practice, I ran:

`traceroute wikipedia.org`

The command continued to the macOS default maximum of 64 hops, with later probes returning timeouts (`* * *`).

This exercise reinforced an important networking concept: a missing traceroute response does not necessarily indicate a network outage. Routers and firewalls may filter or deprioritize diagnostic traffic.

## Cybersecurity Relevance

Understanding network behavior is essential for security operations and incident response. These fundamentals support the investigation of connectivity problems, suspicious network activity, and potential security misconfigurations.

## Documentation

- [Week 5 Notes](notes.md)
- [Week 5 Reflection](reflection.md)

*Notes and reflection are submitted through the CVI lab portal.*

---

[Back to Portfolio Home](../README.md)
