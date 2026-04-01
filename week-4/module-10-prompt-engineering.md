# Module 10: Prompt Engineering Mastery

**⏱ Estimated Time:** 3-4 hours  
**Week:** 4 | **Focus:** Mastery & Final Build

---

## Learning Objectives

- Understand the core principles behind effective prompts for any AI model
- Master key techniques: zero-shot, few-shot, chain-of-thought, role-based, and system prompts
- Build a reusable prompt template library for coding, writing, analysis, and debugging
- Apply advanced patterns: self-critique loops, tree of thought, and meta-prompting
- Learn to test, iterate, and version-control your prompts
- Identify and avoid common anti-patterns that waste tokens and produce poor results

---

## Why Prompt Engineering Matters

The same AI model can produce wildly different outputs depending on how you ask. Prompt engineering is the skill of **crafting inputs that reliably produce high-quality outputs**.

Think of it this way:

| Analogy | Without Prompt Engineering | With Prompt Engineering |
|---------|---------------------------|------------------------|
| Search engine | Typing random words | Using advanced search operators |
| Camera | Auto mode, hope for the best | Manual mode, full creative control |
| Cooking | "Make something tasty" | A detailed recipe with measurements |

Prompt engineering is not about tricks — it is about **clear communication with a machine**.

---

## Prerequisites

- Access to at least one AI model (Claude, ChatGPT, or Gemini)
- Completed Modules 1-8 (you will use your existing projects as practice material)
- A text editor or Notion page to build your prompt library

---

## Core Principles

Before diving into techniques, internalise these five principles:

| # | Principle | Explanation |
|---|-----------|------------|
| 1 | **Be specific** | Vague prompts get vague answers. State exactly what you want. |
| 2 | **Provide context** | Tell the model who you are, what you are working on, and why. |
| 3 | **Define the format** | Specify the output structure (bullet points, JSON, table, etc.). |
| 4 | **Set constraints** | Limit length, tone, audience, or scope to focus the output. |
| 5 | **Iterate** | Your first prompt is a draft. Refine based on what comes back. |

---

## Step-by-Step Activities

### Activity 1: Master the Fundamental Techniques (45 minutes)

Work through each technique below. For every technique, write **two prompts** — one for a coding task and one for a writing task — and compare the outputs.

#### Technique 1: Zero-Shot Prompting

Give the model a task with no examples. Relies entirely on the model's training.

```
Write a Python function that validates an email address using regex.
```

**When to use:** Simple, well-defined tasks where the model already knows the pattern.

#### Technique 2: Few-Shot Prompting

Provide 2-3 examples before asking the model to follow the same pattern.

```
Convert these informal messages to professional emails:

Informal: "hey can u send me the report asap"
Professional: "Hi, could you please send me the report at your earliest convenience? Thank you."

Informal: "the meeting is moved to 3pm tmrw"
Professional: "Please note that tomorrow's meeting has been rescheduled to 3:00 PM."

Informal: "im not gonna make it today, feeling sick"
Professional:
```

**When to use:** When you need a specific style, format, or pattern that is easier to show than to describe.

#### Technique 3: Chain-of-Thought (CoT)

Ask the model to reason step-by-step before giving a final answer.

```
A store sells notebooks for $4 each. They offer a 15% discount for orders
of 10 or more. If a teacher buys 25 notebooks, how much do they pay?

Think step-by-step before giving the final answer.
```

**When to use:** Math, logic, debugging, complex analysis — any task where reasoning matters.

#### Technique 4: Role-Based Prompting

Assign the model a specific persona to shape its response style and expertise.

```
You are a senior backend engineer with 15 years of experience in
distributed systems. Review the following API design and identify
potential scalability issues:

[paste your API design here]
```

**When to use:** When you need domain-specific expertise or a particular perspective.

#### Technique 5: System Prompts

System prompts set persistent instructions that apply to the entire conversation.

```
System: You are a technical writing assistant. You write in clear,
concise British English. You always use active voice. You format
output in Markdown. You never use jargon without defining it first.

User: Explain how DNS works.
```

**When to use:** When you need consistent behaviour across multiple messages in a conversation.

---

### Activity 2: Build Your Prompt Template Library (1 hour)

Create a Notion database (or markdown file) called **Prompt Library** with these properties:

