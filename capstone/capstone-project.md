# Capstone Project: Build Your AI-Powered Portfolio Project

**⏱ Estimated Time:** 8-12 hours (spread across Week 4)  
**Week:** 4 | **Focus:** Mastery & Final Build

---

## Learning Objectives

- Combine every skill from Modules 1-11 into a single, end-to-end project
- Build a real product, tool, or system that solves a genuine problem
- Use AI tools for ideation, development, testing, documentation, and deployment
- Create a portfolio-ready project you can showcase to employers, clients, or collaborators
- Document your process to demonstrate both the outcome and how you got there

---

## What is the Capstone?

The capstone is your graduation project. You will build something **real and useful** — not a toy demo — using the full AI toolkit you have developed over the past four weeks.

This is not a traditional exam. There is no single right answer. You choose the project, scope it, build it, and ship it. The only requirements are:

1. It solves a real problem (yours, your team's, or a community's)
2. It uses at least 5 tools or techniques from the programme
3. It is documented and shareable

---

## Prerequisites

- Completed Modules 1-11 (or at minimum Modules 1-8)
- Your Notion Second Brain set up and populated
- Access to Claude Code, Perplexity, Notion, and at least one automation tool

---

## Step-by-Step Activities

### Phase 1: Ideation (1-2 hours)

#### Step 1: Brainstorm with AI

Use Claude or ChatGPT with this prompt:

```
I have completed a 4-week AI tools training programme. I know how to use:
- Claude Code (AI-assisted coding)
- Cowork Workflows & Plugins (collaborative AI)
- Perplexity (AI-powered research)
- OpenClaw (open-source AI tools)
- Manus Agents (autonomous AI agents)
- Notion + AI (knowledge management)
- Zapier & n8n (automation)
- MCP Servers (AI-tool integration)
- Prompt Engineering (advanced techniques)

I am interested in: {{your_interests}}
My background is: {{your_background}}
Problems I face daily: {{your_problems}}

Generate 10 capstone project ideas that:
1. Solve a real problem
2. Use at least 5 of the tools above
3. Can be built in 8-12 hours
4. Would impress in a portfolio

For each idea, provide:
- Project name
- One-sentence description
- Which tools it uses
- Difficulty (Easy / Medium / Hard)
- Portfolio impact (Low / Medium / High)
```

#### Step 2: Evaluate and Select

Score each idea against these criteria:

| Criterion | Weight | Score (1-5) |
|-----------|--------|-------------|
| **Solves a real problem** | 30% | |
| **Uses 5+ programme tools** | 20% | |
| **Feasible in 8-12 hours** | 20% | |
| **Portfolio impact** | 20% | |
| **Personal excitement** | 10% | |

Pick the project with the highest weighted score.

#### Step 3: Write a Project Brief

Use the prompt template from Module 10:

```
Project Name: {{name}}
Problem Statement: What problem does this solve and for whom?
Solution: What will you build?
Tools & Techniques: Which tools from the programme will you use?
Scope: What is IN scope and what is OUT of scope?
Success Criteria: How will you know it works?
Timeline: Break the 8-12 hours into phases.
```

Save this brief in your Notion Projects database.

---

### Phase 2: Research & Design (1-2 hours)

#### Step 4: Research with Perplexity

Use Perplexity (Module 3) to answer:

- Does a similar tool/project already exist?
- What are the best practices for building this type of project?
- What APIs, libraries, or services will you need?
- What are common pitfalls to avoid?

Save your research as a Learning Note in your Second Brain.

#### Step 5: Design the Architecture

Use Claude Code (Module 1) to help design your system:

```
I am building: {{project_description}}

Help me design the architecture:
1. System components and how they connect
2. Data flow diagram
3. Technology stack recommendations
4. API endpoints (if applicable)
5. Database schema (if applicable)

Keep it simple — this needs to be built in 8-10 hours by one person.
```

#### Step 6: Create a Task Breakdown

Break your project into tasks and add them to your Notion Projects database:

```
Phase 2: Research & Design
  □ Research existing solutions (Perplexity)
  □ Design architecture (Claude Code)
  □ Set up development environment
  □ Create repository on GitHub

Phase 3: Build
  □ Build core feature 1
  □ Build core feature 2
  □ Build core feature 3
  □ Connect automation workflows
  □ Test and debug

Phase 4: Polish & Ship
  □ Write documentation (README)
  □ Record demo video or screenshots
  □ Deploy / publish
  □ Write project retrospective
```

---

### Phase 3: Build (4-6 hours)

This is the core of your capstone. Use the AI tools you have learned to build faster.

#### Step 7: Set Up Your Environment

