# Security Policy for CogniRead-AI-Reading-Assistant-Browser-Extension

As an Apex project, **CogniRead-AI-Reading-Assistant-Browser-Extension** adheres to the **Zero-Defect, High-Velocity, Future-Proof** philosophy. Security is integrated into every stage of development, reflecting Late 2025 best practices.

## Supported Versions

| Version | Status | Supported Until | Notes |
| :--- | :--- | :--- | :--- |
| Latest Release | Supported | Ongoing | Active Patching |

## Reporting a Vulnerability

We take security vulnerabilities seriously. If you discover any security issue, please follow the process below to report it responsibly.

1.  **Do not** create a public issue or pull request.
2.  Email the designated security contact immediately: `security@apex-architect.dev` (Placeholder for high-priority communication).
3.  In your email, clearly describe the vulnerability, including the affected component, the steps to reproduce it, and the potential impact.

We commit to acknowledging receipt of your report within **48 hours** and will work diligently to provide a patched release.

## Vulnerability Disclosure Timeline

We adhere to a responsible disclosure timeline to ensure the security of all users:

1.  **Report Received:** We begin investigation immediately.
2.  **Patch Development:** A fix is developed using **TypeScript/JavaScript** standards (ESLint/Biome enforced, strict type checking).
3.  **Internal Testing:** The fix is rigorously tested via our CI pipeline (`.github/workflows/ci.yml`) using **Playwright** for critical E2E security flows.
4.  **Release:** Once the patch is verified, a new version will be published. We aim to release a fix within **14 days** of a valid vulnerability report.
5.  **Public Disclosure:** Public communication regarding the vulnerability (e.g., updating the GitHub Security Advisory) will occur *after* the patch is released.

## Security Audit & Practices

This project emphasizes a proactive security stance:

*   **Dependency Scanning:** Automated scanning of all npm dependencies is integrated into the CI pipeline using industry-standard tools (e.g., Snyk or GitHub Dependabot).
*   **API Key Management:** **NEVER** hardcode sensitive keys (like the Gemini API Key) in source code. Configuration must be managed via environment variables (`.env` files managed locally, excluded via `.gitignore`).
*   **Content Security Policy (CSP):** Strict CSP headers are enforced in the extension manifest to mitigate XSS attacks against injected content.
*   **Code Review:** All code merges require at least one approving review, focusing specifically on potential injection vectors and API interaction validation.

## Dependencies

This project relies heavily on the **Google Gemini API**. Users must ensure their API credentials are handled securely according to Google's best practices. This repository **DOES NOT** store, manage, or expose user API keys.

For a full list of dependencies, please refer to the project's `package.json`.

--- 

*Last Reviewed: December 2025 by Apex Technical Authority*
[Report Security Issue](mailto:security@apex-architect.dev)