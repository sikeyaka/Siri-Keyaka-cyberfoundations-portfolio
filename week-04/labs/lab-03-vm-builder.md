# Week 4 Lab — Build Your First Virtual Machine (VM Builder Simulator) ★ Deliverable 1

**Student Name:** Siri Keyaka

**Date Completed:** 19 October 2026

**Module:** 1 — Digital Infrastructure & CLI | **Week:** 4  
**Submission Path:** `week-04/labs/lab-03-vm-builder.md`

---

## Overview

Lessons 3 and 4 taught you what a virtual machine is and how one lives and dies. This capstone lab hands you the keys: in the VM Builder Simulator you'll provision a machine of your own through the full five-question wizard (Part A), handle whatever provisioning throws at you (Part B), and run the complete lifecycle — stop, start, snapshot, delete — while a billing meter runs (Part C). This lab is the heart of **★ Deliverable 1: VM concepts + CLI screenshots** — its two screenshots join the two from Labs 01 and 02 in your portfolio repo.

**The simulator will push back on purpose.** Taken names, refused passwords, quota limits, and a region that sometimes fails are all part of the exercise — reading an error calmly and fixing the right thing *is* the skill being graded. Errors here are progress, not mistakes.

---

## Lab Environment / Pre-Lab Check

| Component | Details |
|---|---|
| Environment | CyberFoundations VM Builder Simulator — runs entirely in your web browser; nothing to install, no account needed, no real servers, no real money |
| Prerequisite | Week 4, Lessons 3 and 4 completed; Labs 01 and 02 recommended first |
| Concept Checks | The simulator gates progress on four Concept Checks — all four are covered in Lessons 3 and 4 |
| Time | Plan for 30–45 minutes, including this worksheet |

### How to Open the Simulator — Step by Step

1. Open your web browser (Chrome, Edge, Firefox, or Safari all work — use a computer, not a phone, so your screenshots capture the full screen).
2. Go to this address (you can also click the **VM Builder Simulator** link on the Lab Portal's Week 4 page — same destination):

```
https://cybervisionariesinstitute.github.io/cyberfoundations-simulators/vm-builder.html
```

3. Confirm you're in the right place: you should see a dark purple header reading **"Foundry District Cloud Annex"** and a page titled **"Mission Briefing: Provision Your First Virtual Machine."** If you see anything else, re-check the address.
4. Read the Mission Briefing all the way down — especially the **"How to use this simulator"** box. It explains the six steps, the Concept Checks, and the two screenshot moments.
5. Get your screenshot tool ready before you begin: **Windows:** press `Win + Shift + S` · **Mac:** press `Cmd + Shift + 4`, then drag to capture. You will need it twice, at moments the simulator announces with a 📸 banner.
6. Keep this worksheet open in a **second browser tab**, side by side with the simulator — you'll record answers as you go.

**⚠️ One thing to know before you start:** refreshing the simulator page **resets the entire simulation** — nothing is saved between visits. That's safe (it's a training environment), but capture each screenshot when prompted, before moving on, and don't refresh mid-run unless you want a fresh start.

**Also before you start:** have Lesson 4's Resource Pack open to its Quick Reference page (the lifecycle/billing table). You'll want it.

---

## Part A — Provision Your Machine

### Step 1 — Name It Like a Professional

Work through the Basics screen: choose a VM name that passes the naming rules *and* would tell a stranger what this machine is for. Note: at least one obvious name is already taken — if you hit **NameNotAvailable**, that's the simulator doing its job; pick another and record what happened.

The name you chose, and whether you hit the taken-name error first:

```
I named my virtual machine `soc-lab-vm-01`. I chose this name because it identifies the machine as a Security Operations Center (SOC) lab VM and follows a clear naming convention. The simulator accepted the name without any errors.
```

### Step 2 — Choose a Region, and Say Why

Pick a region on the Basics screen. Each option describes a trade-off (latency, capacity). Record your choice and one sentence of reasoning — professionals never pick a region at random.

