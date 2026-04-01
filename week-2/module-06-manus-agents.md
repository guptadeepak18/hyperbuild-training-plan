# Module 6: Try Basic Agentic Tools (Manus)

**⏱ Estimated Time:** 3-4 hours  
**Week:** 2 | **Focus:** AI Agents & Plugins

---

## Learning Objectives

- Understand agentic AI concepts (autonomy, planning, tool use)
- Set up and use Manus AI for task automation
- Create agents for real-world use cases

---

## What is Agentic AI?

Before diving into Manus, let's understand the core concept:

**Traditional AI (Chat):**
- You ask a question, AI gives an answer
- One input, one output
- No memory between sessions
- Cannot take actions in the real world

**Agentic AI:**
- You define a goal, AI plans and executes multiple steps
- Reasons, decides, and acts autonomously
- Uses tools (browse web, send emails, access files)
- Monitors results and adapts its approach
- Can run on schedules or respond to events

Think of it as the difference between asking someone for directions vs. hiring a driver who plans the route, handles traffic, and gets you there.

---

## What is Manus AI?

Manus is an **AI agent platform** that lets anyone (even non-coders) create autonomous agents for task automation. Key features:

- **Agent Library:** Pre-built agents for common workflows
- **Custom Agents:** Build your own with natural language instructions
- **Multi-Tool Access:** Agents can browse the web, read files, call APIs, and more
- **Trigger System:** Run agents manually, on schedule, or based on events
- **Execution Logs:** Full transparency into what the agent did and why
- **Autonomy Levels:** Manual, assisted, or fully autonomous execution

---

## Prerequisites

