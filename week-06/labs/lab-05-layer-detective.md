# Week 6 Lab 05 — Layer Detective

**Student Name:** Siri Keyaka

**Date Completed:**

**Module:** 2 — Networking & Cloud Foundations | **Week:** 6  
**Submission Path:** `week-06/labs/lab-05-layer-detective.md`

---

## Overview

**This is a SHORT lab — 20 to 30 minutes — and it needs no VM.** No Cloud Heights session, no simulator, no screenshot. This is a thinking lab: you take the evidence you have already collected in Weeks 5 and 6 and sort it into layers.

This is an **independent** lab.

---

## Lab Environment / Pre-Lab Check

| Component | Details |
|---|---|
| Environment | This worksheet only — nothing to start, nothing to connect to |
| Prerequisite | Week 5 labs and Week 6 Labs 01–04 |
| Screenshot | None required |

---

## Part A — The Seven-Row Table

Fill in every row. For the last column, name one **real thing you personally saw** in Weeks 5–6 that belongs at that layer.

| # | Layer name | One-line job | Real thing from Weeks 5–6 |
| --- | --- | --- | --- |
| 7 | Application | Provides network services used by applications. | Used dig to investigate DNS resolution in Week 5. |
| 6 | Presentation | Handles data formatting, encoding, and encryption. | Viewed human-readable DNS query results in Week 5, demonstrating data presentation. |
| 5 | Session | Establishes, manages, and ends communication sessions. | Established an Azure Bastion terminal session in Week 6 Lab 01. |
| 4 | Transport | Supports end-to-end communication using TCP and UDP. | Used dig for DNS queries in Week 5 (typically UDP). |
| 3 | Network | Handles IP addressing, routing, and packet delivery. | Used ping and traceroute to investigate network connectivity in Week 6 Lab 03. |
| 2 | Data Link | Handles local network communication and frame delivery. | Used ip addr in Week 6 to inspect the eth0 network interface and its link-layer information. |
| 1 | Physical | Supports transmission through physical or virtual network infrastructure. | Accessed an Azure-hosted VM in Week 6, which depends on underlying network infrastructure. |

---

## Part B — Case Files

For each case, name the layer where the problem lives, and name the evidence proving the layers **below** it were already working.

### Case File 1 — The Name That Went Nowhere

A hostname lookup fails, but pinging the machine's IP address directly succeeds.

Layer:

```
Layer 7 — Application (DNS)

```

Evidence that the layers below were working:

```
The successful ping to the machine's IP address confirms that IP connectivity was functioning and ICMP replies were received. Since direct IP communication succeeded while hostname resolution failed, the evidence points to a DNS issue rather than a general network connectivity failure.
```

### Case File 2 — Permission Denied

`ssh` to a host returns `Permission denied` after a password prompt.

Layer:

```
Layer 7 — Application (SSH Authentication)
```

Evidence that the layers below were working:

```
Receiving an SSH password prompt indicates that the client successfully reached the SSH service and established communication. The Permission denied response indicates an authentication failure rather than a basic network connectivity issue.
```

### Case File 3 — The Cable Story

A machine reports no link on its interface and has no address at all.

Layer:

```
Layer 2 — Data Link (Possible Layer 1 Cause)
```

Evidence and reasoning:

```
An interface reporting no link suggests that local network connectivity has not been established. The problem could involve a disconnected cable, disabled switch port, or virtual network adapter, so I would verify the link state before investigating IP addressing or routing.
```

### Case File 4 — Ping Works, The Page Does Not

`ping` to a server succeeds, but `curl http://<that server>` returns nothing useful.

Layer:

```
Layer 7 — Application (HTTP), with Layer 4 requiring verification
```

Evidence that the layers below were working:

```
A successful ping confirms that the server responds to ICMP traffic at the network layer. However, it does not confirm that TCP port 80 is accessible or that the HTTP service is functioning, so I would investigate the transport connection and web service next.
```

### Case File 5 — Wrong Neighbourhood

A machine has an address, but its default route points somewhere that cannot forward its traffic.

Layer:

```
Layer 3 — Network (Routing)
```

Evidence and reasoning:

```
The machine has an IP address, but its default route points to a gateway that cannot forward traffic to other networks. This indicates a network-layer routing issue rather than a problem with DNS resolution or application authentication.
```

---

## Part C — The Silent Gateway Case

In Lab 03 the Azure default gateway did not answer your ping. However, your VM had a valid default route configured, and your local communication with the Grid Beacon — the ping replies, the HTTP banner, and `TRACE ID: CF-NET-0604` — succeeded.

A failed gateway ping is one piece of evidence — not automatically proof of a gateway or network failure. But the evidence you weigh against it has to be the right kind of evidence.