Your region and your reasoning:

```
I selected Foundry Central because it is the closest datacenter and offers the lowest latency. This should provide a more responsive connection when accessing and managing my virtual machine during cybersecurity lab exercises.
```

### Step 3 — Choose Your Guest OS

Pick an operating system and record why. There's no wrong answer, but there is a *reasoned* answer — think about which shell you'd rather manage it with, and what the license fee note tells you.

Your OS choice and reasoning:

```
I selected Ubuntu Server 22.04 LTS because I want to continue developing my Linux and Bash command-line skills from the previous labs. Ubuntu is commonly used in cloud environments and does not require an additional operating system license fee, making it a cost-effective choice for my cybersecurity training VM.
```

### Step 4 — Size It, and Do the Money Math

Pick a size tier. Record its specs and hourly rate, then do Lesson 4's monthly reflex: hourly rate × 24 × 30. Would you leave this machine running for a month?

Your size tier, its specs, and its hourly rate:

```
I selected the B2s tier, which provides 2 vCPUs, 4 GB of RAM, and 64 GB of disk storage at a rate of $0.046 per hour. This size is recommended for the course's lab workloads and provides a reasonable balance between performance and cost.
```

Your monthly math (rate × 24 × 30):

```
At $0.046 per hour, the estimated cost of running the B2s VM continuously for 30 days would be $0.046 × 24 × 30 = $33.12. I would not leave the VM running for an entire month if I only needed it for occasional lab exercises, because that would create unnecessary costs. I would stop or deallocate it when not in use and delete resources when they are no longer needed.
```

### Step 5 — Create the Admin Account

Create the administrator username and password. The simulator blocks guessable usernames and refuses weak passwords — if it pushes back, record what it rejected and what you learned from the rejection.

What (if anything) got rejected, and your final username (never record the password):

```
I created an administrator account with the username `soc-operator01`. The username met the simulator's naming requirements, and I used a password that satisfied its complexity requirements. My credentials were accepted, and I did not record the password in my worksheet.
```

### Step 6 — Capture Screenshot 1 (REQUIRED — Deliverable 1)

On the Review & Create screen — before you click Create — take the screenshot the simulator prompts for: your full configuration summary, including the total hourly cost. Name it exactly **`vm-config-summary.png`**. Upload instructions are in the GitHub Commit section.

---

## Part B — Survive Provisioning

### Step 1 — Create, and Read What Happens

Click **Create Virtual Machine** and watch the provisioning stages. Depending on your Part A choices, provisioning may fail with a readable error — **QuotaExceeded** (your size is bigger than the subscription allows) or **AllocationFailed** (your region ran out of capacity). If it fails: read the error, identify which wizard choice it points at, fix *that one thing*, and retry.

What happened on your first Create attempt (success, or the exact error name):

```
My first provisioning attempt was successful. The VM `soc-lab-vm-01` was created in Foundry Central, and Ubuntu Server 22.04 LTS booted successfully. The simulator confirmed that billing started at $0.046 per hour.
```

If you hit an error: what it told you, and what you changed:

```
No error. The VM was successfully provisioned on the first attempt, so no configuration changes were necessary.
```

### Step 2 — Confirm You're Running

Once provisioning completes, confirm on the dashboard: status **Running**, and the billing meter ticking at the rate your size card promised. Record the rate the meter shows.

The running rate shown on your dashboard:

```
$0.046/hr
```

---

## Part C — Run the Full Lifecycle

Complete all four lifecycle tasks on the dashboard, in this order, and answer the simulator's Concept Checks as they appear.

### Step 1 — Stop, and Watch the Meter

Stop (deallocate) your VM. Watch what happens to the billing rate — it should not go to zero. Record the stopped rate and what it's paying for.

The stopped rate, and what a stopped VM still pays for:

