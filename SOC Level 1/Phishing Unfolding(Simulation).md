# Phishing Unfolding (SOC Simulator — TryHackMe SOC L1)

I completed **Phishing Unfolding** in TryHackMe’s **SOC Simulator**.  
This one felt *much closer to real SOC work* than normal rooms because it forces you to triage alerts, decide **TP vs FP**, and write reports the way a SOC actually does.

[**Public summary**]( https://tryhackme.com/soc-sim/public-summary/bb64a481410bc0c06702fc8c174ed9af48f6694d6530fe1b3e3f18eb017e6c787de70ee33b7f0ea2a5d0c9efc1e64097
)


---

## What I practiced (SOC workflow)
- Alert triage: quickly deciding what deserves deep investigation
- Evidence-first thinking: collecting artifacts before writing conclusions
- Report writing: short, clear, and actionable
- Confidence in decisions: closing alerts with a reason (not guessing)

---

## My real struggle (important lesson)
I struggled to do this simulation the right way at first **because I didn’t read the guidelines properly**.

The rule was:
✅ **Write reports only for TRUE POSITIVE alerts**

But I initially wrote reports for **almost everything** (both **True Positive + False Positive**).  
That mistake made me spend **a lot more time** than needed.

The good part: even though I wasted time, **all my reports were 100% correct** — it showed me my analysis logic is solid, but my *process discipline* needs to improve (reading rules + following workflow).

---

## What I learned (the “SOC” takeaways)
- In SOC work, **process matters as much as correctness**.
- Reporting on false positives can be useful for internal tuning, but if the task says “report TP only,” follow the playbook.
- A good approach is:
  1) **Triage fast**
  2) **Confirm TP/FP**
  3) **Report only when required**
  4) **Escalate with clear evidence**

---

## Mini SOC report style (what I used)
When an alert is a **True Positive**, my report should include:

- **Summary (2–3 lines):** what happened and why it’s malicious  
- **Evidence:** 3–6 bullets (URLs/domains, sender artifacts, user action, follow-on activity)  
- **Impact:** what could happen / what was affected  
- **Next steps:** block/hunt/contain/user guidance/escalation  

---

## What I’ll do better next time
- Read the scenario rules once, then read them again (seriously).
- Use a quick decision note for FP (no full report unless asked).
- Get faster at writing TP reports without losing clarity.

---

## Result
✅ All reports: **100% correct**  
🧠 Biggest improvement: following instructions + reporting workflow (not just solving)
