# Bookassist Brand Hub

This repository contains Bookassist brand assets, style guidelines, and Claude Code configuration to help the team produce consistent, on-brand content across all channels.

---

## What's in this repo

- **Style Guide 2025 V4.md** — Colours, fonts, logos, and key terminology
- **CLAUDE.md** — Brand context for Claude Code (see setup instructions below)

---

## Setup Guide

Follow these steps to get set up exactly as the previous team member was working.

### 1. Install Node.js and npm

Node.js is required to install Claude Code and run any JavaScript-based projects.

Download the **LTS version** from: https://nodejs.org/en/download

Run through the installer. Once done, verify in terminal:
```bash
node --version
npm --version
```

---

### 2. Install Git

Git is required to clone repos and push changes to GitHub.

Download from: https://git-scm.com/downloads — select **macOS**

Verify in terminal:
```bash
git --version
```

Configure your identity (use your Bookassist email):
```bash
git config --global user.name "Your Name"
git config --global user.email "you@bookassist.com"
```

---

### 3. Install Claude Code

Once Node.js is installed, run this in your terminal:
```bash
npm install -g @anthropic-ai/claude-code
```

Then launch it:
```bash
claude
```

Sign in with your Anthropic account when prompted. If you don't have one, create one at: https://claude.ai

---

### 4. Install gh-pages (for deploying projects to GitHub Pages)

gh-pages is required for deploying web projects to GitHub Pages.

```bash
npm install -g gh-pages
```

---

### 5. Add brand context to your Claude Code

Claude Code uses a file called `CLAUDE.md` in your home directory as a permanent briefing — it loads automatically in every conversation so you never need to repeat brand rules.

**If you don't have a `~/CLAUDE.md` yet:**

Copy the `CLAUDE.md` file from this repo directly into your home directory:
```bash
cp CLAUDE.md ~/CLAUDE.md
```

**If you already have a `~/CLAUDE.md` with your own content:**

Open the `CLAUDE.md` from this repo, copy everything inside it, and paste it at the bottom of your existing `~/CLAUDE.md` so your current content is preserved.

To open and edit your existing file in terminal:
```bash
open ~/CLAUDE.md
```

Or ask Claude Code directly: *"Can you open and show me my CLAUDE.md file?"*

---

### 6. Clone this repo

```bash
git clone https://github.com/BookassistMarketing/Bookassist-Brand.git
```

---

## Verify your setup

Once everything is installed, run this in your terminal to confirm everything is working:

```bash
node --version && npm --version && git --version && claude --version
```

You should see version numbers returned for all four. If anything is missing or shows an error, go back to the relevant step above and reinstall.

---

## Using Claude Code for brand content

Once set up, Claude Code will automatically follow Bookassist brand guidelines whenever you create:

- Social media posts
- Emails
- Blog posts
- Presentations
- Any other marketing or brand content

You do not need to remind it — the brand rules are loaded from your `CLAUDE.md` automatically.

---

## Recommended Claude Code Plugins

Once Claude Code is installed, run `/plugin` in Claude Code and search for each of these to install:

| Plugin | Purpose |
|---|---|
| `frontend-design` | Production-grade UI and web design |
| `superpowers` | Advanced planning, debugging, and development workflows |
| `playwright` | Browser automation and testing |
| `github` | GitHub integration |
| `skill-creator` | Create and manage custom Claude Code skills |
| `asana` | Manage marketing tasks and campaigns directly from Claude Code |
| `hookify` | Automate repetitive behaviours and prevent unwanted Claude actions |
| `slack` | Draft and send Slack messages directly from Claude Code |
| `linear` | Issue and project tracking |
| `context7` | Pulls in up-to-date documentation for researching tools |

After installing all plugins run `/reload-plugins` to activate them.

---

## Key contacts

Add team contacts here as needed.
