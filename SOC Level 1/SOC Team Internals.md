# SOC L1: Alert Triage (Room Notes)

## What I worked on
This room felt like “first contact” with a SOC alert. The main goal wasn’t to be perfect — it was to build a repeatable way to go from **alert → evidence → decision**.

## The mindset I practiced
When an alert pops up, the first question is not “is it malware?”
It’s usually:

- What exactly triggered this alert?
- Is it a real event or noise?
- If it’s real, how bad is it and what should I do next?

## My triage flow (simple version)
This is the process I tried to follow during the room:

1) **Read the alert fields carefully**
   - Source / destination
   - Username / host
   - Timestamp
   - Trigger rule (what the system thinks happened)

2) **Confirm context**
   - Is this normal for this user/host?
   - Is this internal traffic or external?
   - Does the timing make sense?

3) **Pivot to supporting evidence**
   - Logs around the same time
   - Related network connections
   - Other alerts for the same machine/user

4) **Decide**
   - Benign / false positive
   - Suspicious but not confirmed
   - Confirmed incident

## What I learned (practical)
- “Triage” is basically fast decision-making with limited data.
- Most alerts are not dramatic — they’re small signals that need validation.
- Good triage depends on **asking the right questions**, not guessing.

## Output / takeaway
After this room, I feel more comfortable with the idea that a SOC analyst is not a “hacker” role — it’s a **structured investigation** role.

---

# SOC L1: Alert Reporting (Room Notes)

## What I worked on
This room focused on something that sounds simple but is actually a core SOC skill:
**writing a clean, useful incident/alert report.**

An alert report is basically how you communicate the investigation to:
- your team
- your senior analyst
- your manager
- or the next shift

## What “good reporting” means (what I practiced)
A good report should answer these without extra noise:

- What happened?
- When did it happen?
- Where did it happen (host/user/IP)?
- How do we know (evidence)?
- How serious is it?
- What action was taken (or recommended)?

## My reporting structure (template I’m using)
I tried to keep my notes in this structure:

### 1) Summary
One short paragraph describing the alert and why it matters.

### 2) Key details
- Host:
- User:
- Source IP:
- Destination IP/domain:
- Time window:

### 3) Evidence
- Which log entries / fields supported the conclusion
- Any related events found during pivots

### 4) Assessment
- False positive / benign
- Suspicious
- Confirmed malicious
And why.

### 5) Next steps
- Monitor
- Escalate
- Block / contain
- Reset password / isolate host (depending on scenario)

## What I learned (practical)
- Reporting is not about writing long text — it’s about being clear and traceable.
- If someone can’t reproduce my conclusion from my evidence, the report is weak.
- A strong report saves time for the whole SOC team.

---

# SOC Workbook & Lookups (Room Notes)

## What I worked on
This room was about building a SOC habit:
**don’t rely on memory — rely on lookups and documentation.**

In a real SOC you constantly look up:
- IP reputation
- domain reputation
- hashes
- CVEs
- MITRE technique mapping
- internal baselines (what’s normal in your network)

So this room felt like training that “lookup reflex”.

## My “lookup mindset”
Instead of guessing, I tried to do this:

1) Take the indicator (IP / domain / hash / username)
2) Check if it’s known bad or suspicious
3) Compare it to the alert story and timeline
4) Decide how much confidence I have

## What the workbook idea taught me
The workbook is basically a personal SOC memory:
- how to investigate common alert types
- which data sources to check first
- which questions to ask every time

Even for beginners, this matters because it prevents the “I forgot everything” problem.

## What I learned (practical)
- Lookups don’t give the final answer — they help raise or lower confidence.
- A single “bad reputation” result is not proof by itself.
- The best way to improve fast is to keep repeating the same investigation pattern and documenting it.

## Output / takeaway
My biggest takeaway from this room:
**SOC work becomes easier when you build a routine — not when you try to memorize everything.**






---






# SOC Metrics & Objectives (Room Notes)

## Why this room mattered to me

Before this room, I thought SOC work was mostly about **finding alerts and reacting fast**.  
This lab helped me realize something important:  
a SOC is also measured, evaluated, and improved using **metrics** — not guesses.

If you can’t measure how your SOC performs, you can’t prove value or improve response.



## What are SOC Metrics (in simple words)

SOC metrics are **numbers that explain how well a SOC is doing**.

They help answer questions like:
- Are we detecting attacks fast enough?
- Are analysts overwhelmed with false alerts?
- Are incidents being resolved properly?
- Is security actually improving over time?

Metrics turn SOC work into **data-driven decisions** instead of opinions.



## Key SOC Metrics I Learned

### 1. Mean Time To Detect (MTTD)
- How long it takes to **notice** an incident after it starts
- Lower MTTD = better detection

