# Cyber Defence Frameworks (TryHackMe — SOC Level 1)

This module helped me understand **how defenders explain attacks** and how to **structure investigations** using well-known frameworks.
Instead of memorizing theory, I focused on: *What does this framework help me do as a SOC L1 analyst?*

---

## Rooms Covered (Module Checklist)

- ✅ Pyramid Of Pain  
- ✅ Cyber Kill Chain  
- ✅ Unified Kill Chain  
- ✅ MITRE  
- ✅ Summit  
- ✅ Eviction  

---

## 1) Pyramid Of Pain

### What it means (simple)
The Pyramid of Pain ranks indicators based on **how hard it is for an attacker to change them**.

### The main idea
- **Easy for attacker**: Hashes, IP addresses  
- **Medium**: Domains, network artifacts (like User-Agent, URI patterns)  
- **Hard**: Tools  
- **Hardest**: TTPs (Techniques, Tactics, Procedures — the attacker’s behavior)

### Why this matters in a SOC
Blocking an IP might stop *one* attempt, but attackers can quickly swap IPs.
Detecting **behavior** (TTPs) forces attackers to change how they operate, which is expensive.

### My practical takeaway
When I investigate something, I try to capture:
- quick IOCs (for fast blocking)
- AND the underlying behavior (for stronger detection rules)

---

## 2) Cyber Kill Chain

### What it is (simple)
A step-by-step model for how many attacks progress:
Recon → Weaponize → Deliver → Exploit → Install → C2 → Actions on Objectives

### Why it matters for SOC L1
It helps me answer:
- **Where are we in the attack?**
- **What evidence should exist at this stage?**
- **What should I check next?** (email logs, endpoint, proxy, firewall, etc.)

### What confused me at first (and how I fixed it)
Some stages (like weaponization) may not show up in logs at all.
So I focus on stages we can actually observe:
- Delivery/Exploitation (phish click, macro, suspicious process chain)
- Installation (persistence)
- C2 (outbound connections/beaconing)
- Actions (credential abuse, lateral movement, exfil)

---

## 3) Unified Kill Chain

### What it is (simple)
A more detailed, defender-friendly kill chain that expands the “middle” parts of an attack.

### Why it matters
The classic Kill Chain is good for the big picture, but Unified Kill Chain helps separate steps like:
- credential access
- privilege escalation
- persistence
- discovery
- lateral movement

### SOC mindset takeaway
Unified Kill Chain makes my timelines cleaner because it forces me to identify:
**what changed**, **how access was maintained**, and **how the attacker moved**.

---

## 4) MITRE

### What it is (simple)
MITRE provides resources that help defenders describe and track adversary behavior.
The big value for SOC work is **ATT&CK**: tactics (goals) and techniques (how they do it).

### Why it matters in investigations
It helps me:
- name what I’m seeing in a professional way
- map evidence to known techniques
- think about what logs/telemetry should confirm it
- suggest better detections

### Example mindset (not tool-specific)
Instead of writing:
> “Suspicious PowerShell happened”

I can write:
> “Suspicious command execution consistent with ATT&CK-style execution behavior (needs validation via process + parent + user + network context).”

---

## 5) Summit (Simulation Room)

### What I practiced
This room felt like applying the Pyramid of Pain in a “chase the adversary” scenario:
- identify indicators
- understand how quickly attackers can adapt
- push detection up the pyramid toward stronger signals

### SOC mindset takeaway
The best defenders don’t just block one thing.
They improve detection so the attacker must change **tools/techniques**, not just infrastructure.

---

## 6) Eviction (Investigation-Style Room)

### What I practiced
This room felt more like a defensive investigation:
- follow clues
- build a story from evidence
- identify the “monster under the bed” (hidden malicious activity)

### SOC mindset takeaway
Even in a simulated setting, the workflow is the same:
**collect evidence → build timeline → decide impact → document → recommend next steps**

---

# My Quick Framework Map (How I use these together)

- **Pyramid of Pain** → Helps prioritize *stronger detections* (hurt attacker more)
- **Kill Chain / Unified Kill Chain** → Helps build *attack timeline* and decide what to check next
- **MITRE resources** → Helps label behavior, communicate clearly, and guide detection ideas
- **Summit/Eviction** → Practice applying theory like a SOC investigation

---

# Mini SOC Ticket Template (My Practice Format)

**Title:**  
**Time Window:**  
**Host/User:**  
**Summary (2–3 lines):**  

**Evidence (bullets):**
-  
-  
-  

**Mapping (optional):**
- Kill Chain Stage:  
- ATT&CK / Technique idea:  

**Assessment:** Benign / Suspicious / Escalate  
**Next Steps:**  

---

# Next Practice Goals (After this module)

- Write 2–3 short case notes where I map evidence to:
  - Kill Chain stage + why
  - one “higher pyramid” indicator (artifact or behavior)
- Practice explaining one case aloud (SOC handoff style) in 60 seconds
