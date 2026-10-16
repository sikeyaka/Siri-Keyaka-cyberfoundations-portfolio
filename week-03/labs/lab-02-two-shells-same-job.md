# Week 3 Lab 02 — Two Shells, Same Job: Incident Response Edition (CLI Simulator)

**Student Name:** Siri Keyaka

**Date Completed:** 08 October 2026

**Module:** 1 — Digital Infrastructure & CLI | **Week:** 3  

---

## Overview


This lab explores command-line investigation techniques using Bash and PowerShell in a simulated incident response scenario. The exercise involves investigating a potential unauthorized access attempt within the Foundry District Storeroom, examining an access log, and creating backup copies of investigation notes.

The same investigation is performed in both shells to compare command syntax, output formatting, and file management operations. The exercise reinforces the importance of documenting findings and verifying file locations during security investigations.

## Lab Environment

| Component | Details |
| --- | --- |
| Environment | CyberFoundations CLI Simulator |
| Shells Used | Bash and PowerShell |
| Exercise | Foundry District Storeroom |
| Scenario | Potential unauthorized file access |
| Focus | File system investigation, log inspection, documentation, and file backups |

---

## Part A — The Bash Pass

Use the **Foundry District Storeroom — Bash** box. Every challenge starts from a prepared setup, so check your location at the start of each one. Record your commands and output exactly as they appear.

### Step A1 — Verify Your Starting Location

**Bash Challenge 1.** Run the command to print your current working directory. You should start in `/home/agent`.

Command you ran:

```
pwd
```

Output:

```
/home/agent
```

### Step A2 — Look Around the Directory

**Bash Challenge 2.** List the contents of your current location to spot any files or folders. You should see an `archive` folder and a `README.txt` file.

Command you ran:

```
ls
```

Output:

```
README.txt  archive
```

### Step A3 — Move Deeper into the Storeroom

**Bash Challenge 3.** This challenge starts in `/home/agent`. Move into the flagged incident folder, `/home/agent/archive/incident-42`. From `/home/agent` you can type `cd archive/incident-42`.

Command you ran:

```
cd archive/incident-42
```

**\*\*Location Verification\*\***

Command you ran:

```
pwd
```

Output:

```
/home/agent/archive/incident-42

```

### Step A4 — Inspect the Incident Log File

**Bash Challenge 4.** This challenge starts inside `/home/agent/archive/incident-42`. The incident log is `access-log.txt`. Print its contents to the screen with `cat`.

Command you ran:

```
cat access-log.txt
```

Output:

```
Access Log - Incident 42
03:14 - Unknown login attempt, storeroom bay 3.
03:16 - Access denied.
03:17 - Alert raised to on-call.
```

### Step A5 — Create Your Investigation Note

**Bash Challenge 5.** This challenge starts inside `/home/agent/archive/incident-42`. Investigators document as they go. Create a new, empty file right here called `investigation-notes.txt` to hold your findings.

Command you ran:

```
touch investigation-notes.txt
```

### Step A6 — Back Up Your Note

**Bash Challenge 6.** This challenge starts inside `/home/agent/archive/incident-42`, and `investigation-notes.txt` is already prepared there for you. Make a backup copy called `investigation-notes-backup.txt` with `cp` (copy, not move), then run `ls` in the same challenge to see both files.

Command you ran:

```
cp investigation-notes.txt investigation-notes-backup.txt
```

Confirm both files now exist:

```
access-log.txt  investigation-notes-backup.txt  investigation-notes.txt
```

---

## Part B — The PowerShell Pass

Now use the **Foundry District Storeroom — PowerShell** box. It has its own equivalent copy of the same practice files, with the same Linux-style paths. **Target the same folder and file as Part A:** `/home/agent/archive/incident-42` and `access-log.txt`. The notes files you made in Part A are not in this box — you will create them again here.

### Step B1 — Verify Your Starting Location

**PowerShell Challenge 1.** Run the PowerShell command to print your current location (`Get-Location`). You should start in `/home/agent`.

Command you ran:

```
Get-Location
```

Output:

```
/home/agent
```

### Step B2 — Look Around the Directory

**PowerShell Challenge 2.** List the contents of your current location (`Get-ChildItem` or `dir`).

Command you ran:

```
Get-ChildItem
```

Output:

```
Mode                 Name
d-----               archive
-a----               README.txt
```

### Step B3 — Move Deeper into the Storeroom

**PowerShell Challenge 3.** This challenge starts in `/home/agent`. Move into the **same folder** as Part A, `/home/agent/archive/incident-42` — for example `Set-Location archive/incident-42`.

Command you ran:

```
Set-Location archive/incident-42
```

**\*\*Location Verification\*\***

Command you ran:

```
Get-Location
```

Output:

```
/home/agent/archive/incident-42
```

### Step B4 — Inspect the Incident Log File

**PowerShell Challenge 4.** This challenge starts inside `/home/agent/archive/incident-42`. Print the contents of the same file you read in Part A, `access-log.txt`, with `Get-Content` (or `type`).

Command you ran:

```
Get-Content access-log.txt
```

Output:

