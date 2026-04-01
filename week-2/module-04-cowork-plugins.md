# Module 4: Optimize Cowork (Plugins + Skills)

**⏱ Estimated Time:** 3-4 hours  
**Week:** 2 | **Focus:** AI Agents & Plugins

---

## Learning Objectives

- Install and configure Cowork plugins and connectors
- Create custom skills for repeated workflows
- Chain multiple plugins for complex automations

---

## What are Plugins and Skills in Cowork?

Building on Module 2, this module takes your Cowork setup to the next level:

- **Plugins:** Extensions that give Cowork access to external tools and data sources (Google Drive, Slack, databases, APIs, etc.)
- **Skills:** Reusable task templates that you define once and trigger repeatedly with a simple command
- **Connectors:** Bridges between Cowork and third-party services for real-time data flow

Think of plugins as Cowork's hands (reaching external tools) and skills as its muscle memory (repeating learned tasks).

---

## Prerequisites

- Completed Module 2 (Cowork Workflows)
- Claude Desktop with Cowork tab active
- Accounts for services you want to connect (Google, Slack, Notion, etc.)

---

## Step-by-Step Activities

### Activity 1: Browse and Install Plugins

1. Open Claude Desktop and go to the **Cowork** tab
2. Navigate to the **Plugins** section
3. Browse available plugins by category:

| Category | Example Plugins |
|----------|----------------|
| **Productivity** | Google Drive, Notion, Todoist |
| **Communication** | Slack, Gmail, Discord |
| **Data** | Google Sheets, Airtable, CSV Reader |
| **Development** | GitHub, Jira, Linear |
| **Content** | WordPress, Medium, SEO Analyzer |
| **Document** | PDF Extractor, OCR, Document Converter |

4. Install 2-3 plugins relevant to your workflow:
   - Click **Install** on the plugin
   - Authenticate with your account (OAuth flow)
   - Configure plugin settings and permissions

### Activity 2: Configure Plugin Integrations

**Example 1: Google Drive Plugin**
```
Configure the Google Drive plugin:
1. Authenticate with your Google account
2. Set default folder: "HyperBuild Projects"
3. Permissions: Read and Write
4. Auto-sync: Enabled for /workspace folder
```

**Example 2: Slack Plugin**
```
Configure the Slack plugin:
1. Connect to your Slack workspace
2. Set default channel: #hyperbuild-updates
3. Notification triggers: When a report is generated
4. Message format: Summary with link to full document
```

**Example 3: GitHub Plugin**
```
Configure the GitHub plugin:
1. Authenticate with your GitHub account
2. Set default repository: your-username/hyperbuild-project
3. Auto-commit: Disabled (review first)
4. Issue tracking: Enabled
```

### Activity 3: Create Custom Skills

Skills are reusable workflows you define once and trigger anytime.

**Skill 1: Daily Standup Generator**
```
Create a skill called "standup":

When triggered:
1. Check my Todoist for tasks completed yesterday
2. Check my Google Calendar for today's meetings
3. Scan my /project-files folder for recent changes
4. Generate a standup update in this format:
   - Yesterday: [completed tasks]
   - Today: [planned tasks from calendar + todo]
   - Blockers: [any overdue items]
5. Post to Slack #standup channel
```

**Skill 2: Research Digest**
```
Create a skill called "research-digest":

When triggered:
1. Read all new files in /research-inbox folder
2. For each file, generate a 2-sentence summary
3. Categorize by topic tags
4. Compile into a digest document
5. Save as "digest-{YYYY-MM-DD}.md" in /research-archive
6. Delete processed files from /research-inbox
```

**Skill 3: Meeting Prep**
```
Create a skill called "meeting-prep":

When triggered with a meeting name:
1. Search my Google Drive for related documents
2. Check previous meeting notes in /meetings folder
3. Compile a prep document with:
   - Agenda items from calendar invite
   - Summary of last meeting's action items
   - Relevant document highlights
   - Suggested talking points
4. Save to /meetings/{meeting-name}-prep-{date}.md
```

### Activity 4: Chain Plugins Together

Create a multi-plugin workflow:

```
Weekly Project Report Pipeline:

1. [GitHub Plugin] Pull this week's commits and PRs
2. [Google Sheets Plugin] Read project timeline and milestones
3. [Slack Plugin] Collect important messages from #project channel
4. [Cowork] Synthesize all data into a weekly report
5. [Google Drive Plugin] Save report to shared team folder
6. [Slack Plugin] Post summary with link to #project-updates
```

---

## Testing and Debugging

### Test Each Plugin Individually
Before chaining, verify each plugin works:
```
Test Google Drive: "List the 5 most recent files in my HyperBuild folder"
Test Slack: "Send a test message to #hyperbuild-updates"
Test GitHub: "Show my last 3 commits"
```

### Debug Common Issues

| Issue | Solution |
|-------|----------|
| Plugin not connecting | Re-authenticate; check OAuth permissions |
| Slow response | Reduce the scope of data being fetched |
| Incorrect data | Add more specific instructions; use filters |
| Permission denied | Check plugin settings; re-grant access |
| Skill not triggering | Verify skill name and trigger phrase exactly |

---

## Best Practices

1. **Start Simple:** Get one plugin working before chaining
2. **Test Incrementally:** Add one step at a time to workflows
3. **Document Skills:** Write clear descriptions so you remember what each does
4. **Set Boundaries:** Limit plugin permissions to only what is needed
5. **Review Outputs:** Always check automated outputs before they reach external services
6. **Version Control:** Keep backups of your skill definitions

---

## Resources

| Resource | Link |
|----------|------|
| Cowork Plugins Guide | [cohorte.co](https://www.cohorte.co/ai-articles/how-to-set-up-claude-cowork-files-instructions-plugins-and-connectors-2026) |
| Anthropic Cowork Product | [anthropic.com/product/claude-cowork](https://www.anthropic.com/product/claude-cowork) |
| Cowork Features Walkthrough | [geeky-gadgets.com](https://www.geeky-gadgets.com/claude-cowork-features-workspace/) |
| Claude Help Center | [support.claude.com](https://support.claude.com/en/articles/13345190-get-started-with-cowork) |

---

## Deliverables

1. **Plugin Setup:** 3+ active plugins installed, authenticated, and tested individually
2. **Custom Skills:** At least 1 custom skill that you can trigger on command
3. **Chained Workflow:** 1 multi-plugin workflow that chains 2+ plugins together
4. **Documentation:** Written guide for your setup so a teammate could replicate it

---

[Previous: Module 3 Perplexity](../week-1/module-03-perplexity.md) | [Back to Program Overview](../README.md) | [Next: Module 5 OpenClaw](module-05-openclaw.md)