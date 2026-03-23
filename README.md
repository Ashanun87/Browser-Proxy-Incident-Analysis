# Browser-Proxy-Incident-Analysis
Investigation of proxy interference and authentication anomalies caused by a browser VPN extension
# 🔐 Browser Proxy Interference Incident Analysis

## 📌 Summary
This project documents a real-world investigation into a browser-based proxy issue that caused connectivity failures and suspicious authentication behavior when accessing Gmail.

---

## 🚨 Initial Symptoms
- Gmail returned: `ERR_FAILED`
- Unexpected browser login prompt appeared
- Proxy-related error: `ERR_PROXY_CONNECTION_FAILED`

---

## 🔍 Investigation Steps

### 1. Verified System Proxy Settings
- Navigated to macOS Network → Proxies
- Confirmed all proxy settings were disabled

### 2. Analyzed Browser Behavior
- Identified that issue persisted despite clean system settings
- Hypothesized browser-level interference

### 3. Reviewed Chrome Extensions
- Located active VPN extension: SetupVPN
- Recognized it could route traffic through proxy servers

---

## ⚠️ Findings
- SetupVPN extension was injecting proxy configurations at the browser level
- Caused failed connections and abnormal authentication prompts
- Mimicked behavior similar to traffic interception scenarios

---

## 🛠️ Remediation
- Disabled and removed SetupVPN extension
- Restarted browser
- Retested Gmail access → Issue resolved

---

## 🧠 Key Takeaways
- Browser extensions can override system-level network configurations
- Unexpected login prompts should always be treated as suspicious
- Proxy errors + authentication anomalies may indicate interception risks

---

## 🧩 Skills Demonstrated
- Threat detection & analysis
- Root cause identification
- Network troubleshooting
- Security awareness

---

## 👩🏽‍💻 Author
Andrea Allen
