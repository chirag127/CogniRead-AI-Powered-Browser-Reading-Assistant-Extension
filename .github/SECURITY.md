# Security Policy for CogniRead-AI-Powered-Browser-Reading-Assistant-Extension

As the Apex Technical Authority, we treat security as a first-class citizen. This document outlines the process for responsibly disclosing security vulnerabilities found in this project.

## 1. Supported Versions

This repository aims for immediate patching upon discovery. Security updates are applied to the `main` branch and subsequently backported if necessary.

| Version | Status |
| :--- | :--- |
| Latest (Main Branch) | Supported and actively monitored |
| Previous Major Releases | Monitored for critical vulnerabilities |

## 2. Vulnerability Reporting

We strongly encourage responsible disclosure. Please report security issues privately before making them public.

**Reporting Channel:**

1.  **Create a Private GitHub Issue:** Use the built-in issue tracking system and select the `Security Vulnerability` template (if available), or explicitly mark the issue as **confidential** in the title and description.
2.  **Email Contact (Fallback):** If immediate resolution is required or private issue tracking fails, email the maintainer directly: `security@chirag127.dev` (Note: This is a placeholder for demonstration; use the established GitHub process).

**Required Information for Disclosure:**

To facilitate rapid triage and remediation, please include the following details in your report:

*   **Product/Component:** Specify which part of the extension is affected (e.g., Content Script, Background Worker, Gemini API integration).
*   **Vulnerability Type:** (e.g., XSS, CSRF, Insecure Data Storage, Supply Chain Risk).
*   **Steps to Reproduce:** Detailed, unambiguous steps to trigger the vulnerability.
*   **Impact:** A clear description of the potential harm (e.g., data exfiltration, denial of service).
*   **Suggested Mitigation (Optional but appreciated):** Any pointers toward a fix based on the TypeScript/Vite stack.

## 3. Timeline and Feedback

We commit to the following initial response times:

*   **Acknowledgement:** Within 48 hours of receiving a report.
*   **Triage & Confirmation:** Within 7 business days.
*   **Patch Release:** Aiming for a fix to be deployed to the `main` branch within 14 business days, depending on severity and complexity.

We will keep the reporter informed throughout the remediation process.

## 4. Remediation Policy (Apex Standard)

All discovered vulnerabilities are treated under the principle of **Zero-Defect, High-Velocity**. This means:

1.  **Immediate Isolation:** If necessary, affected functionalities may be temporarily disabled or rolled back until a validated patch is deployed.
2.  **Supply Chain Integrity:** Dependencies (managed via `npm` or `pnpm` equivalent for this TypeScript project) are scanned continuously via CI workflows (`.github/workflows/ci.yml`) using modern vulnerability scanners (e.g., Snyk integration, or built-in GitHub Dependabot alerts).
3.  **Verification:** Patches must pass **ALL** unit tests (Vitest) and end-to-end tests (Playwright) defined in the repository structure.

## 5. Disclaimer

This security policy applies to the source code hosted under `https://github.com/chirag127/CogniRead-AI-Powered-Browser-Reading-Assistant-Extension`.

Issues related to third-party services (e.g., Google Gemini API) should be directed to their respective vendors. However, insecure integration patterns exploiting these third-party services within our extension codebase will be addressed under this policy.