[⬅️ Back to Main Portfolio](../README.md)

# 🌐 Task 03: API Security Risk Analysis

### Executive Summary
A manual security audit of the `postman-echo.com` public API to identify vulnerabilities and simulate real-world attack vectors. This project demonstrates the transition from theoretical OWASP principles to practical risk mitigation.

### Technical Stack & Frameworks
* **Tools:** Postman, Browser DevTools.
* **Standards:** OWASP Top 10 API Security.
* **Core Skills:** HTTP Protocol Analysis, Authentication Validation, Input Sanitization.

### Vulnerability Assessment & Business Impact
| Finding | Technical Observation | Business Risk |
| :--- | :--- | :--- |
| **Broken Authentication** | Accepted fabricated Bearer Tokens (200 OK). | **Critical:** Risk of unauthorized account takeover. |
| **Insecure Data Transit** | Credentials passed via URL parameters. | **High:** Plain-text passwords stored in server/browser logs. |
| **Lack of Rate Limiting** | No throttling on successive requests. | **High:** Vulnerable to Brute-Force and DDoS attacks. |
| **Missing Input Validation** | XSS payload echoed back unsanitized. | **High:** Potential for client-side script execution. |
| **Information Leakage** | Headers exposed server & session data. | **Medium:** Architectural blueprint for targeted hijacking. |

### Project Evidence
* 🔗 **[View Full API Audit Report](./YOUR_FILE_NAME_HERE.pdf)** ```
