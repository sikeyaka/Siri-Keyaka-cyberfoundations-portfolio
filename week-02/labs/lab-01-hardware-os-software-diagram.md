# Week 2 Lab — Cybersecurity Landscape & Digital Infrastructure Overview

**Student Name:** Siri Keyaka

**Date Completed:** 24 September 2026

**Module:** 1 — Digital Infrastructure & CLI | **Week:** 2  
**Submission Path:** `week-02/labs/lab-01-hardware-os-software-diagram.md`

---

## Overview

In this lab, you build a working mental model of the system you'll be securing throughout this course: the hardware, operating system, and software layers that make up every computer, and where the cybersecurity field fits around them. This lab has two parts. Part A connects this week's material to the CyberFoundations City map. Part B has you build and explain a diagram of how a computer's hardware, OS, and software layers interact.

**No terminal or command line is required this week** — that starts in Week 3.

---

## Lab Environment

| Component | Details |
|---|---|
| Environment | Browser-based Lab Portal (Module 1 orientation) |
| Required Materials | CyberFoundations City map; a diagram tool of your choice (hand-drawn and photographed, or any digital tool) |

**Prerequisite:** Portfolio repo created from the CyberFoundations student template in Week 1. This file is already in your repo at `week-02/labs/lab-01-hardware-os-software-diagram.md`, ready to fill in.

**New to the Lab Portal?** Watch this short walkthrough of how to find your Week 2 lab worksheet: [Accessing the Lab Worksheet — Step by Step](PASTE-VIDEO-LINK-HERE) *(~3 min)*.

---

## Part A — CyberFoundations City & the Cybersecurity Landscape

The CyberFoundations City map is your visual guide to the next 11 weeks. Each district represents a module of this course. This part connects this week's material to the map you were introduced to in Week 1.

### Step 1 — Open the Lab Portal Orientation Module

Log into the Lab Portal with your Microsoft account. From your Student Dashboard, open the **Module 1 orientation** module.

### Step 2 — Complete the Orientation Walkthrough

Work through the orientation content. It covers the same hardware/OS/software material as this week's lessons from a different angle — use it to check your understanding, not to replace the lessons.

### Step 3 — Locate This Week's District on the City Map

Open the CyberFoundations City map (introduced in Week 1, Lesson 6). Identify which district corresponds to Module 1 — Digital Infrastructure & CLI.

**District name:** Foundry District

```
The Foundry District
```

**Why this district fits this week's topics (1–2 sentences):**

```
The Foundry District fits Digital Infrastructure & CLI because it focuses on the foundational components that make computer systems work, including hardware, operating systems, and software. Understanding how these layers interact provides the foundation for working with and securing computer systems.
```

---

## Part B — Hardware, OS, and Software Diagram

A computer is a stack of layers: physical hardware at the bottom, an operating system managing that hardware in the middle, and the software you actually use on top. This part has you draw that stack and explain it in your own words.

### Step 1 — Identify the Layers

Before drawing anything, list the three layers you'll diagram and one example of what lives at each layer.

**Hardware layer — one example component:** 1.8 GHz Dual-Core Intel Core i5 processor

```
(e.g., CPU, RAM, storage — your choice)
```

**Operating system layer — name an OS:** macOS Monterey 12.7.6

```
(e.g., Windows, Linux, macOS)
```

**Software layer — one example application:** Google Chrome

```
(e.g., a web browser, a word processor)
```

### Step 2 — Sketch Your Diagram

Sketch a simple diagram (hand-drawn and photographed, or built in any digital tool) showing how the hardware, OS, and software layers stack and interact. Arrows or labels showing "what talks to what" matter more than visual polish. If you'd like a free browser-based option instead of hand-drawing, try [draw.io](https://www.drawio.com/) — no account required to get started.

### Step 3 — Upload and Embed Your Diagram

Upload your diagram image directly into your repo's assets folder — keep it there rather than pasting it loose into this file, so all of this week's images stay together and organized.

1. Go to your portfolio repository on GitHub.com and navigate to `assets/screenshots/week-02/`.
2. Click **Add file → Upload files**, then drag in your diagram image, and give it a descriptive name (lowercase, hyphens, no spaces, no timestamps — e.g. `hardware-os-software-diagram.png`).
3. Scroll down and click **Commit changes**.
4. Click on the uploaded image's filename to open it — you'll see the image itself displayed on the page.
5. Right-click directly on the image and choose **Copy image address** (Chrome/Edge) or **Copy Image Link** (Firefox).
6. Come back to this file, open the pencil (edit) icon, and paste that link into the embed line below, in place of the placeholder:

