# Module 5: Set Up OpenClaw

**⏱ Estimated Time:** 3-4 hours  
**Week:** 2 | **Focus:** AI Agents & Plugins

---

## Learning Objectives

- Install and configure OpenClaw (open-source AI agent gateway)
- Connect OpenClaw to an AI provider and a messaging platform
- Understand skill/tool management and security best practices

---

## What is OpenClaw?

OpenClaw is a **free, open-source AI agent framework** (MIT license) that connects messaging apps (WhatsApp, Telegram, Discord, etc.) to powerful AI models (GPT, Claude, Gemini, or local models via Ollama/LM Studio). It enables you to:

- **Build AI assistants** that live inside your favorite messaging apps
- **Connect multiple AI providers** and switch between them
- **Install skills** for specialized tasks (email, scheduling, social media, etc.)
- **Grant system-level tools** (file access, browser control, command execution)
- **Run locally** on your device for privacy and control

Think of it as your personal AI gateway that turns any chat app into a powerful AI assistant.

---

## System Requirements

- **Node.js:** Version 22+ (LTS recommended)
- **OS:** macOS, Linux, or Windows (via WSL2)
- **RAM:** 2GB minimum (4GB+ recommended)
- **Disk Space:** 1GB+ for basic setup
- **Optional:** Docker for production/isolated deployments

---

## Step-by-Step Activities

### Activity 1: Installation

**Install Node.js (if not already installed):**

On macOS with Homebrew:
```bash
brew install node
```

On macOS/Linux with fnm:
```bash
curl -fsSL https://fnm.vercel.app/install | bash
fnm install 22
```

**Install OpenClaw CLI:**
```bash
npm install -g openclaw@latest
```

If you get permission errors:
```bash
sudo npm install -g openclaw@latest
```

**Verify installation:**
```bash
openclaw --version
```

### Activity 2: Initial Onboarding

Run the onboarding wizard:
```bash
openclaw onboard
```

This will guide you through:

| Step | What You Do |
|------|-------------|
| **1. Choose AI Provider** | Select from Anthropic Claude, OpenAI GPT, Google Gemini, OpenRouter, or local (Ollama) |
| **2. Enter API Key** | Paste your API key (e.g., `sk-ant-...` for Claude, `sk-...` for OpenAI) |
| **3. Select Default Model** | Choose your preferred model (e.g., Claude Sonnet, GPT-4o) |
| **4. Save Configuration** | Config saved to `~/.openclaw/openclaw.json` |

