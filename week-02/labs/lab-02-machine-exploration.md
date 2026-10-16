# Week 2 Lab — Explore Your Own Machine (Real Specs & Live Activity)

**Student Name:** Siri Keyaka

**Date Completed:** 08 October 2026

**Module:** 1 — Digital Infrastructure & CLI | **Week:** 2  

---

## Overview

This lab examines the hardware specifications and real-time system activity of my MacBook Air using macOS system settings and Activity Monitor.

The exercise involves documenting the operating system version, installed RAM, and storage capacity, then observing CPU usage, memory consumption, and active processes. These observations build on the hardware, operating system, and software relationships explored in Lab 01 and demonstrate how system resource monitoring supports performance analysis and cybersecurity investigations.

## Lab Environment

| Component | Details |
| --- | --- |
| Environment | Local MacBook Air |
| Operating System | macOS Monterey 12.7.6 |
| Monitoring Tool | macOS Activity Monitor |
| Installed Memory | 8 GB 1600 MHz DDR3 |
| Storage Capacity | 250.79 GB |
| Focus | System specifications, resource utilization, and process monitoring |

---

## Part A — Find Your Real Specs

### Step 1 — Find Your OS Version

**OS and version:** macOS Monterey 12.7.6


### Step 2 — Check Your Installed RAM

**Installed RAM:** 8 GB 1600 MHz DDR3

### Step 3 — Check Your Available Storage

**Total storage:** 250.79 GB

**Free storage:** 16.64 GB available

---

## Part B — Watch It Live

Used macOS Activity Monitor to examine real-time CPU utilization, memory consumption, and running processes.

### Step 4 — Record CPU Usage

**Current CPU usage:** 15.52%

- System: 6.80%
- User: 8.72%
- Idle: 84.48%

**Calculation:** 6.80% + 8.72% = 15.52%

### Step 5 — Record Memory Usage

**RAM in use:** 6.58 GB out of 8 GB total

- Physical memory: 8 GB
- Memory used: 6.58 GB
- Memory pressure: Green

### Step 6 — List Five Running Processes

| Process Name | What I Think It Does |
| --- | --- |
| Google Chrome | A web browser that lets me access websites and online applications. |
| WindowServer | Manages the windows and graphics displayed on my Mac. |
| Mail | Runs Apple's email application and helps manage my emails. |
| kernel_task | Helps macOS manage system resources and hardware operations. |
| RTProtectionDaemon | Appears to be a background security process that monitors for potential threats. |



### Step 7 — Screenshot and Embed

**Activity Monitor — Memory Usage and Running Processes**

![Activity Monitor Memory Usage and Processes](https://raw.githubusercontent.com/sikeyaka/Siri-Keyaka-cyberfoundations-portfolio/aa413d31d18a21fcda71aabbe37cd74d7fc86cef/assets/screenshots/week-02/machine-exploration-memory.png)

---

### Step 8 — Connect the Numbers

In your own words, explain how the real numbers you found in Part A (OS version, RAM, storage) relate to what you just watched live in Part B. Which number describes hardware, and which describes the OS?

```
Part A showed my Mac's hardware specifications, including RAM and storage, along with its macOS version. Part B showed how the operating system manages those hardware resources in real time, with 6.58 GB of 8 GB RAM in use and 15.52% CPU usage.
```

---

## Analysis Questions

### Analysis Question 1

Pick one process from your list in Part B, Step 6. Is it "software" in the sense Lab 01 used that word? Explain how it depends on the OS and on hardware to actually run.

```
Google Chrome is an example of application software because it allows users to browse the internet and access web-based applications. It depends on macOS to manage system resources, including memory, processing, and network access. The software also relies on physical hardware, such as the CPU and RAM, to execute instructions and keep browser tabs and processes running.
```

### Analysis Question 2

Your CPU usage number changes constantly, even when you're not doing anything. Explain, in your own words, why watching this number matters for security work — not just for performance. (Hint: think about what it might mean if a process you don't recognize suddenly spikes CPU usage.)

```
Monitoring CPU usage can help identify unusual system activity that may indicate a security threat. A sudden spike from an unfamiliar process could suggest malware or unauthorized activity. Investigating these changes can help detect potential threats before they cause further damage. 
```

### Analysis Question 3

Compare what you saw in Task Manager/Activity Monitor to the diagram you built in Lab 01. What's the same? What did watching your machine live show you that a static diagram couldn't?

```
Both Lab 01 and Activity Monitor showed how hardware, the operating system, and software work together. The diagram illustrated these relationships, while Activity Monitor showed them in action. Watching my Mac in real time helped me see how CPU and memory usage fluctuate as processes run.
```

---

## Lab Summary

Examined the hardware specifications and real-time activity of my MacBook Air using macOS system settings and Activity Monitor. Documented CPU utilization of 15.52%, memory usage of 6.58 GB out of 8 GB, and five running processes, including Google Chrome, WindowServer, Mail, kernel_task, and RTProtectionDaemon.

This exercise reinforced how operating systems manage hardware resources and application processes. It also demonstrated the value of monitoring CPU usage, memory consumption, and running processes when identifying unusual system behavior and investigating potential security concerns.

---

*CyberVisionaries Institute | CyberFoundations | Week 2*
