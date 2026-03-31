# Module 1: Learn Claude Code

**⏱ Estimated Time:** 4–5 hours
**Week:** 1 | **Focus:** Foundations — AI Coding & Workflows

---

## Learning Objectives

- Install and configure Claude Code (terminal-native AI coding agent)
- Understand CLAUDE.md project configuration
- Build a small project end-to-end using Claude Code

---

## What is Claude Code?

Claude Code is Anthropic's terminal-native AI coding agent. Unlike a chatbot or autocomplete, it:

- **Reads, writes, and edits** your local files
- **Understands your entire codebase** (not just a single file)
- **Runs commands**, executes shell operations, and manages Git
- Operates under a **strict permission model** — you approve every file change and command

Think of it as having a senior developer that reasons, plans, and takes autonomous action — all through conversational prompts.

---

## Prerequisites

- Claude Pro, Max, Teams, or Enterprise subscription (starts at $20/mo)
- A project directory on your computer
- Git for versioning and rollbacks (recommended)

---

## Step-by-Step Activities

### 1. Install Claude Code

**On macOS or Linux:**
```bash
curl -fsSL https://claude.ai/install.sh | bash
```

**On Windows (PowerShell):**
```powershell
irm https://claude.ai/install.ps1 | iex
```

**Via Homebrew:**
```bash
brew install claude-code
```

Verify installation:
```bash
claude --version
```

### 2. Start Your First Session

```bash
mkdir my-hyperbuild-project
cd my-hyperbuild-project
claude
```

Log in with your Claude account when prompted (first time only).

### 3. Create a CLAUDE.md File

Add a `CLAUDE.md` to your project root. This file tells Claude your stack, standards, and commands:

```markdown
# Project: HyperBuild Demo App

## Tech Stack
- Frontend: React + TypeScript
- Backend: Node.js (Express)
- Database: SQLite

## Commands
- npm run dev: Start local server
- npm test: Run tests
- npm run build: Production build

## Coding Standards
- Use functional components only
- All API responses use { success, data, error } format
- Write tests for all new features
- Use async/await (no raw promises)
```

### 4. Build a Mini Project

Use Claude Code to scaffold and build. Try these prompts:

```
"Initialize a Vite + TypeScript project with React and Tailwind CSS"
"Add a login page with email and password authentication"
"Create a REST API for managing tasks with CRUD operations"
"Write unit tests for the task API endpoints"
"Refactor all utility functions to use async/await"
```

### 5. Essential Claude Code Commands

| Command | Description |
|---------|-------------|
| `/help` | Show all available commands |
| `/plan` | Think and plan before acting (use for complex tasks) |
| `/context` | See what context Claude understands |
| `/model` | Switch between Opus (strongest) and Sonnet (fast) |
| `/clear` | Reset conversation |
| `/skills` | List task shortcuts |

### 6. Practice Iterative Development

1. **Feature Addition:** "Add a dashboard page that shows task statistics"
2. **Refactoring:** "Refactor the auth service to use JWT tokens"
3. **Testing:** "Write integration tests for the login flow"
4. **Debugging:** "Find and fix all TODO comments in the codebase"

---

## Tips for Success

- **Be explicit:** "Rewrite the `/auth` service, follow existing code style, and update related tests"
- **Start small:** Give stepwise instructions for big tasks
- **Use Plan Mode:** `/plan` for complex multi-file changes
- **Review always:** Read Claude's proposed diff before allowing a commit
- **Use Git:** Easy to roll back if you don't like a change

---

## Resources

| Resource | Link |
|----------|------|
| Official Quickstart | [code.claude.com/docs/en/quickstart](https://code.claude.com/docs/en/quickstart) |
| Beginner Tutorial (2026) | [codewithmukesh.com/blog/claude-code-for-beginners](https://codewithmukesh.com/blog/claude-code-for-beginners/) |
| Complete Setup Guide | [otomasi.ai/en/blog/claude-code-tutorial-2026](https://otomasi.ai/en/blog/claude-code-tutorial-2026) |
| Video Walkthrough | [YouTube: Claude Code Setup That Works](https://www.youtube.com/watch?v=P-5bWpUbO60) |
| Dev.to Step-by-Step | [dev.to/ayyazzafar](https://dev.to/ayyazzafar/claude-code-tutorial-for-beginners-2026-from-installation-to-building-your-first-project-1lma) |
| Beginner-to-Pro Guide | [nocode.mba/articles/claude-code-tutorial](https://www.nocode.mba/articles/claude-code-tutorial) |

---

## ✅ Deliverable

A working mini-project built entirely using Claude Code, committed to a GitHub repository with a proper CLAUDE.md configuration file.

---

[← Back to Program Overview](../README.md) | [Next: Module 2 — Cowork Workflows →](module-02-cowork-workflows.md)