| Property | Type | Purpose |
|----------|------|---------|
| Name | Title | Short descriptive name |
| Category | Select | Coding, Writing, Analysis, Debugging, Research, Creative |
| Technique | Select | Zero-shot, Few-shot, CoT, Role-based, System |
| Template | Rich text | The actual prompt with `{{placeholders}}` |
| Notes | Rich text | When to use, tips, variations |
| Rating | Select | ⭐ to ⭐⭐⭐⭐⭐ |

Now create at least **one template per category**:

#### Template: Code Review

```
You are a senior {{language}} developer conducting a code review.

Review the following code for:
1. Bugs and potential runtime errors
2. Security vulnerabilities
3. Performance issues
4. Code style and readability
5. Missing edge cases

For each issue found, provide:
- The line or section affected
- Why it is a problem
- A suggested fix with code

Code to review:
```
{{code}}
```

Prioritise issues from most to least critical.
```

#### Template: Technical Writing

```
Write a {{document_type}} about {{topic}}.

Audience: {{audience}}
Tone: {{tone}}
Length: {{length}}

Requirements:
- Use clear, simple language
- Include practical examples
- Structure with headers, bullet points, and tables where appropriate
- End with actionable next steps

Additional context: {{context}}
```

#### Template: Debugging

```
I have a bug in my {{language}} application.

**What should happen:** {{expected_behaviour}}
**What actually happens:** {{actual_behaviour}}
**Error message (if any):** {{error}}

**Code:**
```
{{code}}
```

**What I have already tried:**
{{attempts}}

Please:
1. Identify the root cause
2. Explain why this bug occurs
3. Provide a fix with code
4. Suggest how to prevent similar bugs in the future
```

#### Template: Data Analysis

```
Analyse the following data and provide insights:

**Data:** {{data}}
**Context:** {{context}}
**Questions to answer:**
1. {{question_1}}
2. {{question_2}}
3. {{question_3}}

Present your analysis as:
- Executive summary (3 sentences)
- Key findings (bullet points)
- Detailed analysis with supporting evidence
- Recommendations (numbered list)
- Caveats and limitations
```

#### Template: Research Summary

```
Research the topic: {{topic}}

Provide:
1. A one-paragraph overview
2. Key facts and statistics (with sources where possible)
3. Current state and recent developments
4. Different perspectives or debates
5. Practical implications for {{audience}}
6. 5 recommended resources for further reading

Format as a structured document with clear headers.
```

#### Template: Creative Brainstorming

```
I need {{number}} creative ideas for {{project}}.

Context: {{context}}
Constraints: {{constraints}}
Target audience: {{audience}}

For each idea, provide:
- A catchy name
- One-sentence description
- Why it could work
- Potential challenges
- First step to implement

Aim for a mix of safe, moderate, and bold ideas.
```

---

### Activity 3: Advanced Patterns (45 minutes)

#### Pattern 1: Self-Critique Loop

Ask the model to generate an answer, then critique and improve it.

```
Step 1: Write a product description for {{product}}.
Step 2: Now critique your description. What is weak? What is missing?
         What could be more compelling?
Step 3: Rewrite the description incorporating your critique.
```

This pattern consistently produces higher-quality outputs than a single pass.

#### Pattern 2: Tree of Thought

Explore multiple solution paths before committing to one.

```
I need to architect a notification system for a mobile app.

Generate 3 different approaches:
- Approach A: [describe approach]
- Approach B: [describe approach]
- Approach C: [describe approach]

For each approach, evaluate:
- Complexity to implement
- Scalability
- User experience
- Cost

Then recommend the best approach with justification.
```

#### Pattern 3: Meta-Prompting

Ask the AI to help you write a better prompt.

```
I want to use AI to help me {{goal}}.

Write me an optimised prompt that I can use to get the best possible
result. Include:
- A clear role assignment
- Specific instructions
- Output format requirements
- Examples if helpful
- Constraints and guardrails
```

This is surprisingly effective — the model often knows what it needs to perform well.

#### Pattern 4: Prompt Chaining

Break complex tasks into a sequence of simpler prompts, passing output from one to the next.

