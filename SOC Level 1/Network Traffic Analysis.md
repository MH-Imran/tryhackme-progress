# Network Traffic Analysis (TryHackMe — SOC Level 1)

This module helped me build a **repeatable way to investigate PCAPs** and explain findings like a SOC L1 analyst.
My focus was: *What can I confidently prove from network traffic, and how do I document it?*

---

## Rooms Covered (Module Checklist)

- ✅ Network Traffic Basics  
- ✅ Wireshark: The Basics  
- ✅ Wireshark: Packet Operations  
- ✅ Wireshark: Traffic Analysis  
- ✅ NetworkMiner  

---

## 1) Network Traffic Basics

### What it means (simple)
Network traffic analysis is using packet/flow data to understand:
- **who** communicated (src/dst)
- **when** it happened (timestamps)
- **how** it happened (protocol/port)
- **what** might have happened (behavior + artifacts)

### What I practiced
- Difference between **packet data (PCAP)** vs **metadata/flows**
- Where traffic can be collected (host, switch SPAN, TAP, firewall, IDS sensor)
- High-level view of common protocols (DNS, HTTP/S, TCP/UDP)

### Why this matters in a SOC
Most alerts are “network-shaped” (suspicious IP/domain/port).  
If I can quickly validate traffic, I can:
- confirm/deny an alert
- scope affected hosts
- extract IOCs for blocking/detection

### My practical takeaway
Before opening any tool, I ask:
- *What is the suspected host?*
- *What time window matters?*
- *What indicator am I trying to confirm (IP/domain/port/protocol)?*

---

## 2) Wireshark: The Basics

### What it is (simple)
Wireshark is a packet analyzer used to inspect PCAPs at a very detailed level.

### What I practiced
- Reading packets (list → details → bytes)
- Using Wireshark “fast triage” views:
  - **Protocol Hierarchy**
  - **Endpoints**
  - **Conversations**
- Basic display filters to reduce noise

### Why this matters in a SOC
Wireshark helps me turn “raw traffic” into answers like:
- Did the host resolve a suspicious domain?
- Did it connect out to that destination?
- What protocol was used (DNS/HTTP/TLS/etc.)?

### My practical takeaway
First pass = **statistics + top talkers**, not deep inspection.
I only deep-dive once I’ve identified the suspicious endpoint(s).

---

## 3) Wireshark: Packet Operations

### What it is (simple)
This room was about using Wireshark like an investigator: **extract evidence**, not just view packets.

### What I practiced
- **Follow TCP Stream** (rebuild conversations when possible)
- Understanding TCP behavior (handshake, FIN/RST)
- Using marking/time references to support a simple timeline
- Exporting/inspecting useful artifacts (when traffic is not encrypted)

### Why this matters in a SOC
A good investigation requires **proof**:
- what was requested (e.g., HTTP URI)
- what was transferred (if visible)
- sequence of events (timeline)

### My practical takeaway
“Follow Stream” is one of the quickest ways to go from packets → story.

---

## 4) Wireshark: Traffic Analysis

### What it is (simple)
Traffic analysis is looking for **patterns and anomalies** (not just single packets).

### What I practiced
- Finding suspicious behavior:
  - scanning (many SYNs / many ports)
  - repeated connections (possible beaconing)
  - unusual DNS patterns (long/random subdomains, NXDOMAIN spikes)
- Using Wireshark features to spot anomalies quickly:
  - **Expert Information**
  - **IO Graphs**
  - Conversations/Endpoints for top talkers

### Why this matters in a SOC
A lot of threats are visible as behavior:
- unusual outbound destinations
- unusual frequency/regularity
- protocol misuse

### My practical takeaway
Even when payloads are encrypted (TLS), I can still extract value from:
- destination IPs
- timing/frequency
- DNS + TLS SNI (when available)
- session sizes/durations

---

## 5) NetworkMiner

### What it is (simple)
NetworkMiner is a network forensic tool that extracts **artifacts** from PCAPs (files, hosts, sessions, credentials in some cases).

### What I practiced
- Identifying hosts involved and basic session details
- Extracting artifacts (when present in captured traffic):
  - files transferred over HTTP (and other cleartext protocols)
  - metadata like user-agents, hostnames, DNS info
- Using it as a fast “artifact extraction” companion to Wireshark

### Why this matters in a SOC
It speeds up evidence collection when I need:
- quick IOCs (domains, URLs, file names)
- a list of involved hosts
- potential payload artifacts for deeper malware analysis (when available)

### My practical takeaway
Workflow that feels SOC-real:
**NetworkMiner for fast artifacts → Wireshark to validate + explain how it happened**.

---

# My Quick NTA Workflow (SOC L1)

1) **Scope**
- time window, suspected host, suspected indicator

2) **Triage**
- Protocol Hierarchy / Endpoints / Conversations (find top talkers)

3) **Pivot**
- DNS → domains queried
- TCP/UDP → unusual ports
- HTTP (if present) → hosts/URIs
- TLS (if present) → SNI/cert hints + patterns

4) **Extract + Document**
- IOCs + timestamps + short narrative + next steps

---

# Mini PCAP Note Template (My Practice Format)

**Title:**  
**Time Window:**  
**Suspected Host:**  
**Summary (2–3 lines):**  

**Evidence:**
-  
-  
-  

**IOCs:**
- IPs:  
- Domains:  
- URLs/URIs:  
- Notes: (ports, protocol, frequency pattern)

**Assessment:** Benign / Suspicious / Escalate  
**Next Steps:**  

---

# Next Practice Goals (After this module)

- Build a “PCAP triage checklist” I can apply in under 5 minutes.
- Practice writing 2 short summaries:
  - one scanning/recon example
  - one possible beaconing/C2-pattern example
- Improve my Wireshark filtering speed (common filters for DNS/HTTP/TLS/TCP flags).