```bash
# Create a new repository
mkdir capstone-project && cd capstone-project
git init

# Set up Claude Code with MCP servers you need
claude mcp add github -- npx -y @modelcontextprotocol/server-github
claude mcp add filesystem -- npx -y @modelcontextprotocol/server-filesystem .

# Open Claude Code
claude
```

#### Step 8: Build with AI Pair Programming

Use Claude Code as your development partner:

- **Scaffold:** "Set up a {{framework}} project with {{requirements}}"
- **Implement:** "Build the {{feature}} component that does {{description}}"
- **Debug:** "This function returns {{wrong_result}} instead of {{expected_result}}. Here's the code: ..."
- **Test:** "Write tests for the {{module}} covering edge cases"
- **Refactor:** "Refactor this code for better readability and performance"

#### Step 9: Add Automation

Connect your project to automations from Module 9:

| Example Automation | Tool |
|-------------------|------|
| New user signs up → Welcome email + Slack notification | Zapier |
| New data entry → AI processing → Database update | n8n |
| Daily report → AI summary → Email digest | n8n |
| Error alert → Slack notification + GitHub issue | Zapier |
| Content published → Social media post | Zapier |

#### Step 10: Test Thoroughly

Use Claude Code to help with testing:

```
Review my project and:
1. Identify potential bugs or edge cases I have missed
2. Suggest security improvements
3. Check for performance bottlenecks
4. Verify error handling is comprehensive
5. Test the main user flows end-to-end
```

---

### Phase 4: Polish & Ship (2-3 hours)

#### Step 11: Write Documentation

Every portfolio project needs excellent documentation. Use Claude to draft your README:

```markdown
# {{Project Name}}

{{One-sentence description}}

## Problem

{{What problem does this solve?}}

## Solution

{{What does this project do?}}

## Demo

{{Screenshots, GIF, or video link}}

## Architecture

{{Simple diagram or description of how it works}}

## Tech Stack

| Component | Technology |
|-----------|-----------|
| {{component}} | {{technology}} |

## AI Tools Used

| Tool | How It Was Used |
|------|----------------|
| Claude Code | {{how you used it}} |
| Perplexity | {{how you used it}} |
| Notion AI | {{how you used it}} |
| Zapier/n8n | {{how you used it}} |
| MCP Servers | {{how you used it}} |

## Setup & Installation

{{Step-by-step instructions to run the project}}

## What I Learned

{{Key takeaways from building this project}}

## Future Improvements

{{What you would add with more time}}
```

#### Step 12: Deploy or Publish

Get your project live and accessible:

| Project Type | Deployment Option |
|-------------|------------------|
| Web app | Vercel, Netlify, Railway, Render |
| API | Railway, Fly.io, AWS Lambda |
| CLI tool | npm publish, pip publish, or GitHub Releases |
| Automation | Leave running on Zapier/n8n |
| Documentation | GitHub Pages, Notion public page |
| Data project | Google Colab notebook, Streamlit |

#### Step 13: Record a Demo

Create a 2-3 minute demo showing your project in action:

1. **Problem** (15 sec): What problem does this solve?
2. **Demo** (90 sec): Show the product working end-to-end
3. **How it works** (30 sec): Quick architecture overview
4. **AI tools used** (15 sec): Highlight the AI tools that made it possible
5. **What's next** (10 sec): Future improvements

Tools: Loom (free), OBS Studio (free), or QuickTime screen recording.

#### Step 14: Write a Project Retrospective

Create a retrospective note in your Second Brain:

```markdown
## 🔄 Capstone Retrospective

### What I Built
{{Brief description}}

### Tools & Techniques Used
| Tool | Module | How I Used It |
|------|--------|--------------|
| | | |

### What Went Well
1.
2.
3.

### What Was Challenging
1.
2.
3.

### What I Would Do Differently
1.
2.
3.

### Key Learnings
1.
2.
3.

### Time Breakdown
| Phase | Planned | Actual |
|-------|---------|--------|
| Ideation | hrs | hrs |
| Research & Design | hrs | hrs |
| Build | hrs | hrs |
| Polish & Ship | hrs | hrs |
| **Total** | **hrs** | **hrs** |
```

---

## Example Capstone Projects

Need inspiration? Here are fully scoped examples:

### Example 1: AI Content Pipeline (Medium)

**Problem:** Creating consistent content across platforms is time-consuming.  
**Solution:** An automated pipeline that takes a blog post idea, researches it, writes a draft, and schedules distribution.

| Component | Tool |
|-----------|------|
| Research | Perplexity + MCP |
| Writing | Claude Code |
| Knowledge base | Notion Second Brain |
| Scheduling | n8n workflow |
| Distribution | Zapier (Twitter, LinkedIn, email) |
| Prompt templates | Module 10 library |

### Example 2: Personal AI Research Assistant (Medium)