```
Access Log - Incident 42
03:14 - Unknown login attempt, storeroom bay 3.
03:16 - Access denied.
03:17 - Alert raised to on-call.
```

### Step B5 — Create Your Investigation Note

**PowerShell Challenge 5.** This challenge starts inside `/home/agent/archive/incident-42`. Create the **same-named** empty file, `investigation-notes.txt`, right here with `New-Item`.

Command you ran:

```
New-Item investigation-notes.txt -ItemType File
```

### Step B6 — Back Up Your Note

**PowerShell Challenge 6.** `investigation-notes.txt` is already prepared in `/home/agent/archive/incident-42`. Make a backup copy called `investigation-notes-backup.txt` with `Copy-Item`, same as you did in Part A, then run `dir` in the same challenge to see both files.

Command you ran:

```
Copy-Item investigation-notes.txt investigation-notes-backup.txt
```

Confirm both files now exist:

```
Mode                 Name
-a----               access-log.txt
-a----               investigation-notes-backup.txt
-a----               investigation-notes.txt
```

---

## Part C — Side-by-Side Comparison (Spot the Difference)

### Step C1 — The Command Comparison Table


| Task / Question | Bash Command (Bash Pass) | PowerShell Command (PowerShell Pass) |
| --- | --- | --- |
| 1. Where am I? | pwd	 | Get-Location |
| 2. Look around | ls | Get-ChildItem |
| 3. Move into a folder | cd archive/incident-42 | Set-Location archive/incident-42 |
| 4. Peek inside a file | cat access-log.txt | Get-Content access-log.txt |
| 5. Create + back up your note | touch investigation-notes.txt; cp investigation-notes.txt investigation-notes-backup.txt | New-Item investigation-notes.txt -ItemType File; Copy-Item investigation-notes.txt investigation-notes-backup.txt |

### Step C2 — Output Differences Reflection

Describe at least one difference in how the two shells presented information to you (e.g., column layout, text colors, file details, folder headers). Minimum 2 sentences.

```
One difference I noticed was that Bash displayed the file and folder names in a simple list when I used `ls`, while PowerShell displayed them in columns with additional information, such as `Mode` and `Name`, when I used `Get-ChildItem`. I also noticed that the PowerShell terminal prompt started with `PS`, while the Bash prompt included the username and machine name. 
```

---

## 🧠 Analysis Questions

### Analysis Question 1 — The Identical Tree

Both passes used equivalent practice datasets with the same Linux-style layout, even though you typed different commands. How do you know the folders and files matched? Point to concrete evidence from your terminal outputs (e.g., matching paths, folder names, or file content). Minimum 3 sentences.

```
I know both shells used the same folder structure because `pwd` in Bash and `Get-Location` in PowerShell both showed `/home/agent` as the starting location. After navigating into the incident folder, both commands confirmed the same path: `/home/agent/archive/incident-42`. Both shells also displayed the same `access-log.txt` contents, including the unknown login attempt at 03:14, access denied at 03:16, and the alert raised at 03:17. This confirmed that I was working with equivalent files and folders in both environments.
```

### Analysis Question 2 — Syntax Preferences

Which command pair (e.g., pwd vs. Get-Location, ls vs. dir, cat vs. type) felt most different to you? Give a specific reason why one felt more comfortable or intuitive than the other. Minimum 3 sentences.

```
The command pair that felt most different to me was `ls` in Bash compared to `Get-ChildItem` in PowerShell. I found `ls` more comfortable because it was shorter, easier to remember, and quicker to type. Although `Get-ChildItem` is more descriptive and makes its purpose clearer, I prefer the simplicity of the Bash command. 
```

### Analysis Question 3 — Applying Lesson 2 Differences

In this simulator, both boxes use the same Linux-style paths (like `/home/agent`) — PowerShell also runs on Linux, so you did not see drive letters such as `C:\`. If the simulator accepted a backslash in a path, that is a typing convenience, not a sign of a Windows file system. First, describe what you actually observed that was different between the bash and PowerShell commands or output. Then explain one Windows-vs-Linux difference from Lesson 2 (such as slash styles, case-sensitivity, or drive letters) and what it would look like on a real Windows computer. Minimum 3 sentences.

```
One difference I observed was that Bash used shorter commands like `pwd`, `ls`, and `cat`, while PowerShell used longer commands like `Get-Location`, `Get-ChildItem`, and `Get-Content`. I also noticed that PowerShell displayed additional file information in columns, while Bash showed a simpler list of filenames. Both simulators used Linux-style paths with forward slashes, such as `/home/agent/archive/incident-42`. From Lesson 2, I learned that Windows commonly uses drive letters and backslashes in file paths, so on a real Windows computer, a similar folder path might look like `C:\Users\agent\archive\incident-42` instead.
```

---

## Lab Summary

Completed equivalent investigation tasks in Bash and PowerShell, including navigating directories, examining an access log, creating investigation notes, and backing up files.

The exercise demonstrated how different command-line tools can accomplish the same investigative objectives while presenting information through different command syntax and output formats.

---

*CyberVisionaries Institute | CyberFoundations | Week 3*
