# Junior Security Analyst Intro — (TryHackMe)

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









# SOC Role in Blue Team — (TryHackMe)

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
