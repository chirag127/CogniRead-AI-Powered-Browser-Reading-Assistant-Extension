# Contribution Guidelines for CogniRead-AI-Reading-Assistant-Browser-Extension

Welcome to the Apex initiative for `CogniRead-AI-Reading-Assistant-Browser-Extension`. As a project maintained under the **Apex Technical Authority**, we uphold rigorous standards focusing on performance, maintainability, and future-proofing. Contributions that align with these principles are highly valued.

## 1. Philosophy: Zero-Defect, High-Velocity, Future-Proof

We adhere strictly to core software engineering principles:

*   **SOLID:** Ensure classes/modules adhere to Single Responsibility, Open/Closed, Liskov Substitution, Interface Segregation, and Dependency Inversion principles.
*   **DRY (Don't Repeat Yourself):** Abstract common logic rigorously.
*   **YAGNI (You Ain't Gonna Need It):** Implement only what is currently required; avoid speculative generalization.

## 2. Development Environment Setup (The Apex Toolchain)

This project is primarily developed using **JavaScript/TypeScript**, leveraging modern browser extension tooling. Before submitting a Pull Request, ensure your local environment mirrors the CI configuration.

1.  **Clone Repository:**
    bash
    git clone https://github.com/chirag127/CogniRead-AI-Reading-Assistant-Browser-Extension.git
    cd CogniRead-AI-Reading-Assistant-Browser-Extension
    

2.  **Dependency Management:** We utilize `npm` for dependency management, though future iterations may integrate `pnpm` for atomic dependency resolution.
    bash
    npm install
    

3.  **Linting and Formatting:** All code must pass validation using **Biome** (as the standardized 2025 formatter/linter).
    bash
    # Check formatting and linting rules
    npm run lint
    # Automatically format files to standard
    npm run format
    

4.  **Testing:** Ensure all new features are accompanied by corresponding unit tests using **Vitest** and integration tests via **Playwright**.
    bash
    # Run unit tests
    npm run test:unit
    # Run end-to-end tests
    npm run test:e2e
    

## 3. Contribution Workflow

We follow a standard fork-and-pull request model.

### A. Reporting Issues
Use the official **Issue Templates** (`.github/ISSUE_TEMPLATE/bug_report.md`) to report bugs or propose features. Be precise, provide steps to reproduce, and specify expected vs. actual behavior.

### B. Submitting Code Changes

1.  **Create a Branch:** Base all development off the `main` branch.
    bash
    git checkout main
    git pull origin main
    git checkout -b feature/your-short-description
    

2.  **Commit Discipline:** Adhere to Conventional Commits specification (`feat:`, `fix:`, `refactor:`, `docs:`).
    *Example: `feat: add Gemini API error handling layer`*

3.  **Pull Request (PR) Creation:**
    *   Reference the issue being resolved (e.g., `Closes #123`).
    *   Ensure your branch passes all local checks (`npm run lint`, `npm run test:unit`).
    *   Fill out the **Pull Request Template** (`.github/PULL_REQUEST_TEMPLATE.md`) completely.

4.  **Review Process:** Automated CI pipelines will run checks upon PR submission. Code changes must receive approval from at least one maintainer before merging.

## 4. Security Contributions

We take security seriously. If you discover a vulnerability, please consult our **Security Policy** (`.github/SECURITY.md`) immediately and report it responsibly. **Do not** disclose vulnerabilities publicly before coordinated remediation.

## 5. Licensing

All contributions are licensed under the **CC BY-NC 4.0 License**, as defined in the root `LICENSE` file. By submitting code, you agree that your contributions fall under this license.

--- 
*Thank you for helping elevate the standards of `CogniRead-AI-Reading-Assistant-Browser-Extension`.*
