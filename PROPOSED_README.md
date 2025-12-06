# CogniRead-AI-Reading-Assistant-Browser-Extension

> **Elevate your reading comprehension instantly.** CogniRead is a powerful, AI-driven browser extension that transforms passive reading into active learning, offering instant summaries, contextual explanations, and text-to-speech functionality leveraging the Google Gemini API.

---

## ⚡ Quick Start: Zero-Friction Comprehension

CogniRead integrates seamlessly into your browsing experience, providing on-demand cognitive support.

### Features
| Feature | Description | API Integration |
| :--- | :--- | :--- |
| **Instant Summarization** | Condenses lengthy articles into actionable bullet points or paragraphs. | Google Gemini Pro |
| **Contextual Explanations** | Double-click any term or concept for a real-time, AI-generated explanation. | Google Gemini Pro |
| **Text-to-Speech (TTS)** | High-quality voice synthesis using the Web Speech API for auditory learning. | Web Speech API |
| **Key Insights Extraction** | Focuses on main arguments, statistics, and conclusions for rapid knowledge assimilation. | Google Gemini Pro |

---

## 🛠️ Tech Stack & Status

| Status | Details | Link |
| :--- | :--- | :--- |
| **Build** | [![GitHub Actions Status](https://img.shields.io/github/actions/workflow/status/chirag127/CogniRead-AI-Reading-Assistant-Browser-Extension/ci.yml?branch=main&style=flat-square&label=CI%2FCD)](https://github.com/chirag127/CogniRead-AI-Reading-Assistant-Browser-Extension/actions/workflows/ci.yml) | Continuous Integration |
| **Coverage** | [![Code Coverage](https://img.shields.io/codecov/c/github/chirag127/CogniRead-AI-Reading-Assistant-Browser-Extension?style=flat-square&token=XYZ_TOKEN)](https://codecov.io/gh/chirag127/CogniRead-AI-Reading-Assistant-Browser-Extension) | Unit & E2E Tests |
| **Stack** | [![Language](https://img.shields.io/badge/Language-JavaScript%20%7C%20TypeScript%20(WXT)-F7DF1E?style=flat-square&logo=typescript)](https://www.typescriptlang.org/) | Core Engine |
| **Linter** | [![Linter](https://img.shields.io/badge/Lint%2FFormat-Biome-03063A?style=flat-square&logo=biome)](https://biomejs.dev/) | Code Quality Gate |
| **License** | [![License: CC BY-NC 4.0](https://img.shields.io/badge/License-CC%20BY--NC%204.0-lightgrey.svg?style=flat-square)](LICENSE) | Rights & Usage |
| **Stars** | [![GitHub Stars](https://img.shields.io/github/stars/chirag127/CogniRead-AI-Reading-Assistant-Browser-Extension?style=flat-square)](https://github.com/chirag127/CogniRead-AI-Reading-Assistant-Browser-Extension/stargazers) | Social Proof |

<p align="center">
  <a href="https://github.com/chirag127/CogniRead-AI-Reading-Assistant-Browser-Extension">
    <img src="https://img.shields.io/badge/Star%20this%20Repo-⭐-D73549?style=for-the-badge&logo=github" alt="Star this Repository" />
  </a>
</p>

## 🗺️ Architecture Overview

The extension adopts a modified Feature-Sliced Design (FSD) tailored for the browser extension lifecycle, separating concerns into background logic (services/APIs), content scripts (interaction), and the UI popup (widgets/pages).

mermaid
graph TD
    A[Browser Page] -->|Injects| B(Content Script);
    B -->|Messaging (API Calls)| C[Background Service (Event Page)];
    C -->|Secure Fetch| D[Google Gemini API / TTS];
    C -->|State Management| E{Extension Local Storage};
    F[Extension Popup UI] -->|Direct Access / State Sync| C;
    C -->|Response| B;
    B -->|DOM Manipulation| A;

    subgraph Core Features
        D
        E
    end


## ⚙️ Setup and Installation

### Prerequisites
1.  Node.js (LTS recommended)
2.  `uv` (Recommended package manager for speed) or `npm`
3.  A valid Google Gemini API Key.

### Development Environment Setup

1.  **Clone the Repository:**
    bash
    git clone https://github.com/chirag127/CogniRead-AI-Reading-Assistant-Browser-Extension.git
    cd CogniRead-AI-Reading-Assistant-Browser-Extension
    

2.  **Install Dependencies:**
    *Using `uv` (Fastest)*
    bash
    # Assuming Node.js dependencies for the extension
    npm install 
    
    *Using `npm`*
    bash
    npm install
    

3.  **Configure Environment Variables:**
    Create a `.env` file in the root directory:
    
    VITE_GEMINI_API_KEY="YOUR_API_KEY_HERE"
    

4.  **Run Development Build:**
    This command typically uses `WXT` or `Vite` to bundle the extension files for testing.
    bash
    npm run dev
    

5.  **Load Extension:**
    *   Open Chrome/Brave/Edge and navigate to `chrome://extensions`.
    *   Enable "Developer mode."
    *   Click "Load unpacked" and select the generated `dist` folder.

## 🚀 Available Scripts

| Command | Description |
| :--- | :--- |
| `npm run dev` | Starts the development server with hot module reloading (HMR). |
| `npm run build` | Compiles the extension for production deployment. |
| `npm run lint` | Runs Biome linting and static analysis checks. |
| `npm run format` | Auto-formats all code using Biome standards. |
| `npm run test:unit` | Executes all unit tests (using Vitest). |
| `npm run test:e2e` | Executes end-to-end tests (using Playwright) against a mocked browser context. |

---

<details>
<summary><h2>🤖 AI AGENT DIRECTIVES (APEX ARCHITECTURE BLUEPRINT)</h2></summary>

The following directives govern all architectural decisions and coding standards for the `CogniRead-AI-Reading-Assistant-Browser-Extension` codebase.

### 1. Technology Stack Definition
| Component | Tool/Framework | Purpose | Standard |
| :--- | :--- | :--- | :--- |
| **Language** | TypeScript (Strict) | Ensures Type Safety and Predictability. | Mandatory TSC `strict: true` |
| **Runtime** | Node.js (LTS) | Development, Testing, and Build Environment. | Target V18+ |
| **Bundler/Dev Tool** | WXT / Vite | High-speed extension bundling and HMR. | Optimized for speed (Rolldown backend future). |
| **Linter/Formatter** | Biome | Unified toolchain for linting, formatting, and analysis. | Aggressive linting ruleset (`complexity` and `performance` enabled). |
| **Testing Frameworks** | Vitest & Playwright | Vitest for unit/integration testing; Playwright for browser-level E2E tests. | 90% Code Coverage Minimum. |
| **Architecture** | Feature-Sliced Design (FSD) | Clear separation of `app`, `pages`, `widgets`, `features`, and `shared` layers. | Enforce low coupling via clear module boundaries. |

### 2. Architectural Principles & Patterns
*   **SOLID Principles:** Mandatory enforcement, especially Single Responsibility Principle (SRP) for utility modules (e.g., `gemini-api.ts` should only handle API calls, not UI updates).
*   **DRY (Don't Repeat Yourself):** Abstract common utility functions (e.g., messaging protocol helpers, configuration loading) into the `shared/lib` layer.
*   **Decoupling:** Background Service logic must be decoupled from Content Script DOM manipulation. Use browser Messaging APIs (`chrome.runtime.sendMessage`) as the strict boundary interface (Ports & Adapters pattern adaptation).
*   **Error Handling:** All AI interactions (Gemini API) must implement robust `try...catch` blocks, return explicit error objects, and handle rate-limiting gracefully via exponential backoff strategies.

### 3. Verification & Auditing Commands
All commits MUST pass the following verification sequence:

1.  **Dependency Check (uv/npm):** Ensure all dependencies are correctly resolved.
    bash
    npm audit --severity high
    
2.  **Linting & Formatting (Biome):** Ensure code quality meets Apex standards.
    bash
    npm run lint
    npm run format --check
    
3.  **Full Test Suite Execution (Vitest & Playwright):**
    bash
    npm run test:unit
    npm run test:e2e
    
4.  **Production Build Integrity Check:**
    bash
    npm run build 
    # (Manual sanity check of dist/ folder manifest and file sizes)
    

</details>

## 🤝 Contributing

We welcome high-quality contributions! Please review the **[CONTRIBUTING.md](.github/CONTRIBUTING.md)** guidelines before submitting pull requests.

## 🛡️ Security

If you discover any security vulnerabilities, please refer to the **[SECURITY.md](.github/SECURITY.md)** policy for responsible disclosure guidelines.

## 📝 License

This project is licensed under the **[Creative Commons Attribution-NonCommercial 4.0 International (CC BY-NC 4.0) License](LICENSE)**.