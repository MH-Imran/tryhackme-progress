# 1) Introduction to EDR (Endpoint Detection & Response) (Room Notes)

### What I learned (in simple words)
EDR is basically the “security camera + detective” for endpoints (Windows/Linux machines).  
It watches what’s happening on a computer — processes, logins, network connections, file activity — and helps analysts **detect suspicious behavior** and **investigate quickly**.

### Why EDR matters in a SOC
Most real incidents leave footprints on endpoints:
- a weird process running
- PowerShell doing something shady
- a suspicious parent/child process chain
- connections to unknown IPs/domains  
EDR helps you see that story without guessing.

### Key EDR ideas I now understand
- **Telemetry**: EDR collects endpoint activity (process execution, network activity, file/registry changes, etc.)
- **Detections/Alerts**: rules + analytics turn activity into alerts
- **Triage vs Investigation**: first decide “is this real?” then dig deeper
- **Containment actions**: isolate host, kill process, quarantine file (depends on product)
- **IOC vs Behavior**: not only “known bad hash,” but also suspicious patterns

### SOC mindset takeaway
When I see an alert, I should ask:
- What process started it?
- What parent process launched it?
- What did it connect to?
- What user context ran it?
- Is this normal for this machine/user?

---

# 2) Introduction to SIEM (Security Information & Event Management) (Room Notes)

### What I learned (in simple words)
A SIEM is like the SOC’s “central brain” for logs.  
It collects logs from different places (endpoints, servers, firewalls, cloud, apps), normalizes them, and lets analysts **search**, **correlate**, and **alert** on suspicious patterns.

### Why SIEM matters in a SOC
If EDR is “per computer,” SIEM is “across the whole environment.”  
It helps answer questions like:
- Is the same username failing logins on multiple machines?
- Did a login happen right after many failures?
- Did a suspicious process correlate with a new outbound connection?

### Key SIEM ideas I now understand
- **Log ingestion**: getting logs into the SIEM (big deal in real life)
- **Normalization/fields**: making logs searchable by consistent fields
- **Correlation**: connecting related events from different sources
- **Dashboards**: visibility of trends (failed logons, rare processes, top destinations)
- **Alerts**: rules that trigger when conditions are met
- **False positives**: alerts aren’t always incidents — triage is required

### SOC mindset takeaway
A SIEM makes me faster, but it doesn’t replace my brain.  
My job is to decide: **benign / suspicious / escalate** — with evidence.

---

# 3) Splunk: The Basics (Room Notes)

### What I learned (in simple words)
Splunk is a popular SIEM/log analytics platform.  
The core power is searching data fast using **SPL (Search Processing Language)**.

### The practical things I practiced
- Searching logs by time range and keywords
- Filtering down noise into something readable
- Looking at important fields and patterns
- Building the habit of “search → refine → verify”

### How I think about SPL (beginner friendly)
SPL feels like:
- start broad (find the dataset / keyword)
- narrow down (filters, time window, field checks)
- summarize (count, group, top values)

### SOC mindset takeaway
In Splunk, I’m training myself to always ask:
- What time window matters?
- What is the key field I should pivot on (user, host, process, src_ip)?
- Can I confirm this with another data source?

---

# 4) Elastic Stack: The Basics (ELK) (Room Notes)
 
### What I learned (in simple words)
Elastic Stack is another major logging and analytics ecosystem:
- **Elasticsearch** = search + storage
- **Logstash / Beats / Agents** = collecting and shipping logs
- **Kibana** = dashboards + visual analysis

Elastic is widely used because it’s flexible, powerful, and common in real SOC environments.

### Why this matters for SOC L1
Even if a company doesn’t use Splunk, the analyst workflow is similar:
- find the right logs
- filter and pivot
- build a timeline
- support a decision

### Key Elastic ideas I now understand
- **Index**: where data lives (like a structured bucket of logs)
- **Fields**: important attributes to search and filter on
- **KQL / Lucene queries**: ways to search logs inside Kibana
- **Visualizations**: seeing spikes, anomalies, and top talkers quickly

### SOC mindset takeaway
Tools change, but analysis stays the same:
**evidence → context → decision → documentation**

---

# 5) Introduction to SOAR (Security Orchestration, Automation & Response) (Room Notes)

### What I learned (in simple words)
SOAR helps SOC teams automate repetitive work and keep response consistent.  
It can run workflows (“playbooks”) like:
- enrich an IP/domain (whois, reputation, geo, VT-like checks)
- open a ticket automatically with evidence
- notify the right team
- quarantine an endpoint (if integrated)

### Why SOAR matters in a SOC
SOC work has a lot of repeated tasks:
- enrichment
- ticket creation
- email triage
- common investigation steps  
SOAR reduces manual effort and improves consistency.

### Key SOAR ideas I now understand
- **Orchestration**: connecting tools together (SIEM, EDR, threat intel, ticketing)
- **Automation**: doing repetitive steps automatically
- **Playbooks**: step-by-step workflows (manual approvals can exist)
- **Human-in-the-loop**: automation helps, but analysts still decide

### SOC mindset takeaway
SOAR doesn’t replace analysts — it removes boring repetition so analysts can focus on decisions.

---

# What this module changed for me
Before this module, I mainly thought “SOC = logs.”  
Now I understand SOC as a **system of tools + workflow**:

- **EDR** = endpoint visibility + response actions  
- **SIEM** = centralized logs + correlation + alerting  
- **Splunk/Elastic** = two common ways to search/analyze logs  
- **SOAR** = automation + playbooks + consistent response

My next goal is to practice this like a real analyst:
**triage fast, collect evidence cleanly, and write good tickets.**

---

# Mini SOC Ticket Template (I use this for practice)
**Title:**  
**Time Window:**  
**Host/User:**  
**Alert Summary:**  
**Evidence (bullets):**  
-  
-  
-  
**Assessment:** Benign / Suspicious / Escalate  
**Next Steps:**  

---

# Next Practice Goals
- Write 5 mini tickets using SIEM-style thinking (pivot by host/user/IP)
- Practice 1 investigation in Windows logs + map it to what SIEM/EDR would show
- Build 1 small “playbook” checklist for phishing or brute-force triage