The Grid Beacon at `10.60.6.4` sits on the same local subnet as your VM (`10.60.6.0/26`). Reaching it proves **local-subnet connectivity** — that traffic never crosses the default gateway, so beacon success alone cannot prove the gateway forwarded anything. Your `ip route` output proves a **default route is configured** — your VM knows where it intends to send non-local traffic — but it does not prove the gateway forwarded that traffic. The evidence that demonstrates the **default path is functioning** is successful communication with a destination outside `10.60.6.0/26`, such as the outbound internet access through NAT that you examined in Lab 04.

### Step 1 — Rule on the Case

Is the failed gateway ping enough evidence to declare a network-layer failure? Explain your answer using the other evidence you collected. In your response, distinguish between:

- evidence that proves **local-subnet connectivity**
- evidence that proves a **default route is configured**
- evidence that supports **successful off-subnet connectivity**

```
No, a failed gateway ping alone does not prove a network-layer failure. The Grid Beacon's response confirms local-subnet connectivity, while `ip route` confirms that a default route is configured. Successful communication with an off-subnet destination would demonstrate that traffic can pass beyond the local network, even if the gateway does not respond to ICMP.
```

### Step 2 — Name the Correct Conclusion

For each of these four results, state what it actually proves: the Grid Beacon at `10.60.6.4` answering, the default route shown by `ip route`, a successful connection to a destination outside your local subnet, and the gateway's failed ping. Then state the rule you would give a junior colleague about the difference between an observation ("the gateway did not answer my ICMP probe") and a diagnosis ("the gateway is broken"):

```
The Grid Beacon's response proves local-subnet connectivity. The 'ip route' output confirms that a default route is configured but does not prove traffic was forwarded. A successful connection to an off-subnet destination demonstrates that the default network path is functioning. The failed gateway ping only shows that the gateway did not respond to ICMP. A failed probe is an observation, not enough evidence to diagnose a broken gateway.
```

---

## Part D — Two Models, One Job

The OSI model has seven layers. The practical TCP/IP model most engineers speak day to day has four or five.

### Step 1 — Map Them

Briefly show how the seven OSI layers collapse into the practical model:

```
The TCP/IP model combines OSI Layers 7 (Application), 6 (Presentation), and 5 (Session) into the Application layer. OSI Layer 4 (Transport) maps to TCP/IP Transport, while OSI Layer 3 (Network) maps to the Internet layer. OSI Layers 2 (Data Link) and 1 (Physical) combine into the Network Access layer. In the five-layer version, Data Link and Physical remain separate.
```

### Step 2 — When Each Is Useful

Explain when the seven-layer vocabulary helps and when the practical model is the better tool:

```
The seven-layer OSI model is useful for identifying where a network problem may be occurring and organizing troubleshooting steps. It helps distinguish issues involving physical connectivity, routing, transport protocols, and application services. The TCP/IP model is more practical for everyday networking because it reflects how protocols such as IP, TCP, UDP, DNS, and HTTP operate together.
```

---

## Analysis Questions

**Analysis Question 1.** Explain the Ladder Rule using layer language. What does "test the near thing first" mean when the rungs are layers? *(Minimum 3 sentences.)*

```
The Ladder Rule means troubleshooting from the closest, most basic point of connectivity before moving toward higher network layers. For example, I would check the network interface and IP configuration before investigating DNS or application services. Testing each layer systematically helps identify where communication stops working without making assumptions about the cause.
```

**Analysis Question 2.** Why is "which layer is this?" a faster question than "what is broken?" when you are under pressure? *(Minimum 3 sentences.)*

```
Identifying the affected layer helps narrow down possible causes instead of troubleshooting the entire network at once. For example, if an IP address responds to ping but a hostname does not resolve, I would investigate DNS before assuming the network is down. This approach saves time, reduces unnecessary troubleshooting, and helps prioritize the next diagnostic step.
```

**Analysis Question 3.** Pick one case file from Part B and describe the very next command you would run to confirm your ruling, and what result would change your mind. *(Minimum 2 sentences.)*

```
For Case File 1 — The Name That Went Nowhere, I would run dig to check whether the hostname resolves to the expected IP address. If it resolves correctly, I would reconsider DNS as the cause and investigate why the original lookup failed.
```

---

## Submission Checklist

- [x] All seven rows of the OSI table completed with a real Week 5–6 anchor each (Part A)

- [x] All five case files given a layer and supporting evidence (Part B)

- [x] Silent gateway case ruled on correctly (Part C)

- [x] OSI vs. practical TCP/IP model compared (Part D)

- [x] All three Analysis Questions answered (minimum sentence counts met)

- [x] No screenshot required for this lab

- [x] This file is committed to your portfolio repo at `week-06/labs/lab-05-layer-detective.md`

---

## GitHub Commit Subsection

1. Open **Week 6 → Lab 05: Layer Detective** in the Lab Portal.
2. Fill in the worksheet fields.
3. Click **Submit to GitHub** — the Portal commits to `week-06/labs/lab-05-layer-detective.md`.

---

*CyberVisionaries Institute · Cyber Foundations · Tier I*
