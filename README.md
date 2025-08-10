# Task 2- Phishing Email Analysis: Amazon Gift Card Scam

This repository contains the analysis of a **suspicious phishing email** impersonating **Amazon Gift Card Services**. The investigation includes email header inspection, hop analysis, blacklist status, and **live link verification**.

---

## 📌 Summary

- **Type**: Phishing Email
- **Claim**: You’ve received an Amazon Gift Card
- **Sender Domain**: `qwikcilver.com`
- **Suspicious Indicators**:
  - Email contains a **functioning link** to claim a "gift card".
  - Sending IP is on **blacklists**.
  - **Email fails authentication checks** on some platforms.
  - Multiple hops marked **Unsecure**.

---

## 🔍 Evidence

All screenshots are available under the `evidence/` folder.

| Evidence | Description |
|---------|-------------|
| `Email_Body.png` | Screenshot of the email body showing the gift card claim. |
| `Email_Hops.png` | Hop-by-hop analysis of email routing and security status. |
| `Header_Analysis.png` | Blacklist status and email header breakdown. |
| `Phishing_Link_Page.png` | The page shown after clicking the link (NEW). |

---

## 🕵️ Technical Findings

### ✅ SPF
- **PASS** with IP `167.89.34.179`

### ❌ Blacklist Status
- The IP `167.89.34.179` is on **multiple DNS-based blacklists** (DBL).
- This is a strong indicator of spam or phishing behavior.

### 📬 Email Hop Analysis

| Hop | Submitting Host | Receiving Host | Time | Security |
|-----|------------------|----------------|------|----------|
| 1 | 0.0.0.0 | geopod-ismtpd-4 | Unsecure |
| 2 | (unknown) | recvd-7487445b-4xmgq | Unsecure |
| 3 | `o5.ptr8232.qwikcilver.com (167.89.34.179)` | `mx.google.com` | ✅ Secure (TLS 1.3) |
| 4 | IPv6 address | Unknown | Unsecure |
| 5 | IPv6 address | Unknown | Unsecure |

---

## 🧪 Link Analysis (Updated)

- The **"Claim Your Gift Card"** link is now **active**.
- Leads to a webpage that appears **legitimate**, but is **likely harvesting data** or leading users to a scam.
- **DO NOT ENTER** any personal or payment information.

---

## 🛡️ Final Verdict

This is a **live phishing email** that impersonates Amazon to trick recipients into clicking and engaging with a **malicious site**. Though the SPF passed, the presence on blacklists, suspicious link, and unsecure hops make this email **malicious and deceptive**.

---