```
After stopping and deallocating my VM, the billing rate dropped from $0.046 per hour to $0.002 per hour. The VM no longer uses billable CPU and RAM resources, but its virtual disk still exists and continues generating storage charges even while the machine is powered off.
```

### Step 2 — Start It Again

Start the VM and confirm the full rate resumes. One sentence: where did your files go while it was stopped?

Your one-sentence answer:

```
My files remained stored on the VM's virtual disk while the machine was stopped. When I restarted the VM, the operating system and saved files were still available because stopping and deallocating the machine did not delete its storage.
```

### Step 3 — Take a Snapshot

Take a snapshot and record its name from the snapshot list. One sentence: what exactly did you just photograph, and when would you be glad you have it?

Snapshot name and your one-sentence explanation:

```
I created a snapshot named `snapshot-1` while my VM was running. The simulator confirmed that it captured a copy of the VM's current state at 13:07:46. Snapshots provide a recovery point that can be used to restore a VM to an earlier state if a configuration change or software installation causes problems.
```

### Step 4 — Capture Screenshot 2 (REQUIRED — Deliverable 1)

With your VM **Running** and at least one snapshot visible, take the dashboard screenshot. Name it exactly **`vm-dashboard-running.png`**.

### Step 5 — Delete, and Read the Warning

Delete your VM. Read the confirmation dialog before you click — record what it warns you is about to happen, then confirm and record your final total cost from the completion banner.

What the delete warning said, in your own words:

```
After deleting `soc-lab-vm-01`, the simulator changed its status to Deleted and reduced the billing rate to $0.000 per hour. The activity log confirmed that the virtual disk was destroyed and all billing stopped. My final simulated cost was $22.10 after 598 simulated hours. This demonstrated why deleting unused cloud resources is important for preventing unnecessary charges.
```

Your final simulated cost:

```
$22.10
```

---

## Analysis Questions

**Analysis Question 1.** Your stopped VM kept billing a small amount. Explain the "locker fee" in your own words — what physical thing still exists when a VM is stopped, and why is deletion the only true zero? *(Minimum 2 sentences.)*

```
Even when a VM is stopped, its virtual disk still occupies storage space on the cloud provider's physical infrastructure. This is similar to paying for a storage locker even when you're not actively using what's inside. In my simulation, stopping the VM reduced the cost to $0.002 per hour, but deleting it removed the disk and stopped all billing. This showed me why properly cleaning up unused cloud resources is important for controlling costs.
```

**Analysis Question 2.** Lesson 4 revealed that your real Weeks 6–12 lab machines are stamped from golden snapshots your instructor built. Using what you did in Part C, Step 3, explain how a golden snapshot works and why it means every student's machine starts identical. *(Minimum 3 sentences.)*

```
A golden snapshot is a saved reference state of a virtual machine that has already been configured and tested. In this lab, I created `snapshot-1` to preserve my VM's current state, which helped me understand how snapshots can be used for recovery and consistency. For the upcoming labs, the instructor can use a prepared golden image to create separate VMs with the same operating system, software, and initial settings. This ensures every student begins with a consistent working environment, reducing setup errors and making troubleshooting easier.
```