Example:
If an attack starts at 10:00 and SOC notices at 10:15 → MTTD = 15 minutes



### 2. Mean Time To Respond (MTTR)
- How long it takes to **contain or remediate** an incident
- Measures response efficiency

Example:
Alert detected at 10:15, resolved at 10:45 → MTTR = 30 minutes



### 3. Alert Volume
- Total number of alerts generated
- High volume ≠ good security

Too many alerts usually mean:
- Poor tuning
- Analyst fatigue
- Missed real threats



### 4. False Positive Rate
- Alerts that look malicious but are actually benign
- A high false positive rate wastes analyst time

Goal:
Reduce noise so analysts focus on **real threats**

---

### 5. Incident Closure Rate
- How many incidents are fully investigated and closed
- Shows analyst productivity and process maturity



## SOC Objectives (What a SOC is actually trying to achieve)

This room made it clear that SOC goals are **not just technical**.

### Core SOC Objectives

- Detect threats early
- Respond quickly and correctly
- Reduce attacker dwell time
- Protect business operations
- Improve security posture over time

A SOC that only “alerts” but doesn’t improve is failing its mission.



## Metrics vs Objectives (Important difference)

- **Objectives** = what the SOC wants to achieve  
- **Metrics** = how we prove we’re achieving it

Example:
Objective: Faster incident response  
Metric: Reduced MTTR month over month



## Why this matters for a SOC Analyst

As a junior SOC analyst, I learned that:
- My investigations affect SOC metrics
- Poor triage increases MTTR
- Mislabeling alerts increases false positives
- Clean investigations help SOC maturity

SOC work isn’t invisible — it’s measured.



## Real-world SOC takeaway

Good SOCs don’t just fight fires.
They:
- Track performance
- Tune detections
- Reduce noise
- Improve response over time

Metrics are how SOC teams justify budgets, tools, and headcount.


## Final reflection

This room helped me understand **how SOC work is evaluated**, not just how it’s done.

Learning detection is important.  
Learning **how detection is measured** is what makes a professional SOC analyst.SOC Metrics & Objectives — TryHackMe (Blue Team Fundamentals)
Why this room mattered to me
Before this room, I thought SOC work was mostly about finding alerts and reacting fast.
This lab helped me realize something important:
a SOC is also measured, evaluated, and improved using metrics — not guesses.

If you can not measure how your SOC performs then you can’t prove value or improve response.

What are SOC Metrics (in simple words)
SOC metrics are numbers that explain how well a SOC is doing.

They help answer questions like:

Are we detecting attacks fast enough?
Are analysts overwhelmed with false alerts?
Are incidents being resolved properly?
Is security really actually improving over time?
Metrics turn SOC work into data-driven decisions instead of opinions.

Key SOC Metrics I Learned
1. Mean Time To Detect (MTTD)
How long it takes to notice an incident after it starts
Lower MTTD = better detection
Example: If an attack starts at 10:00 and SOC notices at 10:15 → MTTD = 15 minutes

2. Mean Time To Respond (MTTR)
How long it takes to contain or remediate an incident
Measures response efficiency
Example: Alert detected at 10:15, resolved at 10:45 → MTTR = 30 minutes

3. Alert Volume
Total number of alerts generated
High volume ≠ good security
Too many alerts usually mean:

Poor tuning
Analyst fatigue
Missed real threats
4. False Positive Rate
Alerts that look malicious but are actually benign
A high false positive rate wastes analyst time
Goal: Reduce noise so analysts focus on real threats

5. Incident Closure Rate
How many incidents are fully investigated and closed
Shows analyst productivity and process maturity
SOC Objectives (What a SOC is actually trying to achieve)
This room made it clear that SOC goals are not just technical.

Core SOC Objectives
Detect threats early
Respond quickly and correctly
Reduce attacker dwell time
Protect business operations
Improve security posture over time
A SOC that only “alerts” but doesn’t improve is failing its mission.

Metrics vs Objectives (Important difference)
Objectives = what the SOC wants to achieve
Metrics = how we prove we’re achieving it
Example: Objective: Faster incident response
Metric: Reduced MTTR month over month

Why this matters for a SOC Analyst
As a junior SOC analyst, I learned that:

My investigations affect SOC metrics
Poor triage increases MTTR
Mislabeling alerts increases false positives
Clean investigations help SOC maturity
SOC work isn’t invisible — it’s measured.

Real-world SOC takeaway
Good SOCs don’t just fight fires. They:

Track performance
Tune detections
Reduce noise
Improve response over time
Metrics are how SOC teams justify budgets, tools, and headcount.

Final reflection
This room helped me understand how SOC work is evaluated, not just how it’s done.

Learning detection is important.
Learning how detection is measured is what makes a professional SOC analyst.

---
