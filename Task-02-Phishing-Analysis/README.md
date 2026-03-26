[⬅️ Back to Main Portfolio](../README.md)

# Task 02: Phishing Detection & Analysis

### Executive Summary
A deep-dive analysis of a malicious email used in a targeted phishing campaign. This project demonstrates the ability to move beyond visual red flags to conduct a technical **Header Analysis**, verifying digital signatures (SPF, DKIM, DMARC) to prove sender impersonation.

### Technical Stack & Frameworks
* **Tools:** Email Header Analyzers, OSINT (Domain Lookups).
* **Protocols:** SPF (Sender Policy Framework), DKIM, DMARC.
* **Concepts:** Social Engineering, URL Deception, Payload Identification.

### Phishing Indicators & Business Impact
| Indicator | Technical Observation | Business Risk |
| :--- | :--- | :--- |
| **Auth Failure** | Failed SPF, DKIM, and DMARC checks. | **Critical:** Confirms the email did not originate from the claimed "TrustedBank" servers; high risk of credential harvesting. |
| **Identity Mismatch** | Display name `alerts@trustedbank.com` vs. Return-Path `auth-secure-mail.top`. | **High:** Uses a "Digital Mask" to bypass basic user scrutiny and trick employees into trusting the source. |
| **Insecure Payload** | Link uses `http://` instead of `https://`. | **High:** Any data entered on the destination site is transmitted in plain text, visible to attackers. |
| **Psychological Trigger** | Urgent claims of account locking and unauthorized withdrawals ($135.25). | **Medium:** Exploits "Fear & Urgency" to bypass the user's rational thinking, a classic Social Engineering tactic. |

### Defensive Guidelines (The "Human Firewall")
* **The Hover Test:** Always hover over links to reveal the true destination before clicking.
* **The "Source" Rule:** Never use links from an email to "verify" accounts; manually navigate to the official website or app.
* **Authentication Logic:** Real institutions do not fail SPF/DMARC records. An authentication failure is a 100% confirmation of a threat.

### Project Evidence
* 🔗 **[Full Phishing Analysis Report](./FUTURE_CS_02.pdf)**
