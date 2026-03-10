# FUTURE_CS_03
"Cyber Security Internship - Task 3: API Vulnerability Assessment Report"

📌 Project Overview
This repository contains a professional security audit and vulnerability assessment of the ReqRes.in REST API. The project was completed as part of my Cybersecurity Internship at Future Interns. The goal was to identify security gaps in data transmission, rate limiting, and server-side configurations.


🛠️ Tools Used
Postman: For API request manipulation and header analysis.
Browser DevTools (Network Tab): For cross-tool validation and real-world traffic monitoring.

🔍 Key Findings
1. Excessive Data Exposure (GET)
Issue: API endpoints return overly verbose JSON responses.
Risk: Potential leakage of internal system details to unauthorized users.


2. Lack of Rate Limiting (POST)
Issue: The internal API does not enforce strict per-IP rate limits for POST requests.
Risk: Susceptibility to automated "brute-force" or credential stuffing attempts.


3. Security Header Misconfiguration
Issue: Missing Strict-Transport-Security (HSTS) headers on the primary domain.
Risk: Vulnerability to man-in-the-middle (MITM) and protocol downgrade attacks.

🛡️ Remediation Plan
Implement Data Filtering: Update the API to strip out all non-essential fields from JSON payloads before they are sent to the client.
Enforce Application-Level Rate Limiting: Add a request "speed limit" (e.g., 10 requests per minute for sensitive endpoints) to block automated scripts.
Enable HSTS & Security Headers: Configure the server to force HTTPS connections and prevent clickjacking by adding HSTS and X-Frame-Options to all responses.
Sanitize Error Messages: Ensure the server returns simple, generic error messages instead of verbose HTML code pages.

📄 Full Assessment Report
👉 View Full VAPT Report (PDF)


🎓 Conclusion

The audit confirms that while external firewall protections are active, internal security gaps persist. Implementing these simple fixes will ensure the API is hardened and protected for all users.
