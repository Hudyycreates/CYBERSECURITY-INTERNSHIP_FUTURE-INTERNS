# API Security Risk Analysis

## Overview
This repository contains a professional security assessment report focused on identifying and documenting common API vulnerabilities. The analysis was conducted by manually probing a public demo API using Postman, simulating the approach a real security analyst would take when auditing an API for security weaknesses.

The goal was not just to find vulnerabilities — but to understand why they exist, what damage they can cause in a real-world environment, and how they can be fixed.

---

## Target
**Postman Echo API** (`postman-echo.com`) — a public API designed for testing purposes, used here as a safe and legal environment to simulate real vulnerability scenarios.

---

## Tools & Technologies
- **Postman** — crafting and sending HTTP requests, inspecting responses
- **Browser DevTools** — analysing response headers and cookies
- **HTTP Protocol** — GET requests, Bearer Token authentication, query parameters
- **OWASP Top 10** — used as the security benchmark for evaluating findings

---

## Testing Methodology
Each test was performed manually by crafting specific requests and observing how the API responded. The following attack scenarios were simulated:

- Inspecting response headers for infrastructure and session data leakage
- Passing sensitive credentials through URL query parameters
- Submitting a fabricated Bearer Token to test authentication validation
- Sending rapid successive requests to test for rate limiting
- Injecting an XSS payload through a URL parameter to test input sanitization

---

## Vulnerabilities Identified

| # | Finding | Severity |
|---|---------|----------|
| 1 | Sensitive Data Exposed in Response Headers | Medium |
| 2 | Sensitive Data Exposed in URL Parameters | High |
| 3 | Broken Authentication — Invalid Token Accepted | Critical |
| 4 | No Rate Limiting | High |
| 5 | No Input Validation / XSS Vulnerability | High |

### Key Takeaways
- The API accepted a **completely fake authentication token** and returned 200 OK — meaning anyone could access it without real credentials
- **Passwords passed through the URL** were stored in plain text in server logs and browser history
- **No rate limiting** was enforced — leaving the API open to brute force and DDoS attacks
- An **XSS payload** was accepted and echoed back without any sanitization, violating OWASP principles
- **Response headers** leaked server infrastructure details and exposed active session cookies

---

## Real World Impact
These vulnerabilities, if found in a production API, could lead to:
- Breach of user data and violation of **GDPR** regulations
- **Session hijacking** and account takeover without needing a password
- Complete **service disruption** through automated request flooding
- **Reputational and financial damage** to a business

---

## Skills Demonstrated
- API security testing and manual vulnerability assessment
- HTTP protocol analysis (headers, status codes, request structure)
- Authentication and authorization evaluation
- Input validation and injection attack testing
- Risk documentation and business impact communication
- Application of OWASP Top 10 principles

---


