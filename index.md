---
layout: default
---
 
# $ whoami
 
> The strongest exploit is almost always a human one. I build software defensively and read the intent behind the signal.
 
I'm a **founding software engineer** who came to cybersecurity through **psychology** — a B.S. from the University of Iowa with a cybersecurity concentration. That order matters: I started with *why people do what they do*, then learned the technical craft to act on it. I write secure code in production at PivotPay, hold a **CompTIA Security+** certification, and I'm building an early-stage MSSP for small businesses — the segment most targeted and least served.
 
Most security treats the human as the weak link to patch around. I treat the human as the system worth understanding.
 
* * *
 
# Featured Projects
 
## Azure SIEM — Detection &amp; Response Pipeline
 
An end-to-end detection pipeline built in **Microsoft Sentinel**, June 2024.
 
*   Ingested security telemetry through **Log Analytics**
*   Authored detection rules in **KQL**
*   Automated triage and response with **Logic Apps**
A sample detection — flagging password-spray / brute-force activity against Azure sign-in logs:
 
```kql
// Flag accounts seeing repeated invalid-credential sign-ins from one source
SigninLogs
| where TimeGenerated > ago(1h)
| where ResultType == "50126"   // invalid username or password
| summarize Attempts = count()
        by IPAddress, UserPrincipalName, bin(TimeGenerated, 5m)
| where Attempts > 10
| project TimeGenerated, IPAddress, UserPrincipalName, Attempts
| order by Attempts desc
```
 
[View the project &rarr;](https://github.com/yourusername/azure-siem-project)
 
## Detection Validation — Atomic Red Team
 
Mapping detections to real adversary behavior by emulating techniques and confirming they surface in the data — closing the gap between "we have a rule" and "the rule actually fires."
 
[View the project &rarr;](https://github.com/yourusername/detection-validation)
 
## Secure Development at PivotPay
 
Production software with secure coding practices from the first commit: threat-aware design, code review, and shipping fast without shipping vulnerabilities.
 
* * *
 
# How I Investigate
 
> Most breaches aren't a failure of technology. They're a failure to ask what a person was actually trying to do.
 
An alert is a hypothesis, not a verdict. I work it through five steps:
 
1.  **Anchor on facts** — separate what's observed from what's assumed.
2.  **Name the missing context** — gaps are findings too.
3.  **Form competing hypotheses** — hold the benign and malicious read at once.
4.  **Identify the tipping evidence** — decide in advance what would settle it.
5.  **Recommend an action** — end with a decision, not a description.
To weigh whether activity is genuinely hostile, I assess across four dimensions instead of pattern-matching one indicator:
 
| Dimension       | The question I'm answering                                  |
|:----------------|:------------------------------------------------------------|
| Context         | Is this normal for this user, host, and hour?               |
| Sequence        | Does the order of events tell a story an attacker would write? |
| Intent          | What goal best explains the behavior as a whole?            |
| Counterfactual  | What would a legitimate user have done differently?         |
 
* * *
 
# Capabilities
 
| Domain                | Tools &amp; methods                                          |
|:----------------------|:------------------------------------------------------------|
| Detection &amp; SIEM  | Microsoft Sentinel, KQL, Log Analytics, Logic Apps        |
| Threat investigation  | IOC vs. IOA, lateral movement, ransomware lifecycle         |
| Adversary emulation   | Atomic Red Team, detection validation                       |
| Secure development    | Secure coding, code review, Git / GitHub workflows          |
| Foundations           | Security+, TLS, network &amp; auth protocols                |
| Human factors         | Social-engineering analysis, behavioral risk, intent modeling |
 
* * *
 
# Background
 
<dl>
<dt>Now</dt>
<dd>Founding Software Engineer, PivotPay &middot; Founder, small-business MSSP (early stage)</dd>
<dt>Certification</dt>
<dd>CompTIA Security+</dd>
<dt>Education</dt>
<dd>B.S. Psychology, University of Iowa &mdash; Cybersecurity concentration</dd>
</dl>
* * *
 
# Contact
 
*   **Email:** [you@example.com](mailto:you@example.com)
*   **GitHub:** [github.com/yourusername](https://github.com/yourusername)
*   **LinkedIn:** [linkedin.com/in/yourusername](https://www.linkedin.com/in/yourusername)
