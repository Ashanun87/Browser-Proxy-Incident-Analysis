Browser Proxy Interference Incident Analysis

This project demonstrates real-world detection and remediation of suspicious browser behavior involving proxy interference and authentication anomalies.

---
 Overview
This project documents a real-world security investigation into abnormal browser behavior encountered while attempting to access Gmail. The issue presented as connectivity failures combined with an unexpected authentication prompt, indicating potential traffic interception or proxy misconfiguration.

---

Objective
To investigate and identify the root cause of browser-based connectivity and authentication anomalies, determine potential security risks, and implement a safe remediation.

---

Initial Symptoms
- Gmail returned error: `ERR_FAILED`
- Unexpected browser-based login prompt appeared (non-standard for Google authentication)
- Proxy-related error observed: `ERR_PROXY_CONNECTION_FAILED`

Evidence
[Gmail Error](https://github.com/user-attachments/assets/154e3f63-07e1-44bd-907f-1bddd10fe264)

[Proxy Error](https://github.com/user-attachments/assets/c536c72a-8fc2-49be-8988-5b0a3ad80457)

---

Investigation Process

1. System-Level Proxy Validation
- Reviewed macOS Network → Proxy settings  
- Confirmed all proxy configurations were disabled  
- Ruled out system-level proxy misconfiguration  

2. Behavioral Analysis
- Observed continued failure despite clean system configuration  
- Identified inconsistency between expected Gmail authentication flow and observed login prompt  
- Hypothesized browser-level interference  

3. Extension Analysis
- Audited installed Chrome extensions  
- Identified active VPN extension: **SetupVPN**  
- Determined extension was routing traffic through external proxy infrastructure  

---

Findings
- SetupVPN extension introduced browser-level proxy routing independent of system settings  
- Caused:
  - Network connectivity failures  
  - Authentication anomalies  
  - Proxy connection errors  
- Behavior mimicked characteristics of potential traffic interception scenarios  

---

Remediation Actions
- Disabled and removed SetupVPN Chrome extension  
- Restarted browser session  
- Re-tested Gmail access via direct URL entry  

Result
- Gmail access restored successfully  
- No further authentication anomalies observed  
- Proxy errors resolved  

---

Key Security Insights
- Browser extensions can override system-level network configurations  
- Unexpected authentication prompts should be treated as potential credential harvesting attempts  
- Proxy-related errors combined with login anomalies may indicate traffic manipulation risks  

---

Skills Demonstrated
- Threat detection & analysis  
- Root cause analysis  
- Network and browser-layer troubleshooting  
- Security awareness and risk identification  
- Incident documentation  

---

Author
Andrea Allen

## 👩🏽‍💻 Author
Andrea Allen