![Hardware/OS/software diagram](https://raw.githubusercontent.com/sikeyaka/Siri-Keyaka-cyberfoundations-portfolio/501f7c3a5229e41e417e5a4e00314dc681df54a5/assets/screenshots/week-02/hardware-os-software-diagram.png)

**If right-click doesn't show that option:** click the small download-arrow icon in the top-right of the image preview instead, then copy the URL from your browser's address bar.

**My Diagram:** MacBook Air Hardware, OS, and Software Layers

### Step 4 — Explain Your Diagram

In your own words — not a copied definition — explain how the three layers interact. Reference your own diagram directly.

```
My diagram shows how the software, operating system, and hardware layers of my MacBook Air depend on one another. Google Chrome runs on macOS Monterey, which manages the computer's hardware resources and allows Chrome to use resources such as the processor and memory. The hardware provides the physical resources needed for the operating system and applications to function. 
```

---

## Analysis Questions

Answer each question in your own words. These questions connect what you did in Parts A and B to the bigger picture of this course.

### Analysis Question 1

If the operating system crashed on the computer you diagrammed, which layer(s) would stop working, and which (if any) would keep working? Explain your reasoning.

```
If macOS crashed on my MacBook Air, the software layer would stop working because applications such as Google Chrome depend on the operating system to run. The hardware would still physically work, but I would not be able to use it normally because the operating system manages the connection between the hardware and software. I would need to restart or restore the operating system before I could use my applications again.
```

### Analysis Question 2

Pick one piece of software you use daily. Trace it down through the OS to the hardware it ultimately depends on. What would happen to that software if the hardware layer failed?

```
Google Chrome is a piece of software I use daily. Chrome runs through macOS Monterey, which uses hardware resources such as my Intel Core i5 processor and 8 GB of RAM to run the application and process information. If an essential hardware component failed, Chrome would either stop working or be unable to run because both the operating system and software depend on the hardware underneath them.
```

### Analysis Question 3

Explain, in your own words, why a cybersecurity professional needs to understand all three layers — hardware, OS, and software — rather than just the software layer where most visible attacks (like phishing emails) happen.

```
A cybersecurity professional needs to understand all three layers because a security issue at one layer can affect the others. Software may be where a threat is first noticed, but the operating system controls things such as processes, permissions, and access to hardware resources. Hardware can also have vulnerabilities or failures that affect the entire system. Understanding how all three layers interact makes it easier to identify where a security problem started, understand its impact, and determine how to respond to it.
```

---

## Lab Report Questions

Answer each question in complete sentences.

**1. What is the cybersecurity landscape, and why does it matter to someone starting this course?**

```
The cybersecurity landscape includes the systems, technologies, threats, vulnerabilities, and security practices involved in protecting digital environments. Understanding the landscape is important when starting this course because cybersecurity covers many different areas, including security operations, risk and compliance, networking, cloud security, and incident response. Having an understanding of the larger cybersecurity landscape helps me see how the technical skills I am learning can be applied to different cybersecurity roles and real-world situations.
```

**2. Which CyberFoundations City district did you identify in Part A, and how does its theme connect to the hardware/OS/software material in Part B?**

```
I identified the Foundry District for Module 1, Digital Infrastructure & CLI. The Foundry District represents the foundational components that computer systems are built on, which connects directly to the hardware, operating system, and software layers covered in Part B. Learning how these layers depend on one another provides a foundation for understanding how computer systems operate and how they can be secured.
```

**3. Of the three layers (hardware, OS, software), which one do you think is hardest to secure, and why?**

```
I think the software layer is the hardest to secure because there are many different applications and they are constantly being updated or changed. Software is also the layer that users interact with most often, which can introduce additional security risks through things like phishing links, malicious downloads, or vulnerable applications. Even when the hardware and operating system are secure, a vulnerable application or user action can still create an opportunity for an attacker.
```

---

## Submission Checklist

- [x] Lab Portal Module 1 orientation completed

- [x] District identified and explained

- [x] Hardware, OS, and software layer examples listed

- [x] Diagram uploaded to `assets/screenshots/week-02/` and embedded using a copied image link (not pasted loose, not a local file path)

- [x] Diagram explanation written in your own words (minimum 3 sentences)

- [x] All three Analysis Questions answered (minimum sentence counts met)

- [x] All three Lab Report Questions answered in complete sentences

- [x] This file is committed to your portfolio repo at `week-02/labs/lab-01-hardware-os-software-diagram.md`
