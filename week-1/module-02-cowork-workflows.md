# Module 2: Build 1-2 Workflows in Cowork

**⏱ Estimated Time:** 3-4 hours  
**Week:** 1 | **Focus:** Foundations - AI Coding & Workflows

---

## Learning Objectives

- Understand Claude Cowork's agentic workspace model
- Build automated workflows for file management and document creation
- Master the handoff protocol (outcome → inputs → constraints → deliverables)

---

## What is Claude Cowork?

Claude Cowork is Anthropic's **agentic AI workspace** designed for multi-step, knowledge-based tasks on your desktop (Windows/macOS). Unlike simple chatbots, Cowork can:

- **Access and manage** local files and folders
- **Automate document creation** (spreadsheets, presentations, reports)
- **Schedule, repeat, or organize** tasks into projects
- **Use plugins and connectors** for external data/tools
- **Act on standing instructions** rather than one-off prompts

Think of it as a persistent AI assistant that lives in your file system.

---

## Prerequisites

- Claude Pro, Max, Teams, or Enterprise subscription
- Claude Desktop app installed ([claude.com/download](https://claude.com/download))
- A dedicated workspace folder on your machine

---

## Core Concepts

### Folder-Based Context
Cowork reads/writes only within assigned folder boundaries. Start with a clean, dedicated folder to minimize data risks and maximize focus.

### Standing Instructions
Provide persistent guidance to Cowork about your desired outcomes, file organization rules, and task priorities. These persist across sessions.

### The Handoff Protocol
Before running any workflow, define:

| Element | Description |
|---------|-------------|
| **Outcome** | What does "done" look like? |
| **Inputs** | What files, sources, or tools should be used? |
| **Constraints** | Tone, format, must-dos/must-nots |
| **Questions First** | Force Cowork to clarify ambiguities before starting |
| **Deliverables** | Output types, locations, and naming conventions |
| **Review Step** | Have Cowork show a plan for approval before major actions |

---

## Step-by-Step Activities

### Activity 1: Initial Setup

1. **Download Claude Desktop** from [claude.com/download](https://claude.com/download)
2. Open the app and navigate to the **Cowork** tab
3. Create a dedicated workspace folder:
   
   ```
   mkdir ~/HyperBuild-Cowork-Workspace
   ```
4. In Cowork, assign this folder as your working directory
5. Add standing instructions:
   
   ```
   You are my project assistant. Always:
   - Ask clarifying questions before starting a task
   - Show me a plan before making changes
   - Use clear file naming: {YYYY-MM-DD}_{description}
   - Summarize what you did after completing each task
   ```

### Activity 2: Workflow 1 - Document Summarization Pipeline

**Goal:** Feed 5 PDFs/documents and get a structured summary report.

**Setup:**
1. Place 5 PDF files or text documents in your workspace folder under a `/docs` subfolder
2. Give Cowork this instruction:

```
Read all documents in the /docs folder. For each document:
1. Extract the title, author (if available), and date
2. Write a 3-sentence summary
3. Identify 3 key takeaways
4. Rate relevance to [your topic] on a scale of 1-5

Output everything in a single markdown file called "summary-report.md"
with a table of contents at the top.
```

3. Review Cowork's plan before it executes
4. Check the output and provide feedback for iteration

**Expected Output:**
```
summary-report.md
├── Table of Contents
├── Document 1: [Title]
│   ├── Summary (3 sentences)
│   ├── Key Takeaways (3 bullets)
│   └── Relevance Score: X/5
├── Document 2: [Title]
│   └── ...
└── Overall Insights
```

### Activity 3: Workflow 2 - Weekly Report Generator

**Goal:** Cowork reads project files and outputs a formatted progress report.

**Setup:**
1. Create a `/project-files` subfolder with sample project documents (meeting notes, task lists, code changelogs)
2. Give Cowork this instruction:

```
You are my weekly report generator. Every time I say "generate report":
1. Scan all files in /project-files modified in the last 7 days
2. Categorize updates by: Completed, In Progress, Blocked
3. Summarize each category in 2-3 bullet points
4. Add a "Next Week Priorities" section with 3 suggested actions
5. Output as "weekly-report-{YYYY-MM-DD}.md"

Format: Professional, concise, suitable for sharing with a manager.
```

3. Add some sample files with different modification dates
4. Trigger with: "Generate report"
5. Review, iterate, and refine the output

**Expected Output:**
```
weekly-report-2026-03-31.md
├── Summary
├── Completed Items
├── In Progress Items
├── Blocked Items
├── Next Week Priorities
└── Appendix: Files Reviewed
```

---

## Advanced Tips

### Iterative Refinement
- Start with a rough workflow, then improve it over multiple sessions
- Cowork retains memory within a project - it gets better with feedback

### Multi-Step Chains
- Chain workflows: Summarize docs → Extract action items → Create task list → Schedule reminders

### Security Best Practices
- Start with empty/test folders before granting access to sensitive data
- Audit Cowork's outputs before sharing externally
- Restrict folder access to only what's needed for the task

---

## Resources

| Resource | Link |
|----------|------|
| Official Cowork Guide | [support.claude.com](https://support.claude.com/en/articles/13345190-get-started-with-cowork) |
| Cowork Features and Setup (2026) | [geeky-gadgets.com](https://www.geeky-gadgets.com/claude-cowork-features-workspace/) |
| Setup Best Practices | [cohorte.co](https://www.cohorte.co/ai-articles/how-to-set-up-claude-cowork-files-instructions-plugins-and-connectors-2026) |
| Beginners Walkthrough | [nocode.mba](https://www.nocode.mba/articles/claude-cowork-beginners) |
| Anthropic Product Page | [anthropic.com/product/claude-cowork](https://www.anthropic.com/product/claude-cowork) |

---

## Deliverables

1. **Workflow 1:** A working document summarization pipeline that processes 5+ documents into a structured report
2. **Workflow 2:** A weekly report generator that scans project files and outputs a formatted progress report
3. **Documentation:** Written instructions for each workflow so a teammate could replicate them

---

[Previous: Module 1 Claude Code](module-01-claude-code.md) | [Back to Program Overview](../README.md) | [Next: Module 3 Perplexity](module-03-perplexity.md)