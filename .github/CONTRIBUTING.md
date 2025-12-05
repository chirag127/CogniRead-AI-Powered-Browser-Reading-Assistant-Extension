# Contributing to CogniRead: AI-Powered Browser Reading Assistant

Thank you for your interest in contributing to **CogniRead**! This guide outlines the best practices and standards for contributing to this project. Your contributions help us maintain a high-quality, efficient, and robust AI-powered reading assistant for the browser.

## Table of Contents
- [Code of Conduct](#code-of-conduct)
- [How Can I Contribute?](#how-can-i-contribute)
  - [Reporting Bugs](#reporting-bugs)
  - [Suggesting Enhancements](#suggesting-enhancements)
  - [Writing Code](#writing-code)
  - [Improving Documentation](#improving-documentation)
- [Getting Started: Local Development Setup](#getting-started-local-development-setup)
  - [Prerequisites](#prerequisites)
  - [Cloning the Repository](#cloning-the-repository)
  - [Installing Dependencies](#installing-dependencies)
  - [Running the Development Environment](#running-the-development-environment)
  - [Running Tests](#running-tests)
  - [Linting and Formatting](#linting-and-formatting)
- [Submitting Changes: Pull Request Guidelines](#submitting-changes-pull-request-guidelines)
  - [Branching Strategy](#branching-strategy)
  - [Commit Message Guidelines](#commit-message-guidelines)
  - [Creating a Pull Request](#creating-a-pull-request)
- [Architectural Principles](#architectural-principles)
- [Security Vulnerabilities](#security-vulnerabilities)
- [License](#license)

## Code of Conduct
Please note that this project is released with a [Code of Conduct](https://github.com/chirag127/CogniRead-AI-Powered-Browser-Reading-Assistant-Extension/blob/main/.github/CODE_OF_CONDUCT.md). By participating in this project, you agree to abide by its terms.

## How Can I Contribute?

### Reporting Bugs
If you find a bug, please open an issue using our [bug report template](https://github.com/chirag127/CogniRead-AI-Powered-Browser-Reading-Assistant-Extension/blob/main/.github/ISSUE_TEMPLATE/bug_report.md).
*   **Before reporting:** Check existing issues to see if the bug has already been reported.
*   **Be descriptive:** Provide a clear, concise description of the bug, steps to reproduce it, expected behavior, and actual behavior. Screenshots or screen recordings are highly appreciated.

### Suggesting Enhancements
New features, improvements, or architectural suggestions are always welcome. Please open an issue to discuss your ideas.
*   Clearly describe the feature, its purpose, and the problem it solves.
*   Explain how it benefits users or the project.

### Writing Code
Contributions of code are invaluable. Before starting any significant work, please discuss your proposed changes by opening an issue first. This helps avoid duplicate efforts and ensures alignment with project goals.

### Improving Documentation
High-quality documentation is crucial. If you find areas for improvement, typos, or want to expand on existing documentation, please feel free to submit a pull request or open an issue.

## Getting Started: Local Development Setup

To set up your local development environment, follow these steps:

### Prerequisites
*   **Git**: For version control.
*   **Node.js**: Version 18.x or higher (LTS recommended).
*   **pnpm**: Recommended package manager. If not installed, you can get it with `npm install -g pnpm`.

### Cloning the Repository
First, clone the `CogniRead` repository to your local machine:
bash
git clone https://github.com/chirag127/CogniRead-AI-Powered-Browser-Reading-Assistant-Extension.git
cd CogniRead-AI-Powered-Browser-Reading-Assistant-Extension


### Installing Dependencies
Install the project dependencies using `pnpm`:
bash
pnpm install


### Running the Development Environment
This project uses Vite for a fast development experience and WXT for browser extension scaffolding.
To start the development server:
bash
pnpm dev

This will build the extension and watch for changes, automatically reloading it in your browser (after initial manual loading).

### Running Tests
We use Vitest for unit/integration tests and Playwright for end-to-end (E2E) tests.

**Unit/Integration Tests (Vitest):**
bash
pnpm test


**End-to-End Tests (Playwright):**
First, ensure Playwright browsers are installed:
bash
pnpm playwright install
pnpm test:e2e


### Linting and Formatting
**CogniRead** enforces strict code quality and consistency using Biome.

**Check for linting/formatting issues:**
bash
pnpm lint


**Automatically fix linting/formatting issues:**
bash
pnpm format

Always run these commands before committing your changes.

## Submitting Changes: Pull Request Guidelines

### Branching Strategy
*   Always create a new branch for your changes, based on the `main` branch.
*   Use descriptive branch names, e.g., `feat/add-summarization-feature`, `fix/issue-123-crash-on-empty-text`, `docs/update-readme`.

### Commit Message Guidelines
We follow the [Conventional Commits specification](https://www.conventionalcommits.org/en/v1.0.0/) for commit messages. This enables automated changelog generation and semantic versioning.

**Commit Message Structure:**

<type>(<scope>): <subject>

[body]

[footer]


**Examples:**
*   `feat(summarization): implement core summarization logic via Gemini API`
*   `fix(popup): resolve UI overflow issue on small screens`
*   `docs(readme): update installation instructions`
*   `chore(deps): update vite to v7`

### Creating a Pull Request
1.  **Sync your branch:** Before pushing, rebase your branch on the latest `main` to resolve any conflicts:
    bash
git fetch origin
git rebase origin/main
    
2.  **Push your branch:**
    bash
git push origin your-branch-name
    
3.  **Open a Pull Request:** Navigate to the [CogniRead GitHub repository](https://github.com/chirag127/CogniRead-AI-Powered-Browser-Reading-Assistant-Extension) and open a new Pull Request.
    *   **Fill out the [PR Template](https://github.com/chirag127/CogniRead-AI-Powered-Browser-Reading-Assistant-Extension/blob/main/.github/PULL_REQUEST_TEMPLATE.md):** Ensure you provide a clear title, detailed description, and link to any relevant issues.
    *   **Ensure CI passes:** Your PR will be automatically checked by GitHub Actions for linting, formatting, and tests. Make sure all checks pass.
    *   **Request Review:** Once your PR is ready, request a review from the maintainers.

## Architectural Principles
CogniRead adheres to a **Feature-Sliced Design (FSD)** architecture.
*   **Modularity**: Clear separation of concerns into layers (app, processes, pages, widgets, features, entities, shared).
*   **Scalability**: Designed to easily extend and maintain features as the project grows.
*   **Reusability**: Encourages the creation of independent, reusable modules.
*   **Testability**: Each layer and slice should be independently testable.

Adherence to principles like **SOLID**, **DRY (Don't Repeat Yourself)**, and **YAGNI (You Aren't Gonna Need It)** is also expected.

## Security Vulnerabilities
If you discover a security vulnerability, please report it responsibly by following our [Security Policy](https://github.com/chirag127/CogniRead-AI-Powered-Browser-Reading-Assistant-Extension/blob/main/.github/SECURITY.md). Do not open a public issue.

## License
By contributing to CogniRead, you agree that your contributions will be licensed under the [Creative Commons Attribution-NonCommercial 4.0 International License](https://github.com/chirag127/CogniRead-AI-Powered-Browser-Reading-Assistant-Extension/blob/main/LICENSE).