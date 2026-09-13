# Junior Security Analyst Intro — TryHackMe SOC Level 1

- **Module:** Blue Team Introduction
- **Room:** [Junior Security Analyst Intro](https://tryhackme.com/room/jrsecanalystintrouxo)
- **Difficulty:** Easy
- **Date completed:** <fill in>
- **Tools:** room's web-based alert dashboard simulation

## TL;DR

This room explains the Junior (Tier 1) Security Analyst role: what a triage analyst does, what basic skills are needed, and who to contact when something needs escalation.

## Task context

Scenario: my first day as a Junior Security Analyst. The room shows the team structure (Senior Analyst, SOC Engineer, SOC Manager, Incident Responder) and then gives a simple alert to handle: a successful SSH login from an external IP.

## Methodology / walkthrough

### Step 1. Learn the team structure

Before doing anything, I need to know who does what on the team:

- **Junior/L1 Analyst** — checks new alerts, does the first classification.
- **Senior/L2 Analyst** — handles harder cases, helps junior analysts.
- **SOC Engineer** — keeps the tools running (SIEM/EDR/SOAR), improves detections.
- **Incident Responder** — steps in when an incident is confirmed and needs action.
- **SOC Manager** — makes decisions and talks to the business side.

Takeaway: I shouldn't escalate to just anyone. I need to send the alert to the person who actually deals with that type of problem.

### Step 2. Check the alert

The alert: a successful SSH login from an IP that shouldn't normally connect. My steps:

1. Look at the **source** of the alert — which IP, which host it connected to.
2. Check if this IP is already known as bad (in a real job I'd use VirusTotal or AbuseIPDB; in this room the IP is already marked as malicious).
3. Since the IP is malicious, this is not just something to note — it's an **actionable alert**. It needs a comment and the IP needs to be blocked.
4. Write a short comment: what the IP is, why I'm blocking it, and what happened (a successful SSH login from an unexpected IP).

### Step 3. Who to tell

This is suspicious, but it's not a full incident yet. So I escalate to the **Senior Analyst**, not to the Manager or the Incident Responder. The Senior Analyst is the right person to check unclear cases and decide if it needs to go further.

## Key MITRE ATT&CK techniques

This room doesn't use ATT&CK directly. But a login from a bad IP fits under **Initial Access → Valid Accounts (T1078)** if this case grew into a real investigation.

## Lessons learned

- A SOC is a team, not one person. Everyone has a clear role.
- Triage means deciding fast: is this normal noise, something to note, or a real problem?
- Even small actions (like a comment on a block) matter — they help later reports and metrics.
- Good basics for this job: networking (OSI/TCP-IP), Windows/Linux basics, and some web knowledge. I should review these if they feel weak.

## References

- [Junior Security Analyst Intro — TryHackMe](https://tryhackme.com/room/jrsecanalystintrouxo)
- TryHackMe: Introductory Networking Room (for an OSI/TCP-IP refresher)
