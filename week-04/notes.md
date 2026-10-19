# Week 4 Notes — Permissions, Searching, and Virtual Machines

**Student Name:** Siri Keyaka

**Date Completed:** 19 October 2026

Summarize this week's key concepts in your own words — not copy-pasted definitions.

## Key Concepts This Week

- File permissions: read/write/execute × owner/group/other, and reading `ls -l`
- Changing permissions with `chmod` (symbolic and numeric) — and THE GATEKEEPER'S RULE
- Windows ACLs, read with `Get-Acl` (the real-world `icacls` tool does the same job, but is not available in the simulator)
- Wildcards (`*`, `?`, `[ ]`) and searching inside files with `grep`/`Select-String`
- Virtual machines: host vs. guest, the hypervisor, Type 1 vs. Type 2, isolation
- The VM lifecycle: create, start, stop (deallocate), snapshot, delete — and what each costs
- Golden snapshots — how your Weeks 6–12 lab machines are made

## In My Own Words

**Decode `-rw-r-----` audience by audience: who can do what to this file?**

```
The first character (`-`) indicates that this is a regular file. The owner has read and write permissions (`rw-`), meaning they can view and modify the file but cannot execute it. The group has read-only permission (`r--`), so group members can view the file but cannot modify or execute it. Other users have no permissions (`---`), meaning they cannot read, write, or execute the file.
```

**What is a hypervisor, and what are its two jobs?**

```
A hypervisor is software that allows multiple virtual machines to run on the same physical computer. Its two main jobs are resource management and isolation. It allocates hardware resources like CPU, RAM, and storage to each VM while keeping the virtual machines separated so they can operate independently without interfering with one another.
```

**A stopped VM still costs a little money. What is it paying for, and what's the only way to reach a true zero?**

```
A stopped and deallocated VM can still cost money because its virtual disk and stored data continue using cloud storage. Although the compute charges stop, storage charges remain. In our lab, stopping the VM reduced the cost from $0.046 to $0.002 per hour. To reach a true zero, we had to delete the VM and its disk, which brought the simulated cost down to $0.000 per hour.
```

---

## Submission Checklist

- [x] I summarized each concept in my own words, not copied definitions

- [x] I answered all three "In My Own Words" prompts

- [x] This file is committed to my portfolio repo at `week-04/notes.md`
