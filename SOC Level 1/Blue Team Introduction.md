# Junior Security Analyst Intro 

## Why I did this room
I’m working toward a SOC Analyst (Tier 1) role, so I wanted a clear picture of what a junior analyst actually does day-to-day. This room felt like a good “reality check” before going deeper into tools and labs.



## What I learned (in my own words)

### What a Junior SOC Analyst really does
A junior analyst is usually the first person to look at alerts. The job is less about “hacking” and more about:
- noticing what looks unusual
- checking logs and basic evidence
- deciding if an alert is real or just noise
- documenting what happened clearly

### The workflow mindset matters
A big takeaway for me was that SOC work is a process:
1) Alert comes in  
2) Triage (quick decision: ignore / investigate)  
3) Investigation (logs, endpoints, network clues)  
4) Escalate if needed  
5) Document the outcome  

Even if your technical skills are improving, you still need this workflow thinking.

### Documentation is part of the job
This room reminded me that writing is not optional in SOC work. Even a simple case needs a short, clear summary:
- what you saw
- why you think it’s normal or suspicious
- what you checked
- what you did next

That’s something I’m practicing in my Windows event log notes too.



## What I’m focusing on next
To match what this room described, I want to keep building skills in:
- Windows event logs (4624 / 4625 / 4688)
- Basic network traffic understanding (DNS, TCP handshakes, retransmissions)
- Writing short “mini SOC ticket” conclusions after investigations



## Quick reflection
This room made SOC work feel more realistic for me. It’s not about being perfect — it’s about being consistent, careful, and able to explain what happened.








---









# SOC Role in Blue Team

## Why I did this room
I wanted to understand the SOC role from the blue team side — not just tools, but responsibilities. I’m trying to build the habit of thinking like a defender: detect, verify, respond, and communicate.



## What I learned (in my own words)

### SOC is not one job — it’s a team function
The room helped me understand that “SOC analyst” can mean different levels of responsibility, but the common goal is the same:
- detect threats early
- reduce risk
- respond quickly and correctly

### The blue team focus is visibility + response
A big difference I noticed is that blue team work depends on visibility:
- logs (Windows, Linux, network devices)
- alerts (SIEM/EDR)
- context (asset value, user behavior, time patterns)

Without logs and context, you can’t make a good decision.

### What matters most in SOC investigations
The room pushed a mindset I’m trying to develop:
- Don’t panic over one event
- Look for patterns (repeated attempts, abnormal timing, unusual processes)
- Correlate evidence (logs + network + endpoint)
- Make a clear conclusion, even if it’s “likely benign”

### Escalation is a skill
A junior analyst doesn’t handle everything alone. Part of the job is knowing when to escalate:
- high severity indicators
- confirmed malicious activity
- unclear but risky behavior



## How this connects to what I’m doing
This room fits perfectly with what I’m practicing:
- Windows logs: spotting failed logons, service logons, process creation
- Wireshark: understanding what “normal traffic” looks like
- Writing short investigation notes so I can explain evidence clearly



## Quick reflection
This room reinforced one thing for me:
SOC work is not about knowing everything — it’s about following a process, staying calm, and being able to explain your decision with evidence.





---





# Human as Attack Vectors 

## What I understood after this room
This room made one thing very clear: attackers don’t always “hack systems” first — they often **hack people** first. If they can influence a decision (click, trust, share, approve), they can bypass a lot of security controls.

## Common human-based attack methods
- **Phishing**: fake messages that push you to click, open, or login
- **Spear phishing**: phishing that’s personalized (more convincing)
- **Vishing / Smishing**: phone calls / SMS used to steal info or push actions
- **Pretexting**: pretending to be IT/HR/bank/vendor to create urgency
- **Baiting**: “free” files, cracked software, USB drops, giveaways
- **Tailgating**: physical access by following someone into a restricted area

## What attackers usually want
- Credentials (passwords, MFA codes, session tokens)
- Money transfers / invoice changes (BEC)
- Access to internal tools (VPN, email, helpdesk, Slack/Teams)
- A foothold to move deeper (lateral movement)

## SOC signals I’d watch for
- Login success after unusual failures (4625 → 4624 patterns)
- New sign-ins from unusual IPs/devices/locations
- New mailbox rules/forwarding, suspicious OAuth consent
- Unusual password reset activity or MFA prompt fatigue reports
- User reports like “I clicked a link” or “someone called from IT” (treat as high-signal)

## Defenses that actually help
- Security awareness that teaches real examples (not just theory)
- Strong MFA (prefer phishing-resistant options when possible)
- Email protections (SPF/DKIM/DMARC, safe links, attachment scanning)
- Clear verification rules for sensitive requests (finance, IT, HR)
- Easy reporting path for suspicious messages (button + fast response)

## My takeaway
People make mistakes — that’s normal. SOC work is about reducing damage when it happens, spotting the early signals, and helping the organization learn without blaming the victim.




---





# System as Attack Vectors

## What I understood after this room
This room reminded me that systems don’t need “zero-days” to get breached. A lot of compromises happen because of **misconfigurations, weak controls, and unpatched software**. Attackers love predictable weaknesses.

## System-side attack vectors (high level)
- **Unpatched vulnerabilities** in OS/apps/services
- **Weak authentication** (weak passwords, exposed RDP/SSH, no MFA)
- **Misconfigurations** (open ports, default credentials, unsafe permissions)
- **Exposed services** (databases, admin panels, remote management)
- **Poor access control** (users with too much privilege)
- **Insecure software / scripts** running in the environment
- **Lack of visibility** (no logging, no alerts, no endpoint monitoring)

## What a SOC analyst should look for
- Suspicious external connections to critical ports (RDP/SMB/SSH)
- Repeated auth failures followed by success (spray/brute force behavior)
- New admin users or privilege changes (4720/4732/4672 indicators)
- New scheduled tasks/services or persistence artifacts
- Strange parent/child process chains (PowerShell → cmd → downloads/execution)
- Lateral movement signals (new logons to multiple hosts, new remote sessions)

## Why “privilege” matters
If an attacker gets a normal user, they often try to upgrade to admin:
- Find stored credentials
- Abuse misconfigurations
- Exploit local vulnerabilities
- Move laterally to higher-value machines

## Defensive habits that reduce real risk
- Patch management (prioritize internet-facing + high severity)
- Reduce attack surface (close ports, disable unused services)
- Least privilege (users don’t need admin rights by default)
- Strong logging (Windows Security logs, Sysmon, SIEM forwarding)
- Baselines (know what “normal” processes and connections look like)
- Hardening + monitoring for persistence points (tasks, services, run keys)

## My takeaway
“System as attack vector” is basically: if we leave doors open, someone will try them. The SOC job is to notice the patterns early, validate what’s real, and help close the gaps before they become incidents.