**Analysis Question 3.** If you hit a provisioning error in Part B (or even if you didn't): why do you think this lab *wants* you to encounter errors in a simulator before Week 6 hands you real infrastructure? *(Minimum 2 sentences.)*

```
I think the simulator is designed to help students become comfortable identifying and troubleshooting errors before working with real cloud infrastructure. Although my VM provisioned successfully on the first attempt, the lab showed how issues such as unavailable names, insufficient resources, or region capacity limits can affect deployment. Practicing these situations in a simulated environment helps build troubleshooting skills without risking real systems, data, or unexpected charges.
```

**Analysis Question 4.** Defend your Part A size choice to an imaginary manager watching the budget: why was your tier the right rent for this job, and what would have made you pick a bigger or smaller one? *(Minimum 2 sentences.)*

```
I selected the B2s tier because its 2 vCPUs, 4 GB of RAM, and 64 GB of storage provided the resources recommended for the course's lab exercises at a reasonable cost of $0.046 per hour. A larger VM would have increased expenses without providing a clear benefit for this workload. I would consider a smaller tier for very lightweight tasks that required fewer resources, or a larger tier if I needed to run multiple security tools, process larger datasets, or support more demanding applications. My goal would be to choose enough resources for reliable performance without paying for capacity I didn't need.
```

---

## Submission Checklist

- [x] VM named within the rules, taken-name error handled if encountered (Part A, Step 1)

- [x] Region chosen with recorded reasoning (Part A, Step 2)

- [x] Guest OS chosen with recorded reasoning (Part A, Step 3)

- [x] Size tier recorded with hourly rate and monthly math (Part A, Step 4)

- [x] Admin account created; any rejections recorded — password NOT written anywhere (Part A, Step 5)

- [x] **REQUIRED:** `vm-config-summary.png` captured at the Review screen (Part A, Step 6)

- [x] First Create attempt recorded — success or exact error + fix (Part B)

- [x] Stop / start / snapshot completed with meter observations recorded (Part C, Steps 1–3)

- [x] **REQUIRED:** `vm-dashboard-running.png` captured with VM running + snapshot visible (Part C, Step 4)

- [x] VM deleted; warning paraphrased and final cost recorded (Part C, Step 5)

- [x] All four Concept Checks passed in the simulator

- [x] All four Analysis Questions answered (minimum sentence counts met)

- [x] This file is committed to your portfolio repo at `week-04/labs/lab-03-vm-builder.md`

---

## GitHub Commit Subsection — ★ Deliverable 1

This lab completes **Deliverable 1: VM concepts + CLI screenshots**. Two things get committed:

**1. This worksheet, via the Lab Portal:**

1. Go to the CyberFoundations Lab Portal and sign in.
2. Open **Week 4 → Lab 03: Build Your First Virtual Machine**.
3. Fill in the worksheet fields and click **Submit to GitHub**. The Portal commits the completed file to `week-04/labs/lab-03-vm-builder.md`.

**2. Your four Deliverable 1 screenshots, uploaded to `assets/screenshots/week-04/`:**

| Screenshot | From | Filename |
|---|---|---|
| Permissions audit | Lab 01 | `cli-permissions-audit.png` |
| Archive investigation | Lab 02 | `cli-search-investigation.png` |
| VM configuration summary | Lab 03, Part A | `vm-config-summary.png` |
| VM dashboard, running + snapshot | Lab 03, Part C | `vm-dashboard-running.png` |

For each: on GitHub.com, navigate to `assets/screenshots/week-04/`, click **Add file → Upload files**, drag the image in (exact filenames above — lowercase, hyphens, no spaces), and **Commit changes**. Then open each uploaded image, right-click directly on it, choose **Copy image address** (Chrome/Edge) or **Copy Image Link** (Firefox), and paste the two VM links into the embeds below:

![VM configuration summary](https://raw.githubusercontent.com/sikeyaka/Siri-Keyaka-cyberfoundations-portfolio/7fbe40d2baacdac0a35bd8895f7d2ed8c7869187/assets/screenshots/week-04/vm-config-summary.png)

![VM dashboard — running, with snapshot](https://raw.githubusercontent.com/sikeyaka/Siri-Keyaka-cyberfoundations-portfolio/7fbe40d2baacdac0a35bd8895f7d2ed8c7869187/assets/screenshots/week-04/vm-dashboard-running.png)

**If right-click doesn't show that option:** click the small download-arrow icon in the top-right of the image preview instead, then copy the URL from your browser's address bar.

**Commit message tip (from Lesson 4):** when GitHub asks for a commit message on your uploads, write one that says what the work is — *"Add Deliverable 1: VM lifecycle and CLI evidence"* — not "stuff." An employer reading your repo sees discipline in details like that.

---

*CyberVisionaries Institute · Cyber Foundations · Tier I*
