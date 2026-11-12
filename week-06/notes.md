# Week 6 Notes — Cloud Heights: Cloud VMs, SSH, VNets & Layers

**Student Name:** Siri Keyaka

**Date Completed:**

Summarize this week's key concepts in your own words — not copy-pasted definitions. This week moved from the simulated Grid into a real cloud environment, so focus on what you personally observed as well as what each term means.

> **Cloud Heights Security Rule:** Your Bastion shareable link and Cloud Heights password are private access credentials. Never paste either into this file, a screenshot, your GitHub repository, Circle, or a chat message.

## Key Concepts This Week

- **Cloud** — other people's computers, professionally operated and reached over a network
- **Datacenter** — the physical facility where cloud computing equipment lives
- **Region** — a geographic area where a cloud provider operates datacenters
- **Virtual machine (VM)** — a computer created in software; in Cloud Heights, your VM runs on hardware in a real datacenter
- **IaaS / PaaS / SaaS** — different levels of cloud service: rent the room, rent the workshop, or rent the finished service
- **Shared responsibility model** — the cloud provider secures the building and underlying platform; the customer is still responsible for what belongs to them
- **Provisioning** — creating and preparing a resource so it is ready to use
- **Golden image / snapshot** — a known starting point that can be used to create consistent machines
- **Snapshot vs backup** — a snapshot is a point-in-time copy used for recovery or cloning; a backup is a separate recovery copy with a different purpose
- **Azure Bastion** — the guarded front desk that gives you browser-based SSH access without giving your VM a public IP
- **Bastion shareable link** — sensitive access information that must never be committed to GitHub or exposed in screenshots
- **SSH (Secure Shell)** — remote command-line access to another machine
- **SSH client and server** — the client starts the connection; the server listens and answers
- **Port 22** — the standard numbered door used by SSH
- **Host / fingerprint verification** — the verify-before-approve habit when connecting to a host for the first time
- **Authentication** — proving that you are the account you claim to be
- **Remote session / remote shell** — the live command-line session running on another machine
- **Getting TO vs getting INTO a machine** — network reachability and authentication are different problems
- **`hostname`** — asks which machine you are on
- **`whoami`** — asks which account you are using
- **`pwd`** — asks where you are in the filesystem
- **Private IP address** — an address used inside a private network rather than directly on the public internet
- **Virtual network (VNet)** — the private cloud neighborhood where resources communicate
- **Subnet** — a smaller address range inside a VNet; a floor inside the larger building
- **NAT / outbound translation** — lets a privately addressed machine communicate outward without giving the machine its own public IP
- **Network Security Group (NSG)** — the network guard post that controls what traffic is allowed; you take control of these rules in Week 7
- **Known-good reference point** — a target whose expected behavior gives you something reliable to compare against
- **Grid Beacon** — the known-good Cloud Heights host at `10.60.6.4`
- **The silent Azure gateway** — Azure's default gateway may not answer ICMP ping even when the network is healthy
- **OSI model** — the seven-layer vocabulary used to organize network and application behavior
- **TCP/IP model** — the more compact layer model commonly used by practitioners
- **Layers** — a way to separate different jobs in a communication path so troubleshooting can be systematic
- **Encapsulation** — information travelling inside other information, like a letter inside an envelope inside a mailbag
- **The Ladder Rule in the real cloud** — work outward, prove what works, use the route and a known-good target, and never let one silent tool response choose the culprit by itself

## My Cloud Heights Command Table

You used these commands on a real Ubuntu machine this week. Instead of memorizing syntax, write down the **question each command answers** or the job it performs.

| Command | What question does it answer / what does it do? |
| --- | --- |
| `hostname` | Shows the name of the machine I am connected to. |
| `whoami` | Shows which user account I am currently using. |
| `pwd` | Displays my current working directory. |
| `ip addr` | Displays network interfaces and their assigned IP addresses. |
| `ip route` | Shows the routing table, including the default gateway used to reach other networks. |
| `ping` | Tests whether a destination responds to ICMP echo requests. |
| `traceroute` | Helps identify the network hops packets take toward a destination. |
| `dig` | Queries DNS to investigate how domain names resolve to IP addresses. |
| `curl` | Sends requests to a URL or service and displays the response. |
| `ssh` | Establishes a secure remote command-line connection to another machine. |
| `exit` | Closes the current shell or ends a remote session. |

## In My Own Words

### 1. Getting TO vs Getting INTO

Explain the difference between getting **TO** a machine and getting **INTO** a machine. Use something you personally observed in Cloud Heights as evidence.

```
Getting TO a machine means establishing a network connection to reach it, while getting INTO a machine means successfully authenticating and accessing its system. In Cloud Heights, I used Azure Bastion to reach my assigned Ubuntu VM through a browser-based SSH connection. After authenticating, I could access the remote terminal and run commands such as hostname, whoami, and pwd. This showed me that reaching a machine and being authorized to access it are two separate steps.
```

### 2. The Silent Gateway

Your Azure gateway did not answer `ping`, but your VM was still healthy. Explain how you proved the network was working and what this taught you about interpreting tool output.

```
During Week 6, my Azure default gateway did not respond to ping, but that did not automatically mean the network was broken. I used ip addr to verify my VM's private IP address and ip route to confirm that a default gateway was configured. I also successfully communicated with the Grid Beacon at 10.60.6.4, receiving ping replies and an HTTP response containing TRACE ID: CF-NET-0604. This confirmed that local-subnet communication was working, although it did not independently prove that the gateway was forwarding traffic outside the subnet. I learned that one failed test is not enough to diagnose a network failure and that I need to compare multiple pieces of evidence.
```

### 3. Private on the Inside, Connected to the Outside

Explain how your Cloud Heights VM can reach the internet even though it has only a private IP address. Then explain how **you** reach the VM from outside its VNet.

```
My VM uses a private IP address and accesses the internet through NAT, which translates outbound traffic to a public address. I connect to the VM through Azure Bastion using browser-based SSH without exposing the VM directly to the internet.
```

### 4. VNet vs Subnet

Explain the difference between a VNet and a subnet using the Cloud Heights building/floor analogy. Then explain why separating systems into smaller network ranges can help security.

```
A VNet is like an entire building, while a subnet is one floor within it. In Cloud Heights, the VNet uses 10.60.6.0/24, and the student subnet uses 10.60.6.0/26. Separating networks into smaller sections helps control access and contain security threats.
```

### 5. The Ladder Rule Has a Map Now

The Ladder Rule never used the words OSI or TCP/IP. Explain how the layer models give you a map for the same troubleshooting process you have already been using.

```
The OSI and TCP/IP models organize network communication into layers, making the Ladder Rule easier to follow. By checking interfaces, IP addresses, routing, and application services systematically, I can identify where a problem occurs instead of assuming the entire network is down.
```

---

## Submission Checklist

- [x] I summarized the Week 6 concepts in my own words, not copied definitions

- [x] I completed my Cloud Heights command table

- [x] I explained getting TO vs getting INTO a machine

- [x] I documented what the silent Azure gateway taught me

- [x] I explained the Cloud Heights private-network design

- [x] I connected the Ladder Rule to network layers

- [x] I checked that my Bastion shareable URL does not appear anywhere in this file

- [x] I checked that my Cloud Heights password does not appear anywhere in this file

- [x] This file is committed to my portfolio repo at `week-06/notes.md`

---

*CyberVisionaries Institute — Cyber Foundations, Tier I*