- Manus AI account ([manus.app](https://manus.app))
- A clear use case or task you want to automate
- Basic understanding of workflows (from Modules 2 and 4)

---

## Step-by-Step Activities

### Activity 1: Account Setup and Interface Tour

1. Go to [manus.app](https://manus.app) and create an account
2. Complete profile setup and verify your email
3. Explore the main interface:

| Section | Purpose |
|---------|---------|
| **Dashboard** | Home for launching and managing agents |
| **Agent Library** | Pre-built templates and community agents |
| **My Agents** | Your custom or saved agent setups |
| **Execution Logs** | Monitor agent runs, check errors, review outputs |
| **Settings** | API keys, integrations, preferences |

### Activity 2: Try Pre-Built Agents

Start with 2 agents from the library to understand how they work:

**Agent 1: Research Assistant**
1. Go to Agent Library
2. Find "Research Assistant" or similar template
3. Give it a task:
   ```
   Research the top 5 AI agent frameworks in 2026.
   For each, provide: name, description, pricing,
   key features, and GitHub stars (if open source).
   Output as a comparison table.
   ```
4. Watch the execution log as it works
5. Review the output and note how it planned its steps

**Agent 2: Content Summarizer**
1. Find "Content Summarizer" or "Article Digest" template
2. Give it a task:
   ```
   Go to Hacker News (news.ycombinator.com) and find
   the top 5 AI-related posts from today. For each,
   summarize the article in 2 sentences and rate its
   relevance to someone learning AI tools.
   ```
3. Observe how it browses, reads, and synthesizes

### Activity 3: Create Your First Custom Agent

**Build a "Daily Briefing" Agent:**

1. Click **Create New Agent**
2. Name it: "Daily Briefing Bot"
3. Write the agent instructions:

```
You are my daily briefing assistant. When triggered:

1. Check the latest AI news from these sources:
   - Hacker News (AI category)
   - TechCrunch (AI section)
   - The Batch newsletter (deeplearning.ai)

2. Select the top 5 most important stories

3. For each story, provide:
   - Headline
   - Source
   - 2-sentence summary
   - Why it matters (1 sentence)

4. End with a "Today's Action Item" - one thing I should
   do or learn based on today's news

5. Format as a clean, scannable briefing document
```

4. Set the autonomy level to **Assisted** (agent works but asks before major decisions)
5. Test with a manual trigger
6. Review output and refine instructions

### Activity 4: Configure Triggers

Set up different trigger types for your agents:

**Manual Trigger:**
- Click "Run" whenever you want the agent to execute
- Best for: one-off tasks, testing

**Scheduled Trigger:**
```
Schedule: Every weekday at 8:00 AM
Agent: Daily Briefing Bot
Output: Save to /briefings folder + send email summary
```

**Event-Based Trigger:**
```
Trigger: When a new file is added to /inbox folder
Agent: Document Processor
Action: Summarize, categorize, and move to appropriate folder
```

### Activity 5: Build an Advanced Agent

**"Competitor Monitor" Agent:**

```
You are my competitor monitoring agent.

Targets: [Company A], [Company B], [Company C]

When triggered (weekly):
1. Search for recent news about each target company
2. Check their social media for announcements
3. Look for new product launches or feature updates
4. Check job postings for hints about strategy

For each competitor, provide:
- Latest news summary (3 bullets)
- Notable social media activity
- Product/feature updates
- Strategic signals from job postings

End with:
- Competitive landscape summary
- Recommended actions for our team
- Risk alerts (if any)

Format as a professional competitive intelligence brief.
```

---

## Understanding Agent Execution

When an agent runs, it follows this cycle:

```
Goal Received
    |
    v
Plan Steps (break goal into tasks)
    |
    v
Execute Step 1 --> Observe Result
    |
    v
Decide: Continue / Adjust / Ask for Help
    |
    v
Execute Step 2 --> Observe Result
    |
    v
... (repeat until goal achieved)
    |
    v
Compile Final Output
    |
    v
Deliver Results
```

**Key Concepts:**
- **Planning:** Agent breaks your goal into actionable steps
- **Tool Use:** Agent selects appropriate tools for each step
- **Observation:** Agent checks if each step succeeded
- **Adaptation:** Agent adjusts its plan based on results
- **Completion:** Agent compiles and delivers final output

---

## Best Practices

1. **Start with clear goals:** Vague goals lead to vague results
2. **Be specific about output format:** Tell the agent exactly how you want results structured
3. **Use assisted mode first:** Review agent decisions before going fully autonomous
4. **Monitor early runs:** Watch execution logs to catch issues early
5. **Iterate on instructions:** Refine agent prompts based on output quality
6. **Set guardrails:** Define what the agent should NOT do
7. **Test with safe data:** Use test accounts and non-sensitive data initially

---

## Troubleshooting

| Issue | Solution |
|-------|----------|
| Agent produces wrong output | Make instructions more specific and structured |
| Agent gets stuck in a loop | Add a step limit or timeout in settings |
| Agent fails on a step | Check execution log for the specific error |
| Agent takes too long | Reduce scope or break into smaller sub-agents |
| Output format is messy | Add explicit formatting examples in instructions |
| Agent cannot access a site | Check if the site blocks bots; try alternative sources |

---

## Resources

| Resource | Link |
|----------|------|
| Manus AI Platform | [manus.app](https://manus.app) |
| Manus Documentation | Check Manus Help Center / Blog |
| Agentic AI Concepts | Search "Agentic AI explained 2026" on YouTube |
| Agent Design Patterns | Search "AI agent design patterns" on Google |
| Community Examples | Manus Discord / Community Forum |

---

## Deliverables

1. **Pre-Built Agents:** Successfully run 2 pre-built agents from the library with documented results
2. **Custom Agent:** Create 1 custom agent with clear instructions, tested and producing quality output
3. **Trigger Configuration:** Set up at least 1 scheduled or event-based trigger
4. **Execution Log Review:** Document what you learned from reading 3+ execution logs
5. **Iteration Notes:** Show before/after of at least 1 agent instruction refinement

---

[Previous: Module 5 OpenClaw](module-05-openclaw.md) | [Back to Program Overview](../README.md) | [Next: Module 7 AI Business Plan](../week-3/module-07-ai-business-plan.md)