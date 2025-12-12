
# Windows Fundamentals (Part 1) - Tryhackme Notes

## Why I started with this
Before going deeper into SOC tools and logs, I wanted to properly understand how Windows works at a basic level.  
Since most organizations use Windows, it makes sense to know how users, files, and processes behave in a normal system.

These are my personal notes from completing **Windows Fundamentals – Part 1** on TryHackMe.



## How I now think about Windows
I used to think of Windows just as an operating system people use daily.  
After this module, I started seeing it as a system that constantly records activity — which is very useful for security monitoring.

Almost everything happening in Windows leaves some kind of trace.



## Users and accounts
- Windows uses user accounts to separate access between people.
- Each user has their own profile and permissions.
- Admin accounts are especially sensitive because they can do almost anything.
- From a security perspective, unusual login behavior should always be investigated.

This helped me understand why failed logins and account changes are such common SOC alerts.



## Groups and permissions
- Users are placed into groups, and groups define what users are allowed to do.
- I learned that attackers often try to abuse group membership instead of exploiting software.
- If a normal user suddenly becomes an admin, that’s a serious red flag.

This part made me realize how important permission monitoring is.



## Processes
- A process is basically a running program.
- Every time you open an application, a process is created.
- Malware can hide by pretending to be a normal process.
- Knowing what “normal” looks like makes it easier to spot something suspicious.

I also learned that processes often have parent-child relationships, which can reveal attacker behavior.



## Windows filesystem basics
- The main system drive is usually `C:\`.
- Important folders include:
  - `C:\Windows`
  - `C:\Users`
  - `C:\Program Files`
- Attackers often place files inside user folders or temporary locations.
- File location matters a lot during investigations.

I didn’t realize before how much context file paths can give during an incident.



## Why this matters for SOC work
This module helped me understand why Windows is such a big focus in SOC environments:
- Most alerts are related to user activity or processes.
- Knowing the basics makes later log analysis much easier.
- It builds the foundation for SIEM and detection work.





  _**Completed**: Dec 10, 2025_







---











# Windows Fundamentals (Part 2) - Tryhackme Notes

## Why this part was important to me
After learning the basics in Part 1, I wanted to understand how Windows actually records what’s happening on the system.  
This is where **Windows Fundamentals Part 2** becomes very relevant for SOC analysts.

Most real investigations rely on logs, not guesses.



## Windows event logs
- Windows keeps detailed records of system activity using event logs.
- These logs include:
  - Logins and logouts
  - Failed authentication attempts
  - Process execution
  - System and service changes
- These logs are often forwarded to SIEM platforms in real environments.

This made it clear why SOC analysts spend so much time looking at logs.



## Event Viewer
- Event Viewer is the built-in tool to view Windows logs.
- Logs are grouped into categories like:
  - Security
  - System
  - Application
- Security logs are especially important when investigating attacks.

I realized that understanding where logs come from is just as important as reading them.



## Processes and services (security angle)
- Services run in the background and often start automatically.
- Malware sometimes installs itself as a service to stay persistent.
- A service running under an unusual account should raise suspicion.

This part helped me connect Windows behavior to real attacker techniques.



## Windows registry (first exposure)
- The registry stores configuration data for the system and applications.
- Attackers frequently modify the registry to maintain persistence.
- Even small registry changes can indicate malicious activity.

At this stage, I don’t understand every registry key — but I now know *why* it matters.



## Why this matters for SOC and SIEM
- SIEM tools rely heavily on Windows event logs.
- Many detections are based on:
  - Event IDs
  - Authentication activity
  - Process creation
  - Service modifications
- Understanding Windows internals makes alerts less confusing.

This module helped me feel more confident about moving into SOC-level labs.



## What I plan to do next
- Complete Windows Fundamentals Part 3
- Practice checking logs directly using Event Viewer and PowerShell
- Start correlating Windows activity with MITRE ATT&CK techniques
- Apply this knowledge in SOC and SIEM exercises



  _**Completed**: Dec 11, 2025_






---
