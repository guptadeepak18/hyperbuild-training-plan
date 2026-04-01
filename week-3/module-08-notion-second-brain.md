# Module 8: Build a Notion Second Brain

**⏱ Estimated Time:** 3-4 hours  
**Week:** 3 | **Focus:** Business & Knowledge Systems

---

## Learning Objectives

- Set up a Notion workspace using the PARA method (Projects, Areas, Resources, Archive)
- Build linked databases with custom properties and multiple views
- Create reusable templates for Daily Notes, Meeting Notes, and Learning Notes
- Use Notion AI to accelerate capture, summarisation, and writing
- Establish a weekly review process to keep your Second Brain current

---

## What is a Second Brain?

A "Second Brain" is a trusted external system that stores, organises, and resurfaces everything you learn and need to act on — so your biological brain can focus on thinking rather than remembering.

Tiago Forte's **PARA method** is the most popular framework for structuring a Second Brain:

| Letter | Stands For | What Goes Here |
|--------|-----------|----------------|
| **P** | Projects | Active, time-bound work with a clear outcome |
| **A** | Areas | Ongoing responsibilities with no end date |
| **R** | Resources | Reference material you may use someday |
| **A** | Archive | Completed or inactive items from the other three |

Notion is ideal for a Second Brain because it combines databases, documents, and AI in a single workspace.

---

## Prerequisites

