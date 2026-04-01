# Module 9: Automate with MCPs, Zapier & n8n

**⏱ Estimated Time:** 4-5 hours  
**Week:** 4 | **Focus:** Mastery & Final Build

---

## Learning Objectives

- Understand Model Context Protocol (MCP) servers and how they extend AI capabilities
- Build basic automations with Zapier (no-code) and n8n (low-code)
- Create 2-3 real-world automations connecting your AI tools together
- Compare automation platforms to choose the right one for each use case

---

## What is Automation?

Automation connects your tools so they work together without manual effort. Instead of copying data between apps, you define triggers and actions that run automatically.

**The Automation Stack for AI Power Users:**

| Layer | Tool | Complexity | Best For |
|-------|------|-----------|----------|
| **Protocol** | MCP Servers | Advanced | Giving AI models direct access to tools and data |
| **No-Code** | Zapier | Beginner | Quick integrations between popular apps |
| **Low-Code** | n8n | Intermediate | Complex workflows with custom logic, self-hosted |
| **Code** | Custom Scripts | Advanced | Unique integrations, full control |

---

## Part 1: Model Context Protocol (MCP) Servers

### What are MCPs?

The Model Context Protocol is an **open standard** that lets AI models (like Claude) connect directly to external tools, databases, and services. Think of MCPs as USB ports for AI — they give your AI assistant hands to reach into other systems.

**Without MCP:** You copy-paste data between your AI and other tools.  
**With MCP:** Your AI reads from and writes to other tools directly.

### How MCPs Work

```
You (prompt) → Claude → MCP Server → External Tool
                  ↑                        |
                  └── Response ←───────────┘
```

### Setting Up MCP Servers with Claude Code

**Step 1: Check available MCP servers**

Popular MCP servers include:

| MCP Server | What It Does |
|-----------|-------------|
| **filesystem** | Read and write files on your computer |
| **github** | Interact with GitHub repos, issues, PRs |
| **postgres** | Query PostgreSQL databases |
| **slack** | Send and read Slack messages |
| **google-drive** | Access Google Drive files |
| **memory** | Persistent memory across conversations |
| **brave-search** | Web search via Brave |
| **fetch** | Make HTTP requests to any API |

**Step 2: Install an MCP server**

Using Claude Code, install the GitHub MCP server:

```bash
claude mcp add github -- npx -y @modelcontextprotocol/server-github
```

Or the filesystem MCP server:

```bash
claude mcp add filesystem -- npx -y @modelcontextprotocol/server-filesystem ~/Documents
```

**Step 3: Verify the connection**

```bash
claude mcp list
```

**Step 4: Use it in Claude Code**

Once connected, Claude can directly interact with the tool:

```
"List my open GitHub issues in guptadeepak18/hyperbuild-training-plan"
"Read the README.md file from my Documents folder"
"Search the web for latest n8n tutorials"
```

### MCP Best Practices

