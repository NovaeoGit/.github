# AI Skills & Agents Training — Agenda

**Date:** April 16, 2026
**Facilitator:** Derrek

---

## Part 1: The Claude Suite (20 min)

Quick tour of every Claude surface — what each one is for, when to use it, and the plugins/connectors available in each.

### 1.1 Claude Web (claude.ai)
- **Chat** — general conversation, analysis, writing
- **Code** (claude.ai/code) — browser-based Claude Code, same engine as terminal
- Available connectors: Google Drive, GitHub, web search, file uploads

### 1.2 Claude Desktop App
- **Chat mode** — same as web, but native app with system integration
- **Code mode** — full Claude Code in a desktop window
- **Cowork mode** — multi-agent collaboration with shared plans and parallel execution
- Available connectors: MCP servers, local file access, terminal

### 1.3 Claude Code in Terminal
- The CLI — `claude` command
- Full tool access: file read/write, bash, git, web search
- Skills and hooks system
- Same engine powering all surfaces — skills you install work everywhere

### 1.4 IDE Extensions
- VS Code and JetBrains — Claude Code embedded in your editor
- Same skills, same MCP servers, same settings

**Key takeaway:** All surfaces share the same engine. Your skills, settings, and MCP servers carry across all of them.

---

## Part 2: NovaeoGit Organization Tour (15 min)

Walk through the GitHub organization together.

### 2.1 Organization Overview
- Browse [github.com/NovaeoGit](https://github.com/NovaeoGit) — the org README
- Repo catalog and what each repo does
- Reference links to Anthropic docs

### 2.2 Repo Highlights
- **clawd-skills** — the skill library (75+ production skills, hello-world starter, design guide)
- **procurement-agent** / **sourcing-agent** — real agent systems powered by skills
- **supplement-video-engine** — programmatic video production
- **seo-geo-project** — SEO content hubs across 8 brands
- **Amazon-Listing-Analysis** — multi-AI product analysis

### 2.3 Organization Discussions
- Where to ask questions, share discoveries, post ideas
- Everyone should have posted their "I read the README" discussion before we start

---

## Part 3: Hands-On Walkthrough (30 min)

Follow the training walkthrough together: [01-getting-started-walkthrough.md](01-getting-started-walkthrough.md)

1. Open Claude Code (the only terminal command they'll type)
2. Connect to GitHub
3. Clone the clawd-skills repo
4. Open Obsidian to watch live changes
5. Set up .env with API keys from Dashlane
6. Explore the hello-world skill
7. Install it globally to ~/.claude/skills/
8. Run it — auto-trigger and /slash-command
9. Look at a production skill
10. Create their own skill

---

## Part 4: GitHub Operations for the Team (15 min)

How we work together as a team using GitHub.

### 4.1 Your Sandbox Repo
Every team member has a personal sandbox repo in NovaeoGit:
- `sandbox-[firstname]` — your personal workspace
- Use it to experiment, practice, build things, break things
- Push anything you're working on — scripts, notes, experiments, skill drafts
- This is YOUR space — no one else will touch it

**To get started, prompt Claude Code:**
> Clone my sandbox repo from NovaeoGit and set it up as my workspace.

### 4.2 Sharing a Project with the Team
When you build something the team should have access to:

1. Ask Claude Code to create a new repo in NovaeoGit for your project
2. Include a README explaining what it does and how to use it
3. Include a CLAUDE.md so Claude Code understands the project
4. Share the link in Discussions

**Prompt Claude Code:**
> Create a new repo in NovaeoGit called [project-name]. Push my current project to it with a README and CLAUDE.md.

### 4.3 Sharing a Skill You Built
When you create a skill locally that others should have:

1. Clone the clawd-skills repo (if you haven't already)
2. Ask Claude Code to copy your skill into the repo and push it

**Prompt Claude Code:**
> Copy my skill from ~/.claude/skills/[skill-name] into the clawd-skills repo under skills/[skill-name] and push it to GitHub.

### 4.4 Getting Skills Others Shared
To grab new skills the team has pushed:

**Prompt Claude Code:**
> Pull the latest changes from the clawd-skills repo and install any new skills globally.

### 4.5 General Rules
- **Always sync to GitHub** — if it's worth keeping, push it
- **Personal experiments** go in your sandbox repo
- **Team-worthy projects** get their own repo in NovaeoGit
- **Reusable skills** get pushed to clawd-skills
- **Questions and announcements** go in Discussions
- Don't worry about breaking things — that's what sandboxes are for

---

## Part 5: Open Exploration & Q&A (remaining time)

Free time to:
- Finish the walkthrough at your own pace
- Explore other repos
- Build a skill for something you actually need
- Try Claude Cowork with a teammate
- Ask questions

---

## Quick Reference Card

| I want to... | Prompt Claude Code with... |
|--------------|---------------------------|
| Clone a repo | "Clone NovaeoGit/[repo-name] to my home directory" |
| Install a skill globally | "Install [skill-name] from the skills folder to ~/.claude/skills/" |
| Create a new skill | "Create a new global skill called [name] that does [description]" |
| Push my work | "Commit my changes and push to GitHub" |
| Share a skill | "Copy my [skill] into the clawd-skills repo and push it" |
| Create a new project repo | "Create a new repo in NovaeoGit called [name] and push this project" |
| Pull team updates | "Pull the latest from clawd-skills and install any new skills" |
| Get help | "I'm stuck — what should I do next?" |