- A free Notion account at [notion.so](https://www.notion.so)
- Completed Module 7 (AI Business Plan) — you will use your business plan as practice content
- Optional: Notion mobile app for quick capture on the go

---

## Step-by-Step Activities

### Activity 1: Set Up Your PARA Workspace (30 minutes)

**Step 1: Create a new Notion page called "Second Brain".**

In the left sidebar click **+ New page**, name it `Second Brain`, and choose **Empty with icon** (pick a 🧠 emoji).

**Step 2: Create the four top-level PARA sections.**

Inside your Second Brain page, create four sub-pages:

```
📁 Projects     — Active work with a finish line
📂 Areas        — Ongoing responsibilities
📚 Resources    — Reference and learning material
🗄️ Archive      — Completed / inactive items
```

**Step 3: Populate each section with real content.**

| Section | Example Entries |
|---------|----------------|
| Projects | HyperBuild Capstone, Launch personal website, Read "Atomic Habits" |
| Areas | Health & Fitness, Finances, Career Development, Side Projects |
| Resources | AI Tools, Productivity Systems, Coding Notes, Book Summaries |
| Archive | Completed job applications, Old course notes, Past projects |

---

### Activity 2: Build Your Core Databases (1 hour)

Notion's superpower is relational databases. Create these three linked databases.

**Database 1: Projects Database**

Create a full-page database (`/database — full page`) named **Projects**. Add these properties:

| Property Name | Type | Options / Notes |
|--------------|------|----------------|
| Status | Select | 🟡 Active, 🟢 Completed, ⏸ On Hold, ❌ Cancelled |
| Area | Relation | Link to Areas database |
| Due Date | Date | Target completion date |
| Priority | Select | 🔴 High, 🟠 Medium, 🟢 Low |
| Energy | Select | 🔋 Deep Work, ⚡ Quick Win, 💬 Collaborative |
| Progress | Number | Percentage (0–100) |

**Database 2: Notes Database**

Create a database named **Notes** with these properties:

| Property Name | Type | Options / Notes |
|--------------|------|----------------|
| Type | Select | 📅 Daily, 📝 Meeting, 📖 Learning, 💡 Idea, 🔗 Reference |
| Project | Relation | Link to Projects database |
| Area | Select | Health, Finance, Career, etc. |
| Tags | Multi-select | Free-form keywords |
| Source | URL | Where the note came from |
| Created | Created time | Auto-populated by Notion |

**Database 3: Areas Database**

Create a simple database named **Areas** with a **Status** (Active / Archived) property and a **Description** rich text field. This is what you link Projects and Notes back to.

---

### Activity 3: Create Reusable Templates (45 minutes)

Templates let you open a new note pre-filled with structure. In your Notes database, click the dropdown arrow next to **New** and select **+ New template**. Create these three.

**Template 1: Daily Note**

```markdown
## ☀️ Daily Note — {{date}}

### 🎯 Top 3 Priorities Today
1. 
2. 
3. 

### 📅 Schedule
| Time | Task |
|------|------|
| 09:00 |  |
| 11:00 |  |
| 14:00 |  |

### 📝 Notes & Thoughts


### 🔗 Quick Links
- [ ] Check inbox
- [ ] Review Projects dashboard
- [ ] Update task statuses

### 🌙 End of Day Reflection
**What went well:**  
**What to improve:**  
**Tomorrow's priority:**  
```

**Template 2: Meeting Notes**

```markdown
## 📅 Meeting: [Title]

**Date:**  
**Attendees:**  
**Project:**  

---

### 🎯 Agenda
1. 
2. 
3. 

### 📝 Discussion Notes


### ✅ Action Items
| Action | Owner | Due |
|--------|-------|-----|
|  |  |  |

### 🔄 Next Meeting
**Date:**  
**Agenda preview:**  
```

**Template 3: Learning Note**

```markdown
## 📖 Learning Note: [Title]

**Source:**  
**Date:**  
**Tags:**  

---

### �� Key Ideas (in my own words)
1. 
2. 
3. 

### 🔗 How This Connects to What I Already Know


### ✅ Actions / Applications


### 📌 Direct Quotes Worth Saving
> 

### ⭐ Rating: /5
```

---

### Activity 4: Add Multiple Views (30 minutes)

Views let your database work for different contexts. In your **Projects** database, add these views:

| View Name | Type | Filter / Sort |
|-----------|------|--------------|
| **🏠 Active Projects** | Board | Filter: Status = Active; Group by: Priority |
| **📅 Timeline** | Timeline | Sort by: Due Date |
| **📋 All Projects** | Table | No filter, show all properties |
| **🔴 Due This Week** | Gallery | Filter: Due Date is within the next 7 days |

In your **Notes** database add:

| View Name | Type | Filter |
|-----------|------|--------|
| **📅 Daily Log** | List | Filter: Type = Daily; Sort: Created descending |
| **📝 Meeting Notes** | List | Filter: Type = Meeting |
| **📖 Learning** | Gallery | Filter: Type = Learning |

---

### Activity 5: Use Notion AI (30 minutes)

Notion AI is built into every page. Press **Space** on a blank line to open the AI menu. Try each of these:

| Prompt | What It Does |
|--------|-------------|
| `Summarise this page` | Creates a TL;DR of long notes |
| `Extract action items` | Finds tasks buried in meeting notes |
| `Improve writing` | Polishes draft text for clarity and tone |
| `Translate to [language]` | Translates content instantly |
| `Explain this simply` | Makes technical notes accessible |
| `Write a project brief for…` | Drafts a new project page from a short description |

**Practice:** Open one of your Module 7 business plan sections, paste it into a Notion page, and use Notion AI to summarise it and extract action items.

---

### Activity 6: Set Up a Weekly Review (15 minutes)

A Second Brain only stays useful if you review it regularly. Create a **Weekly Review** template in your Notes database:

```markdown
## 🔄 Weekly Review — Week of {{date}}

### 1. Clear the Inbox
- [ ] Process all Quick Captures
- [ ] File loose notes into PARA

### 2. Review Projects
- [ ] Update status for each active project
- [ ] Identify any stuck or overdue items
- [ ] Celebrate completed projects → move to Archive

### 3. Review Calendar
- [ ] Look back: what happened this week?
- [ ] Look ahead: what is coming next week?

### 4. Review Areas
- [ ] Any area being neglected?
- [ ] Any new project to spin up?

### 5. Set Intentions
**This week's #1 priority:**  
**One habit to maintain:**  
**One thing to let go of:**  
```

Schedule 30 minutes every Friday for your weekly review.

---

## Quick Capture Methods

Getting information into your Second Brain should take seconds, not minutes.

| Method | How | Best For |
|--------|-----|---------|
| **Notion Web Clipper** | Browser extension — clip any web page | Articles, references, bookmarks |
| **Notion Mobile App** | Open app → Quick Note | Ideas on the go, voice memos |
| **Share to Notion** | Share from any app on mobile | Tweets, screenshots, links |
| **Slack Integration** | Forward Slack messages to Notion | Meeting follow-ups, decisions |
| **/page command** | Type `/page` in any Notion page | Quick sub-page creation |

---

## Tips & Best Practices

- **Don't over-engineer upfront:** Start with the basic PARA structure and add complexity only when you feel the need
- **Quick Capture first, organise later:** Use the mobile app or Web Clipper to capture ideas immediately — file them during your weekly review
- **Progressive summarisation:** When re-reading old notes, bold the most important sentences. This makes future reviews much faster
- **Two-minute rule:** If a note or task takes less than two minutes to process, do it immediately instead of capturing it
- **Relations over tags:** Link databases with Relation properties rather than relying on free-form tags for more powerful filtering
- **Limit active projects:** Keep your Projects section to a manageable number (10–15 max). Move anything you are not actively working on to Archive

---

## Resources

| Resource | Link |
|----------|------|
| Notion | [notion.so](https://www.notion.so) |
| PARA Method by Tiago Forte | [fortelabs.com/blog/para](https://fortelabs.com/blog/para/) |
| Notion Templates Gallery | [notion.so/templates](https://www.notion.so/templates) |
| Notion AI Documentation | [notion.so/help/notion-ai](https://www.notion.so/help/notion-ai) |
| Thomas Frank Explains (YouTube) | [youtube.com/@ThomasFrankExplains](https://www.youtube.com/@ThomasFrankExplains) |
| Building a Second Brain (book) | [buildingasecondbrain.com](https://www.buildingasecondbrain.com) |

---

## Deliverables

1. **PARA Workspace:** A fully structured Notion workspace with Projects, Areas, Resources, and Archive sections
2. **Three Databases:** Projects, Notes, and Areas databases with correct properties and relations
3. **Three Templates:** Daily Note, Meeting Notes, and Learning Note templates tested and working
4. **Multiple Views:** At least 2 views per database configured
5. **Weekly Review:** Weekly Review template created and first review completed
6. **Notion AI Practice:** At least one page summarised and action items extracted with Notion AI

---

[Previous: Module 7 AI Business Plan](module-07-ai-business-plan.md) | [Back to Program Overview](../README.md) | [Next: Module 9 Automation](../week-4/module-09-automation.md)
