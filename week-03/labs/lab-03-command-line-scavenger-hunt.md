# Week 3 Lab 03 — Command Line Scavenger Hunt (CLI Simulator)

**Student Name:** Siri Keyaka

**Date Completed:** 08 October 2026

**Module:** 1 — Digital Infrastructure & CLI | **Week:** 3  

---

## Overview

This lab focuses on independently navigating a simulated file system to locate, inspect, and organize files within the Foundry District Archive Room.

Using Bash commands, the exercise involves locating three files across multiple directories, examining their contents, organizing them into a designated folder, and consulting command documentation when needed. The activities reinforce file system navigation, troubleshooting, and information management skills applicable to cybersecurity investigations and system administration.

## Lab Environment

| Component | Details |
| --- | --- |
| Environment | CyberFoundations CLI Simulator |
| Shell Used | Bash |
| Exercise | Foundry District Archive Room |
| Focus | Directory navigation, file inspection, file organization, and command documentation |
| Challenges | 8 |

---

## Part A — The Hunt

Find all three of the following, hidden at different depths in the Archive Room tree:

- A file related to a **shift log**
- A file related to a **maintenance note**
- A file related to a **supply inventory**


Shift log file — full path once found:

```
/home/archivist/operations/ops-log/shift-log.txt 
```

Maintenance note file — full path once found:

```
/home/archivist/records/records-2025/maintenance-note.txt
```

Supply inventory file — full path once found:

```
/home/archivist/records/records-2024/supply-inventory.txt 
```

---

## Part B — Read and Report

Shift log contents:

```
Shift Log - Foundry District Archive Room
07:00 - Archive opened, no incidents overnight.
15:00 - Routine filing complete.
```

Maintenance note contents:

```
Maintenance Note - Conveyor belt 3 serviced, next check due in 90 days.
```

Supply inventory contents:

```
Supply Inventory - Q4 2024
Gloves - 400 units
Masks - 250 units
Tape - 60 rolls
```

---

## Part C — Organize Your Findings

### Step 1 — Create a Sorted-Findings Folder


Command you ran:

```
mkdir sorted-findings
```

### Step 2 — Move All Three Files Into It

Commands you ran:

```
mv operations/ops-log/shift-log.txt sorted-findings/
mv records/records-2025/maintenance-note.txt sorted-findings/
mv records/records-2024/supply-inventory.txt sorted-findings/
```

### Step 3 — Confirm the Move


Command you ran:

```
ls sorted-findings
```

Output:

```
maintenance-note.txt  shift-log.txt  supply-inventory.txt
```

---

## Part D — When You Get Stuck

### Step 1 — Ask the Terminal


Command or term you looked up:

```
man chmod
```

What the help text (or the folder's contents) told you:

```
I learned that the `chmod` command changes file permissions and controls who can read, write, or run a file. The simulator also showed an example of using `chmod 755 file`.
```

### Step 2 — Describe a Wrong Turn

Everyone takes at least one wrong turn in a tree this size. Describe one moment you ended up somewhere unexpected, and how you used `pwd`/`Get-Location` and `cd ..` to recover.

```
While searching for the maintenance note, I first checked the `ops-notes` folder, but it only contained a break-room memo. I also tried navigating to `ops-logs` and received a "No such file or directory" error because I entered the wrong folder name. I used `cd ..` to return to the previous directory, continued exploring the folder structure, and eventually found the maintenance note inside `records/records-2025`.
```

---

## Analysis Questions

### Analysis Question 1

Which of the three files in Part A took the longest to find, and what was it about the tree's structure (depth, similarly-named folders, etc.) that made it harder?

```
The maintenance note took me the longest to find because I had to explore several folders before locating it. The directory structure included similarly named folders, such as `ops-log` and `ops-notes`, which made it easy to take a wrong turn. I initially searched under `operations` before realizing I needed to explore the `records` directory, where I eventually found the file inside `records-2025`.
```

### Analysis Question 2

Compare how you felt starting this lab to how you felt at the very start of Lesson 3A, looking at a blank blinking cursor for the first time. What changed?

```
At the beginning of Lesson 3A, the command line was unfamiliar, and I was still learning how to navigate directories. By the time I started this lab, I felt more comfortable entering commands and understanding what the terminal was showing me. I still made mistakes while navigating, but I was able to recognize when something wasn't working and find my way back. Completing the scavenger hunt helped me become more confident using the command line to locate and read files.
```

### Analysis Question 3

Week 4 moves from managing your own files to controlling who's allowed to do what to them — permissions — plus your first look at what a virtual machine is. Based on everything you've practiced this week, what's one thing you're curious about or looking forward to?

```
I'm looking forward to learning more about file permissions and how they help protect information in a system. Since cybersecurity involves controlling access to sensitive data, I'm interested in understanding how commands like `chmod` can be used to manage who is allowed to read, modify, or execute files.
```

---

## Lab Summary

Completed an independent file system investigation using Bash to locate and inspect three files within a nested directory structure. Organized the findings into a dedicated folder and verified the results using command-line tools.

The exercise strengthened practical navigation and troubleshooting skills, including recovering from incorrect directory paths and using command documentation to understand unfamiliar commands.

---

*CyberVisionaries Institute | CyberFoundations | Week 3*