- Only install MCP servers you actively need
- Review permissions before granting access
- Use environment variables for API keys (never hardcode)
- Check the official MCP registry at [github.com/modelcontextprotocol/servers](https://github.com/modelcontextprotocol/servers)

---

## Part 2: Zapier (No-Code Automation)

### What is Zapier?

Zapier connects 6,000+ apps through "Zaps" — automated workflows with a trigger and one or more actions. No coding required.

### Key Concepts

| Concept | Definition |
|---------|-----------|
| **Zap** | An automated workflow |
| **Trigger** | The event that starts the Zap (e.g., new email) |
| **Action** | What happens next (e.g., create a task) |
| **Filter** | A condition that decides if the Zap continues |
| **Path** | Branching logic (if X do A, if Y do B) |
| **Formatter** | Transform data between steps (dates, text, numbers) |

### Activity 1: Set Up Zapier (15 minutes)

1. Go to [zapier.com](https://zapier.com) and create a free account
2. Explore the dashboard and the Zap editor
3. Connect 2-3 apps you use daily (Gmail, Slack, Notion, GitHub, Google Sheets)

### Activity 2: Build Your First Zap (30 minutes)

**Zap: GitHub Star → Slack Notification**

```
Trigger: New star on your GitHub repository
Action: Send a message to your Slack channel

Message format:
"⭐ {user} just starred {repository}! Total stars: {count}"
```

Step-by-step:
1. Click **Create Zap**
2. Trigger: Choose **GitHub** → **New Star**
3. Connect your GitHub account
4. Select your repository
5. Action: Choose **Slack** → **Send Channel Message**
6. Connect your Slack account
7. Select channel and format the message
8. Test and turn on

### Activity 3: Build a Multi-Step Zap (45 minutes)

**Zap: New Form Submission → Google Sheets + Email + Slack**

```
Trigger: New Google Form submission
Action 1: Add row to Google Sheets (log the response)
Action 2: Send email to yourself (summary)
Action 3: Post to Slack (team notification)
```

### Activity 4: AI-Powered Zap (30 minutes)

**Zap: New Email → AI Summary → Notion**

```
Trigger: New email in Gmail (filtered by label or sender)
Action 1: ChatGPT — Summarize the email in 2 sentences
Action 2: Notion — Create a new entry in your Inbox database
         with the summary as the content
```

---

## Part 3: n8n (Low-Code Automation)

### What is n8n?

n8n (pronounced "n-eight-n") is an **open-source, self-hostable** workflow automation tool. It is more powerful and flexible than Zapier, with a visual node-based editor.

**Zapier vs. n8n:**

| Feature | Zapier | n8n |
|---------|--------|-----|
| Hosting | Cloud only | Self-hosted or cloud |
| Pricing | Per-task billing | Free (self-hosted) or flat rate |
| Complexity | Simple, linear | Complex, branching, loops |
| Code support | Limited | Full JavaScript/Python |
| AI nodes | ChatGPT only | Multiple AI providers |
| Open source | No | Yes (fair-code license) |
| Best for | Quick, simple automations | Complex, cost-sensitive workflows |

### Activity 5: Set Up n8n (30 minutes)

**Option A: Cloud (quickest)**
1. Go to [n8n.io](https://n8n.io) and sign up for the cloud version
2. You get a free trial with full features

**Option B: Self-hosted with Docker**
```bash
docker run -it --rm \
  --name n8n \
  -p 5678:5678 \
  -v n8n_data:/home/node/.n8n \
  docker.n8n.io/n8nio/n8n
```

Then open [http://localhost:5678](http://localhost:5678) in your browser.

**Option C: Self-hosted with npm**
```bash
npm install -g n8n
n8n start
```

### Activity 6: Build an n8n Workflow (45 minutes)

**Workflow: RSS Feed → AI Summary → Notion Database**

1. **Trigger Node:** RSS Feed Read
   - URL: `https://news.ycombinator.com/rss`
   - Check every 15 minutes

2. **AI Node:** OpenAI (or Anthropic)
   - Prompt: "Summarize this article in 2 sentences: {{title}} - {{description}}"
   - Model: GPT-4o or Claude Sonnet

3. **Filter Node:** Only continue if the article mentions "AI" or "automation"

4. **Notion Node:** Create Database Item
   - Database: Your Resources database from Module 8
   - Title: Article title
   - Summary: AI-generated summary
   - Source URL: Article link
   - Tags: Auto-tagged based on content

### Activity 7: Build a Complex n8n Workflow (45 minutes)

**Workflow: Daily AI Digest Pipeline**

```
Schedule Trigger (daily at 8 AM)
    |
    v
RSS Feed 1 (Hacker News) ──┐
RSS Feed 2 (TechCrunch) ───┤
RSS Feed 3 (The Batch) ────┘
    |
    v
Merge Node (combine all articles)
    |
    v
AI Node (rank by relevance to "AI tools and automation")
    |
    v
AI Node (generate digest summary)
    |
    v
Split into two paths:
    ├── Email Node (send digest to yourself)
    └── Notion Node (save to Second Brain)
```

---

## Automation Ideas

Here are practical automations to build with what you have learned:

| Automation | Trigger | Actions | Tool |
|-----------|---------|---------|------|
| Meeting notes to tasks | New meeting note in Notion | Extract action items, create tasks in Todoist | n8n |
| Social media monitor | New mention on Twitter/X | Summarize with AI, alert on Slack | Zapier |
| Weekly report | Every Friday at 5 PM | Pull GitHub commits + Notion updates, compile report, email team | n8n |
| Invoice processor | New email with PDF attachment | Extract data with AI, add to Google Sheets, send confirmation | n8n |
| Learning tracker | New article saved in Pocket | Summarize with AI, save to Notion Resources | Zapier |
| Competitor alert | New article mentioning competitor | AI analysis, save to Notion, Slack alert | n8n |

---

## Troubleshooting

| Issue | Solution |
|-------|----------|
| Zapier Zap not triggering | Check trigger app connection; verify filter conditions |
| n8n workflow errors | Click the failed node to see error details; check credentials |
| MCP server not connecting | Verify installation with `claude mcp list`; check API keys |
| Rate limits | Add delay nodes between API calls; batch requests |
| Data format mismatch | Use Formatter (Zapier) or Function node (n8n) to transform data |
| n8n Docker not starting | Check port 5678 is free; verify Docker is running |

---

## Resources

| Resource | Link |
|----------|------|
| MCP Server Registry | [github.com/modelcontextprotocol/servers](https://github.com/modelcontextprotocol/servers) |
| MCP Documentation | [modelcontextprotocol.io](https://modelcontextprotocol.io) |
| Zapier | [zapier.com](https://zapier.com) |
| Zapier University | [zapier.com/university](https://zapier.com/university) |
| n8n | [n8n.io](https://n8n.io) |
| n8n Documentation | [docs.n8n.io](https://docs.n8n.io) |
| n8n Community | [community.n8n.io](https://community.n8n.io) |

---

## Deliverables

1. **MCP Setup:** At least 1 MCP server installed and working with Claude Code
2. **Zapier Automation:** 2 working Zaps (1 simple, 1 multi-step or AI-powered)
3. **n8n Workflow:** 1 working n8n workflow with at least 3 nodes
4. **Comparison Doc:** A written comparison of MCP vs. Zapier vs. n8n with your recommendation for different use cases
5. **Automation Inventory:** A list of 5 tasks in your daily workflow that could be automated, with the recommended tool for each

---

[Previous: Module 8 Notion Second Brain](../week-3/module-08-notion-second-brain.md) | [Back to Program Overview](../README.md) | [Next: Module 10 Prompt Engineering](module-10-prompt-engineering.md)