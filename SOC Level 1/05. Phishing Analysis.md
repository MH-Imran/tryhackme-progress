# Phishing Analysis (Room notes)

I completed the full **Phishing Analysis** module. This one felt very “SOC-real” because phishing isn’t about guessing — it’s about **collecting small artifacts**, validating them, and writing a clear conclusion that a team can act on.

---

## Rooms Completed (Module Checklist)

- ✅ Phishing Analysis Fundamentals  
- ✅ Phishing Emails in Action  
- ✅ Phishing Analysis Tools  
- ✅ Phishing Prevention  
- ✅ The Greenholt Phish  
- ✅ Snapped Phish-ing Line  
- ✅ Phishing Unfolding  

---

## What I learned (the big picture)
Phishing analysis becomes much easier when I follow a repeatable flow:

1) **Identify the lure** (what the email wants the user to do)  
2) **Extract artifacts** (sender details, headers, URLs, attachments, wording patterns)  
3) **Validate** with tools (reputation checks, header analysis, URL expansion, sandboxing where possible)  
4) **Decide** (benign / suspicious / confirmed phishing)  
5) **Recommend action** (block, hunt, user comms, escalation)

---

## Key skills I practiced (SOC-focused)

### 1) Reading email structure properly
- Understanding what an email is made of (headers + body + metadata)
- Recognizing the difference between:
  - display name vs real sender
  - “from” vs “reply-to” vs “return-path” style fields
- Looking at timestamps and message flow (enough to reason about what’s real vs spoofed)

### 2) Spotting phishing indicators in real samples
- urgency + fear language
- impersonation (brand/CEO/IT/support)
- mismatched links (text says one thing, URL says another)
- odd domains/subdomains/paths
- attachments and “enable macros” style tricks

### 3) Using analysis tools the right way
- URL checks (expansion, reputation, redirects)
- domain/IP reputation and context
- hash checks (when attachments are involved)
- building an evidence trail instead of relying on one indicator

### 4) Thinking defensively (prevention + response)
- what controls help most (user awareness, filtering, blocking, MFA, reporting)
- how a SOC should respond after a report (contain + hunt + prevent repeats)

---

## Room reflections (short)

### Phishing Analysis Fundamentals
This made the “email parts” finally click. Instead of treating emails as plain text, I started treating them like evidence.

### Phishing Emails in Action
Good practice for identifying realistic indicators without overreacting to one small thing. The pattern matters more than a single clue.

### Phishing Analysis Tools
Helped me build a repeatable toolkit mindset: collect artifact → verify with tool → document result.

### Phishing Prevention
This room reminded me phishing defense isn’t only technical. Process matters: reporting flow, user training, and layered controls.

### The Greenholt Phish
This felt like a real investigation. I had to slow down, follow the evidence properly, and avoid jumping to conclusions.

### Snapped Phish-ing Line
This one was fun but also challenging — I struggled a bit finding the last flag at first. I fixed it by re-checking the question wording and validating the artifact trail step-by-step instead of re-scanning the same obvious places.

### Phishing Unfolding
This room connected everything into a bigger “incident unfolding” view, which feels closer to how phishing escalates inside a company.

---

## My phishing triage checklist (what I’ll reuse)
- Who is the sender really? (display name vs real address)
- Any reply-to tricks?
- Is the domain legit or lookalike?
- Where do the links actually go? (redirects?)
- Attachment present? What type? Any risk indicators?
- Who else received it? Any clicks?
- What should we block/hunt for?

---

## Mini SOC Ticket Template (Phishing)

**Title:** Suspected phishing email reported by user  
**Time window:**  
**User/Mailbox:**  

**Summary (2–3 lines):**  
What the email claimed + what it tried to make the user do.

**Artifacts collected:**
- Sender / Reply-to:
- Subject:
- URLs/domains:
- Attachment (name/type/hash if available):

**Assessment:** Benign / Suspicious / Confirmed Phishing  
**Next steps:**
- Block URL/domain (if malicious)
- Search for other recipients
- Contain affected host/account if user clicked
- User guidance + close the loop

---

## What I’m doing next
- More practice with phishing investigations + writing short tickets
- Continue building a small portfolio of “evidence → conclusion” writeups in GitHub