**Get API Keys from:**
- Anthropic: [console.anthropic.com](https://console.anthropic.com)
- OpenAI: [platform.openai.com/api-keys](https://platform.openai.com/api-keys)
- Google: [aistudio.google.com](https://aistudio.google.com)

### Activity 3: Connect a Messaging Platform

```bash
openclaw channels login
```

Follow the prompts for your chosen platform:

**Discord:**
1. Create a bot at [discord.com/developers](https://discord.com/developers/applications)
2. Copy the bot token
3. Paste into OpenClaw when prompted
4. Invite the bot to your server

**Telegram:**
1. Message [@BotFather](https://t.me/botfather) on Telegram
2. Create a new bot and get the token
3. Paste into OpenClaw when prompted

**WhatsApp:**
1. Scan the QR code shown in terminal
2. Link your WhatsApp account
3. Wait for confirmation

### Activity 4: Install and Manage Skills

Skills are pre-built automations for common tasks.

**Browse available skills:**
```bash
openclaw skills list
```

**Install skills:**
```bash
openclaw skills install note-taking
openclaw skills install web-search
openclaw skills install file-manager
```

**Popular Skills to Try:**

| Skill | What It Does |
|-------|-------------|
| **note-taking** | Save and retrieve notes via chat |
| **web-search** | Search the web and summarize results |
| **file-manager** | Read, write, and organize files |
| **scheduler** | Set reminders and schedule tasks |
| **email-manager** | Read and draft emails |
| **social-media** | Draft and schedule social posts |
| **code-helper** | Write, review, and explain code |

### Activity 5: Configure Tools

Tools grant system-level capabilities to OpenClaw. Enable them carefully.

```bash
openclaw tools list
openclaw tools enable browser
openclaw tools enable filesystem
```

**Tool Categories and Risk Levels:**

| Tool | Capability | Risk Level |
|------|-----------|------------|
| **filesystem** | Read/write local files | Medium |
| **browser** | Browse web pages | Medium |
| **exec** | Execute system commands | High |
| **clipboard** | Access clipboard | Low |
| **notifications** | Send desktop notifications | Low |

### Activity 6: Start and Test

**Start OpenClaw:**
```bash
openclaw gateway
```

**Check health:**
```bash
openclaw health
```

**Test via your connected messaging app:**
- Send a message to your bot: "Hello, what can you do?"
- Try a skill: "Take a note: Remember to review Module 6 tomorrow"
- Try a tool: "What files are in my Documents folder?"

---

## Security Best Practices

### Essential Security Checklist

- [ ] **Run as non-root user** (never run OpenClaw as root)
- [ ] **Restrict file access** to specific directories only
- [ ] **Only install trusted skills** from verified sources
- [ ] **Disable high-risk tools** (exec, browser) unless needed
- [ ] **Store API keys securely** (use environment variables or vaults)
- [ ] **Monitor credentials** in `~/.openclaw/credentials`
- [ ] **Check log files** periodically in `/tmp/openclaw/`
- [ ] **Update regularly:** `npm update -g openclaw`

### For Production Deployments

- Use Docker for isolation
- Set up a VPN or identity-based mesh network (e.g., Tailscale)
- Use secrets managers (HashiCorp Vault, AWS Secrets Manager)
- Enable application-level firewalls

---

## Configuration Files Reference

| File | Location | Purpose |
|------|----------|---------|
| Main config | `~/.openclaw/openclaw.json` | AI provider, model, settings |
| Credentials | `~/.openclaw/credentials` | API keys and auth tokens |
| Workspace | `~/.openclaw/workspace` | Persistent memory and data |
| Logs | `/tmp/openclaw/` | Execution logs and debug info |

---

## Troubleshooting

| Issue | Solution |
|-------|----------|
| `openclaw: command not found` | Add npm global bin to your PATH |
| API key rejected | Verify key format and provider match |
| Bot not responding | Check `openclaw health` and restart gateway |
| Skill install fails | Check Node.js version (need 22+) |
| WhatsApp QR expired | Run `openclaw channels login` again |
| Permission errors | Run with `sudo` or fix npm permissions |

---

## Resources

| Resource | Link |
|----------|------|
| Complete Setup Guide | [popularaitools.ai](https://popularaitools.ai/blog/openclaw-setup-guide-2026) |
| Install and Secure (HackerNoon) | [hackernoon.com](https://hackernoon.com/the-complete-openclaw-setup-guide-install-configure-and-secure-your-ai-gateway) |
| Tools and Skills Deep Dive | [yu-wenhao.com](https://yu-wenhao.com/en/blog/openclaw-tools-skills-tutorial/) |
| Security Best Practices | [flaex.ai](https://www.flaex.ai/blog/openclaw-secure-setup-guide-2026-safe-by-default-checklist-implementation) |
| Local Model Setup (LM Studio) | [codersera.com](https://codersera.com/blog/openclaw-lm-studio-setup-guide-2026) |

---

## Deliverables

1. **Working Installation:** OpenClaw installed and passing health check
2. **AI Provider Connected:** At least one AI provider configured and responding
3. **Messaging Platform:** Bot connected to Discord, Telegram, or WhatsApp and responding to messages
4. **Skills Installed:** 2+ skills installed and tested via chat
5. **Security Review:** Completed the security checklist above

---

[Previous: Module 4 Cowork Plugins](module-04-cowork-plugins.md) | [Back to Program Overview](../README.md) | [Next: Module 6 Manus Agents](module-06-manus-agents.md)