**Problem:** Staying current with AI research papers is overwhelming.  
**Solution:** An automated system that monitors arXiv, summarises new papers, and organises them in Notion.

| Component | Tool |
|-----------|------|
| Paper monitoring | n8n (RSS + arXiv API) |
| Summarisation | Claude via API / MCP |
| Organisation | Notion databases |
| Alerts | Slack via Zapier |
| Search interface | Simple web app via Claude Code |
| Query prompts | Module 10 templates |

### Example 3: Client Onboarding Automation (Easy-Medium)

**Problem:** Onboarding new freelance clients involves repetitive manual steps.  
**Solution:** An automation that creates a project in Notion, sends a welcome email, sets up a Slack channel, and generates a project brief.

| Component | Tool |
|-----------|------|
| Trigger | Google Form / Typeform |
| Project creation | Notion API via n8n |
| Welcome email | Zapier |
| Project brief | Claude AI (via prompt template) |
| Tracking | Notion Projects database |
| Follow-up reminders | Zapier scheduled Zap |

### Example 4: AI-Powered Personal Dashboard (Hard)

**Problem:** Important data is scattered across multiple tools.  
**Solution:** A dashboard that aggregates GitHub activity, Notion tasks, calendar events, and AI-generated insights.

| Component | Tool |
|-----------|------|
| Frontend | Next.js via Claude Code |
| GitHub data | MCP GitHub server |
| Notion data | Notion API |
| Calendar | Google Calendar API |
| AI insights | Claude API |
| Deployment | Vercel |
| Daily digest | n8n automation |

---

## Grading Rubric

Use this rubric to self-assess your capstone:

| Category | Excellent (5) | Good (3) | Needs Work (1) |
|----------|--------------|----------|----------------|
| **Problem & Solution** | Solves a clear, real problem with a well-scoped solution | Solves a problem but scope is too broad or narrow | Problem is unclear or solution is a toy demo |
| **Tool Integration** | Uses 6+ programme tools effectively | Uses 4-5 tools | Uses fewer than 4 tools |
| **Technical Quality** | Clean code, tested, handles edge cases | Works but has some rough edges | Buggy, incomplete, or poorly structured |
| **Documentation** | Excellent README, demo video, clear setup instructions | Good README, some documentation gaps | Minimal or no documentation |
| **Automation** | 2+ automations connected and running | 1 automation working | No automation |
| **Second Brain** | All research, notes, and retrospective in Notion | Some notes in Notion | No Notion integration |
| **Creativity** | Novel approach, goes beyond the basic requirements | Solid but straightforward | Follows an existing tutorial without originality |

**Score yourself:**
- 28-35: Outstanding — portfolio-ready, share it widely
- 20-27: Good — polish one or two areas and it is ready
- Below 20: Keep going — revisit the modules where you scored lowest

---

## Resources

| Resource | Link |
|----------|------|
| Vercel (deployment) | [vercel.com](https://vercel.com) |
| Railway (deployment) | [railway.app](https://railway.app) |
| Loom (screen recording) | [loom.com](https://www.loom.com) |
| GitHub Pages | [pages.github.com](https://pages.github.com) |
| Streamlit (data apps) | [streamlit.io](https://streamlit.io) |
| Project README template | [readme.so](https://readme.so) |

---

## Deliverables

1. **Project Brief:** A clear brief saved in your Notion Projects database
2. **Research Notes:** At least 2 Learning Notes from your Perplexity research
3. **Working Project:** A functional project deployed or published on GitHub
4. **GitHub Repository:** Clean repo with proper README, .gitignore, and commit history
5. **Automation:** At least 1 working automation connected to your project
6. **Documentation:** Complete README with problem statement, demo, setup instructions, and tools used
7. **Demo:** A 2-3 minute recorded demo (Loom or similar)
8. **Retrospective:** A retrospective note in your Notion Second Brain
9. **Second Brain Update:** All project materials organised in your PARA structure

---

## Congratulations! 🎉

If you have reached this point, you have completed the entire HyperBuild Training Plan. You now have:

- ✅ **11 modules** of hands-on AI tool experience
- ✅ A **Notion Second Brain** organising everything you know
- ✅ **Automation workflows** saving you hours every week
- ✅ A **prompt engineering library** for consistent AI results
- ✅ A **curated learning system** to stay current with AI
- ✅ A **portfolio project** demonstrating all of the above

**What is next?**

1. Share your capstone project on LinkedIn, Twitter/X, or your portfolio site
2. Continue your daily learning routine from Module 11
3. Build a second project — speed and quality will improve dramatically
4. Help others learn these tools — teaching is the best way to master them

---

[Previous: Module 11 AI Reading List](../week-4/module-11-ai-reading-list.md) | [Back to Program Overview](../README.md)