[README (1).md](https://github.com/user-attachments/files/26456334/README.1.md)
<div align="center">

<img src="https://img.shields.io/badge/OpenClaw-Personal%20AI%20Assistant-7F77DD?style=for-the-badge&logoColor=white" alt="OpenClaw"/>

# 🦾 OpenClaw Setup Guide

### *Your personal AI assistant — running on your own machine in under 10 minutes*

[![Setup Time](https://img.shields.io/badge/Setup%20Time-10%20min-1D9E75?style=flat-square)](https://openclaw.ai)
[![Difficulty](https://img.shields.io/badge/Difficulty-Beginner%20Friendly-378ADD?style=flat-square)](https://openclaw.ai)
[![Works On](https://img.shields.io/badge/Works%20On-Mac%20%7C%20Linux%20%7C%20Windows-888780?style=flat-square)](https://openclaw.ai)
[![Chat Via](https://img.shields.io/badge/Chat%20Via-WhatsApp%20%7C%20Telegram%20%7C%20Terminal-25D366?style=flat-square)](https://openclaw.ai)

<br/>

> **OpenClaw** is a personal AI assistant that runs entirely on your own hardware.
> Text it on WhatsApp — it manages your emails, calendar, files, and reminders.
> No subscription lock-in. No data leaving your machine. Fully yours.

<br/>

---

</div>

## 📋 Table of Contents

- [What is OpenClaw?](#-what-is-openclaw)
- [Before You Start](#-before-you-start-prerequisites)
- [Method 1: Ollama (Easiest)](#-method-1-ollama-easiest--recommended)
- [Method 2: NPM (Manual)](#-method-2-npm-manual)
- [Method 3: AWS Lightsail (24/7 Always-On)](#-method-3-aws-lightsail-247-always-on)
- [Connect WhatsApp or Telegram](#-connect-whatsapp-or-telegram)
- [What Can It Do?](#-what-can-it-do)
- [Security Tips](#-security-tips)
- [Troubleshooting](#-troubleshooting)
- [Need Help?](#-need-help)

<br/>

---

## 🤖 What is OpenClaw?

Think of it as hiring a digital employee — except it runs on your laptop, costs almost nothing, and never takes a day off.

| | Details |
|---|---|
| 📱 **Where you talk to it** | WhatsApp, Telegram, Discord, iMessage, or your terminal |
| 🧠 **What it handles** | Emails, calendar, files, web search, reminders, daily briefings |
| 🏠 **Where it runs** | Your own computer or a cheap $5/month server |
| 🔒 **Your data** | Stays on your machine — nothing sent to third parties |
| 💸 **Cost** | Only the AI provider API cost — the app itself is free |

<br/>

---

## ✅ Before You Start (Prerequisites)

You need **three things** before running any command. Get these ready first.

### 1. A Supported Operating System

```
✅ macOS  (any version)
✅ Linux  (Ubuntu, Debian, Arch, etc.)
✅ Windows — requires WSL2 (see note below)
❌ Windows without WSL2 — not supported
```

> **Windows users:** WSL2 lets you run Linux commands inside Windows.
> [Install it here](https://learn.microsoft.com/en-us/windows/wsl/install) — takes about 10 minutes and is a one-time setup.

---

### 2. An AI API Key

OpenClaw needs an AI "brain." Pick one provider and grab an API key.

| Provider | Best For | Link |
|---|---|---|
| **Anthropic (Claude)** ⭐ Recommended | Best reasoning, long context | [console.anthropic.com](https://console.anthropic.com) |
| **OpenAI (GPT-4)** | Widely supported | [platform.openai.com](https://platform.openai.com) |

> **How to get an Anthropic API key (step by step):**
> 1. Create an account at [console.anthropic.com](https://console.anthropic.com)
> 2. Go to **Billing** → add a card (pay-as-you-go, ~$5 lasts weeks for personal use)
> 3. Go to **API Keys** → click **Create Key** → copy and store it safely

---

### 3. Node.js v22+ *(Method 2 only)*

Check your version:
```bash
node --version
# You need: v22.x.x or higher
```

If it's missing or lower:
```bash
# macOS (Homebrew)
brew install node

# macOS / Linux (recommended — version manager)
curl -fsSL https://fnm.vercel.app/install | bash
fnm install 22
```

<br/>

---

## 🚀 Method 1: Ollama (Easiest) — Recommended

**Best for:** First-timers, non-technical founders, anyone who wants it working fast.
**Time:** ~5 minutes. No config files. No Node.js needed.

---

### Step 1 — Install Ollama

**macOS / Linux:**
```bash
curl -fsSL https://ollama.com/install.sh | sh
```

**macOS (Homebrew):**
```bash
brew install ollama
```

**Windows (WSL2 terminal):**
```bash
curl -fsSL https://ollama.com/install.sh | sh
```

> Or download the desktop app directly from [ollama.com](https://ollama.com)

---

### Step 2 — Launch OpenClaw

```bash
ollama run openclaw
```

Ollama will automatically detect and install OpenClaw, show a model selector, and open an interactive terminal chat.

> **Tip:** Choose a cloud model for the best performance and built-in web search.

---

### Step 3 — Complete the Onboarding

The terminal will ask you:
1. Give your assistant a name (e.g. *Jarvis*, *Nova*, *Max*)
2. Tell it how to address you
3. Optionally connect a messaging app

**That's it. Your assistant is live.**

<br/>

---

## 🛠 Method 2: NPM (Manual)

**Best for:** Developers or anyone who wants full control over configuration.
**Time:** ~15 minutes.

---

### Step 1 — Verify Node.js v22+

```bash
node --version
# Must show v22.x.x or higher
```

---

### Step 2 — Install OpenClaw Globally

```bash
npm install -g openclaw
```

**Permission error?**
```bash
sudo npm install -g openclaw
```

**`openclaw` not found after install?**
```bash
export PATH="$(npm bin -g):$PATH"

# Make it permanent
echo 'export PATH="$(npm bin -g):$PATH"' >> ~/.zshrc
source ~/.zshrc
```

---

### Step 3 — Run Onboarding

```bash
openclaw
```

Follow the prompts:
1. Accept the security notice
2. Select **Quick Start**
3. Choose your AI provider
4. Paste your API key
5. Connect a messaging app (or skip for now)
6. Name your assistant

---

### Step 4 — Verify Everything Works

```bash
openclaw daemon restart
sleep 3
openclaw models list
```

You should see models listed (e.g. `anthropic/claude-sonnet-4-6`).

> **Empty list?** Your API key is incorrect or billing is not active. Check your provider console.

---

### Step 5 — Choose Your Interface

**Terminal UI:**
```bash
openclaw tui
```

**Browser UI:**
```bash
# Open in your browser:
http://127.0.0.1:18789
```

<br/>

---

## ☁️ Method 3: AWS Lightsail (24/7 Always-On)

**Best for:** Founders who want their assistant online around the clock, reachable from anywhere.
**Cost:** ~$5–10/month.
**Time:** ~20 minutes.

---

### Step 1 — Create a Lightsail Instance

1. Open [AWS Lightsail](https://lightsail.aws.amazon.com)
2. Click **Create Instance**
3. Select your region
4. Platform → **Linux/Unix**
5. Blueprint → **OpenClaw**
6. Plan → **4 GB RAM** (recommended)
7. Name your instance → **Create**

---

### Step 2 — Set Up AI Permissions

1. Go to the **Getting Started** tab on your instance page
2. Click **Copy the script**
3. Click **Launch CloudShell**
4. Paste and run the script
5. Wait for `Done` in the output

> This creates an IAM role and grants Bedrock AI model access — fully automated.

---

### Step 3 — Open the Web UI and Approve Your Device

1. Click **Open Web UI** on your dashboard
2. `health offline` is normal at first
3. Go to **My OpenClaw → Security tab → Approve** your device
4. Refresh — you'll see `health OK` ✅

---

### Step 4 — Add a Model and Start Chatting

Go to the **Models** tab → **Add Model** → configure your provider → start chatting.

> **Pro tip:** Create a Snapshot after setup (Snapshots tab) as a backup restore point.

<br/>

---

## 📱 Connect WhatsApp or Telegram

*Optional — but makes OpenClaw dramatically more useful. Text it from your phone.*

### WhatsApp

```bash
# 1. Enable WhatsApp and allow your number
openclaw config set channels.whatsapp.enabled true
openclaw config set channels.whatsapp.allowFrom '["+919876543210"]'
# Replace with your number in international format

# 2. Restart
openclaw daemon restart
```

Then scan the QR code:
- WhatsApp → **Settings → Linked Devices → Link a Device**

> ⚠️ Best practice: use a dedicated number, not your personal one.

---

### Telegram

```bash
# 1. Open Telegram → search @BotFather → send /newbot
#    Give it a name → copy the token

# 2. Add token to OpenClaw
openclaw config set channels.telegram.token YOUR_BOT_TOKEN
openclaw daemon restart
```

Open your new bot in Telegram and start chatting.

<br/>

---

## 💡 What Can It Do?

Here are real things you can message your assistant:

```
"What's on my calendar today?"
"Send an email to John saying I'll be 10 minutes late."
"Remind me to follow up with the investor on Friday at 9am."
"Search for the latest AI funding news."
"Summarize the PDF I just sent you."
"Create a GitHub issue for the login bug."
"What tasks do I have open?"
```

OpenClaw supports **skills** (plugins) to extend its capabilities:

| Skill | What it does |
|---|---|
| 📧 Gmail | Read, write, and send emails |
| 📅 Google Calendar | Check and create events |
| 📁 File System | Read and organize local files |
| 🔍 Web Search | Real-time research |
| 🐙 GitHub | Create issues, review PRs |
| 🗒️ Notes & Todos | Track tasks in Markdown |

<br/>

---

## 🔒 Security Tips

Running a personal AI agent is powerful. A few rules keep you safe:

| Rule | Why it matters |
|---|---|
| **Never expose your gateway to the internet** | Bind to `localhost` only. Use SSH tunneling for remote access. |
| **Never give the agent `sudo` access** | It can do everything you need without root. |
| **Don't link personal accounts on shared machines** | Agents with shell access can read environment variables. |
| **Use sandbox mode when testing** | Especially when browsing untrusted websites or reading unknown files. |
| **Run security checks regularly** | `openclaw security check` — built-in misconfiguration scanner. |

<br/>

---

## 🐛 Troubleshooting

**`openclaw` command not found after install**
```bash
export PATH="$(npm bin -g):$PATH"
# Add to ~/.zshrc or ~/.bashrc to make permanent
```

**Models list is empty**
```bash
openclaw models list
# Empty = wrong API key or billing not active
# Verify both in your provider's console
```

**WhatsApp QR code not appearing**
```bash
find /data/.openclaw/browser -name SingletonLock -delete 2>/dev/null
openclaw daemon restart
```

**`health offline` in Web UI**
- Go to Security tab → find your device → click **Approve** → refresh

**Gateway not responding**
```bash
openclaw daemon restart
sleep 3
openclaw status
```

<br/>

---

## 🆘 Need Help?

| Resource | Link |
|---|---|
| 📖 Official Docs | [docs.openclaw.ai](https://docs.openclaw.ai) |
| 💬 Community | [openclaw.ai](https://openclaw.ai) |
| 🐛 Bug Reports | Open an issue on this repo |
| 🔐 Security Issues | Email the maintainers privately |

<br/>

---

<div align="center">

**Built for founders who move fast.**
*If this guide saved you time, drop a ⭐ on the repo.*

<br/>

[![Docs](https://img.shields.io/badge/Read%20the%20Docs-docs.openclaw.ai-7F77DD?style=flat-square)](https://docs.openclaw.ai)
[![License](https://img.shields.io/badge/License-MIT-888780?style=flat-square)](LICENSE)

</div>