```
Prompt 1: "List the 5 most important features for a project management tool"
    ↓ (output becomes input)
Prompt 2: "For each feature, write user stories in the format: As a [user], I want [goal], so that [benefit]"
    ↓ (output becomes input)
Prompt 3: "Estimate the development effort for each user story (S/M/L) and suggest a priority order"
```

---

### Activity 4: Testing and Iterating (30 minutes)

Good prompt engineers test systematically. Create a simple testing framework:

**Step 1: Define success criteria**

Before writing a prompt, decide what "good" looks like:

| Criterion | How to Measure |
|-----------|---------------|
| Accuracy | Is the information correct? |
| Completeness | Does it cover all required points? |
| Format | Does it match the requested structure? |
| Tone | Is it appropriate for the audience? |
| Actionability | Can you use the output immediately? |

**Step 2: Test with variations**

Take one of your templates and test it with:
- Different models (Claude vs. ChatGPT vs. Gemini)
- Different levels of detail in the input
- Different constraint settings (length, tone, format)

**Step 3: Document what works**

Update your Prompt Library with:
- Which model works best for each template
- Common failure modes and how to fix them
- Version history (keep old versions for comparison)

---

### Activity 5: Anti-Patterns to Avoid (15 minutes)

Review these common mistakes and check your own prompts against them:

| Anti-Pattern | Problem | Fix |
|-------------|---------|-----|
| **Vague instructions** | "Make it better" | Specify what "better" means: clearer, shorter, more technical |
| **Overloading** | Asking 10 things in one prompt | Break into a chain of focused prompts |
| **No format spec** | Getting prose when you wanted bullet points | Always specify the output format |
| **Assuming context** | Model does not know your project | Provide relevant background every time |
| **Ignoring the output** | Accepting the first response as-is | Always review, critique, and iterate |
| **Prompt stuffing** | Adding unnecessary words hoping for better results | Be concise; every word should earn its place |
| **Temperature neglect** | Using default settings for all tasks | Use low temperature for factual tasks, higher for creative |
| **No examples** | Describing a complex format in words | Show 1-2 examples instead |

---

## Tips & Best Practices

- **Start simple, add complexity:** Begin with a basic prompt and layer in constraints only as needed
- **Use delimiters:** Separate instructions from content with `---`, triple backticks, or XML tags
- **Specify what NOT to do:** "Do not include disclaimers" or "Do not use passive voice" can be as valuable as positive instructions
- **Version your prompts:** Keep a changelog in your Prompt Library — small wording changes can have big effects
- **Match model to task:** Use Claude for long documents and analysis, GPT-4o for coding, Gemini for multimodal tasks
- **Reuse system prompts:** Build a collection of system prompts for your most common workflows and load them at the start of each conversation
- **Share and collaborate:** Prompts are shareable assets — maintain a team prompt library if you work with others

---

## Resources

| Resource | Link |
|----------|------|
| OpenAI Prompt Engineering Guide | [platform.openai.com/docs/guides/prompt-engineering](https://platform.openai.com/docs/guides/prompt-engineering) |
| Anthropic Prompt Engineering Docs | [docs.anthropic.com/en/docs/build-with-claude/prompt-engineering](https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering) |
| Learn Prompting | [learnprompting.org](https://learnprompting.org) |
| Prompting Guide | [promptingguide.ai](https://www.promptingguide.ai) |
| Brex Prompt Engineering Guide | [github.com/brexhq/prompt-engineering](https://github.com/brexhq/prompt-engineering) |
| Awesome ChatGPT Prompts | [github.com/f/awesome-chatgpt-prompts](https://github.com/f/awesome-chatgpt-prompts) |

---

## Deliverables

1. **Technique Practice:** At least 2 prompts per technique (zero-shot, few-shot, CoT, role-based, system) tested and saved
2. **Prompt Library:** A Notion database or markdown file with at least 6 reusable prompt templates (one per category)
3. **Advanced Pattern:** At least 1 self-critique loop, 1 tree-of-thought, or 1 meta-prompt tested and documented
4. **Testing Results:** A comparison of the same prompt across 2+ models with notes on which performed best
5. **Anti-Pattern Audit:** Review your prompts from Modules 1-9 and identify 3 that could be improved using techniques from this module

---

[Previous: Module 9 Automation](module-09-automation.md) | [Back to Program Overview](../README.md) | [Next: Module 11 AI Reading List](module-11-ai-reading-list.md)