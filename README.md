# GitHub Actions Lab - Neil Patrick Saldanha

## Overview
This repository demonstrates three GitHub Actions workflows showcasing key CI/CD concepts.

## Workflows

### 1. Job Dependencies Workflow (dependent-jobs.yml)
**Purpose:** Demonstrates sequential job execution using the `needs` key.

**Key Concepts:**
- Job dependencies using `needs`
- Sequential execution: build → test → deploy
- Simulated build, test, and deployment processes

**Trigger:** Push to main branch

---

### 2. Environment Variables and Secrets Workflow (env-and-secrets.yml)
**Purpose:** Demonstrates environment variable scoping and secret management.

**Key Concepts:**
- Workflow-level environment variables (available to all jobs)
- Job-level environment variables (available to all steps in a job)
- Step-level environment variables (available only in that step)
- GitHub Secrets for sensitive data (AWS credentials)
- Secrets are automatically masked in logs

**Trigger:** Manual (workflow_dispatch)

---

### 3. Multi-Platform Testing Workflow (multi-platform.yml)
**Purpose:** Demonstrates parallel execution across multiple operating systems.

**Key Concepts:**
- Independent jobs running simultaneously
- Multi-platform testing: Ubuntu, Windows, and macOS
- Platform-specific commands
- The `runs-on` key for specifying runner operating system

**Trigger:** Pull request to main branch

---

## Key GitHub Actions Concepts Demonstrated

- **needs:** Creates job dependencies (Workflow 1)
- **env:** Defines environment variables at workflow, job, and step levels (Workflow 2)
- **runs-on:** Specifies the runner operating system (All workflows)
- **secrets:** Securely stores and accesses sensitive data (Workflow 2)
- **workflow_dispatch:** Enables manual workflow triggering (Workflow 2)
- **pull_request:** Triggers workflows on PR events (Workflow 3)

## Challenges and Solutions

### Challenge 1: Understanding Variable Scope
Initially, understanding when environment variables are accessible was confusing.

**Solution:** Created explicit examples at each scope level (workflow, job, step) to see how each variable type behaves and where they can be accessed.

### Challenge 2: Windows Command Syntax
Windows uses different commands than Linux/Mac for basic operations.

**Solution:** Used Windows-specific commands like `systeminfo`, `echo >`, and `type` instead of Linux equivalents like `uname`, `echo`, and `cat`.

### Challenge 3: Testing Pull Request Workflows
Pull request workflows need a separate branch to trigger properly.

**Solution:** Created a feature branch (`test-multi-platform`), pushed the workflow file, then opened a PR to trigger the multi-platform workflow and observe parallel execution.

---

## Repository Structure
```
.
├── .github/
│   └── workflows/
│       ├── dependent-jobs.yml
│       ├── env-and-secrets.yml
│       └── multi-platform.yml
└── README.md
```

## How to Use

1. **Workflow 1 (Job Dependencies):** Automatically runs on every push to main branch
2. **Workflow 2 (Environment & Secrets):** Go to Actions → "Environment Variables and Secrets Workflow" → Click "Run workflow"
3. **Workflow 3 (Multi-Platform):** Automatically runs when you create a pull request to main branch

---

## Lab Completion

All three workflows have been successfully implemented and tested:
- ✅ Workflow 1: Sequential job execution with dependencies
- ✅ Workflow 2: Environment variables and secrets management
- ✅ Workflow 3: Parallel multi-platform testing

## Author
Neil Patrick Saldanha