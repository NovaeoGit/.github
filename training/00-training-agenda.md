# AI Skills & Agents Training — Agenda

**Date:** April 16, 2026
**Facilitator:** Derrek

---

## Opening: The New Default (5 min)

Before anything else, set the ground rule for this training and everything after it:

> **Your default is now "Ask Claude."**

Not Derrek. Not Google. Not stopping and waiting. Claude Opus is the most powerful AI model in the world. It can read, write, build, research, debug, plan, and execute — anything you can do at a computer, it can do or help you do. Starting today:

- **Stuck on something?** Ask Claude.
- **Don't know how to start?** Ask Claude.
- **Not sure if something is possible?** Ask Claude.
- **Need to learn something new?** Ask Claude.
- **Want to build something but don't know how?** Ask Claude.

This isn't a suggestion — it's the new workflow. Claude is your first stop, every time. The goal of today's training is to prove this to you so deeply that it becomes instinct.

**During this training:** If you have a question, don't raise your hand — type it into Claude Code first. If Claude can't answer it (unlikely), then ask the group.

---

## Part 1: The Claude Suite (20 min)

### 1.1 Claude Web (claude.ai)
- **Chat** — general conversation, analysis, writing, research
- **Code** (claude.ai/code) — browser-based Claude Code, same engine as terminal
- Available connectors: Google Drive, GitHub, web search, file uploads

### 1.3 Claude Desktop App
- **Chat mode** — same as web, but native app with system integration
- **Code mode** — full Claude Code in a desktop window
- **Cowork mode** — multi-agent collaboration with shared plans and parallel execution
- Available connectors: MCP servers, local file access, terminal

### 1.4 Claude Code in Terminal
- The CLI — `claude` command
- Full tool access: file read/write, bash, git, web search
- Skills and hooks system
- Same engine powering all surfaces — skills you install work everywhere

### 1.5 IDE Extensions
- VS Code and JetBrains — Claude Code embedded in your editor
- Same skills, same MCP servers, same settings

**Key takeaway:** All surfaces share the same engine. Your skills, settings, and MCP servers carry across all of them. Learn one, you know them all.

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

**Reinforcement during walkthrough:**
When someone asks you (Derrek) a question during this section, redirect them:
> "Great question — type that into Claude Code and see what it says."

Do this every time. It will feel awkward at first but it's the fastest way to rewire the habit. They need to experience Claude answering their questions successfully, repeatedly, to build trust in the workflow.

---

## Part 4: How Skills Are Built — The "Hand-Holding" Process (15 min)

This is the most important concept in the training. Skills don't come from nowhere — they come from real work.

### 4.1 The Process

**Step 1: Do it live with Claude, side by side.**

The first time you do any task, you don't write a skill. You work through it with Claude in a normal conversation — prompting, going back and forth, adjusting, iterating. Claude does the work, you guide the direction. This is the "hand-holding" phase.

**Step 2: Arrive at a good outcome.**

At some point you'll have a result you're happy with — a workflow that works, an output format that's right, a sequence of steps that reliably produces what you need.

**Step 3: Recognize the pattern.**

Ask yourself: "Will I want to do this again?" If yes, it's time to build a skill.

**Step 4: Build the skill from the session.**

You don't start from scratch. You tell Claude:

> **Look at what we just did in this conversation. Turn it into a reusable skill in ~/.claude/skills/. Follow the SKILL.md format from the design guide.**

Claude already has the full context — the steps, the edge cases, the corrections you made, the final output format. It writes the skill from lived experience, not theory.

**Step 5: Run the skill next time.**

The next time the task comes up, the skill fires automatically. What took 30 minutes of back-and-forth now takes 30 seconds.

### 4.2 Live Example

Walk through a real example from the Novaeo skill library:

1. Show a production skill (e.g., `procurement-inbox` or `email-response`)
2. Explain the messy reality: "The first time I did this, it was a 45-minute conversation with Claude. I was figuring out the steps, correcting mistakes, refining the output."
3. Show the clean skill that came out of it
4. Show it running — the same task that took 45 minutes now runs in seconds

### 4.3 Key Mindset

- **You don't need to know how to code to build a skill.** Claude writes it. You just need to know what you want.
- **Every repetitive task is a skill waiting to be built.** If you do something twice, it should be a skill by the third time.
- **Skills get better over time.** Every skill has a Post-Run self-improvement section — Claude fixes issues automatically after each run.
- **Your daily work IS skill development.** You're not stopping your work to "build skills" — you're doing your work and turning the good parts into skills along the way.

---

## Part 5: GitHub Operations for the Team (15 min)

How we work together as a team using GitHub.

### 5.1 Your Sandbox Repo
Every team member has a personal sandbox repo in NovaeoGit:
- `sandbox-[firstname]` — your personal workspace
- Use it to experiment, practice, build things, break things
- Push anything you're working on — scripts, notes, experiments, skill drafts
- This is YOUR space — no one else will touch it

**To get started, prompt Claude Code:**
> Clone my sandbox repo from NovaeoGit and set it up as my workspace.

### 5.2 Sharing a Project with the Team
When you build something the team should have access to:

1. Ask Claude Code to create a new repo in NovaeoGit for your project
2. Include a README explaining what it does and how to use it
3. Include a CLAUDE.md so Claude Code understands the project
4. Share the link in Discussions

**Prompt Claude Code:**
> Create a new repo in NovaeoGit called [project-name]. Push my current project to it with a README and CLAUDE.md.

### 5.3 Sharing a Skill You Built
When you create a skill locally that others should have:

1. Clone the clawd-skills repo (if you haven't already)
2. Ask Claude Code to copy your skill into the repo and push it

**Prompt Claude Code:**
> Copy my skill from ~/.claude/skills/[skill-name] into the clawd-skills repo under skills/[skill-name] and push it to GitHub.

### 5.4 Getting Skills Others Shared
To grab new skills the team has pushed:

**Prompt Claude Code:**
> Pull the latest changes from the clawd-skills repo and install any new skills globally.

### 5.5 General Rules
- **Always sync to GitHub** — if it's worth keeping, push it
- **Personal experiments** go in your sandbox repo
- **Team-worthy projects** get their own repo in NovaeoGit
- **Reusable skills** get pushed to clawd-skills
- **Questions and announcements** go in Discussions
- Don't worry about breaking things — that's what sandboxes are for

---

## Part 6: Open Exploration & Q&A (remaining time)

Free time to:
- Finish the walkthrough at your own pace
- Explore other repos
- Build a skill for something you actually need
- Try Claude Cowork with a teammate
- Ask questions — **to Claude first, then to the group**

---

## Part 7 (Optional): Live Demo — "Watch This"

If time allows, end with a live power demo. The goal is to leave the team with a visceral sense of what Claude can do when you just ask it.

Pick one of these (or improvise based on the room's energy):

**Build a working web app from one sentence:**
> "Build me a web app that lets someone paste an Amazon ASIN and it shows the product title, price, rating, and top 5 review themes. Make it look professional."

Watch a full working tool materialize from nothing — HTML, CSS, JavaScript — then open it in a browser.

**Full brand audit from a URL:**
> "Go to [one of your Shopify stores] and do a complete audit — homepage, product pages, SEO meta tags, page speed issues, mobile experience, and content gaps. Give me a prioritized list of improvements."

Something that takes consultants weeks, done in minutes.

**Turn a messy email into structured action:**
> "Here's a supplier email [paste a real one]. Parse out every quote, compare the prices to what we're currently paying, draft a response negotiating better terms on the items where we're overpaying, and create a summary table I can share with the team."

Something the team does manually every day, handled instantly.

The point isn't to show off — it's to expand their sense of what's possible. After a full training of hands-on work, this demo hits differently because they now have the foundation to do it themselves.

---

### Closing Reinforcement

End the training by coming back to the opening:

> Remember — your default is "Ask Claude." Not me, not Google, not stopping. Starting now, when you're stuck, when you're curious, when you don't know where to begin — open Claude and describe what you're trying to do. It will get you unstuck faster than any person can, and it's available 24/7.
>
> The people who get the most out of this are the ones who use it the most. Don't wait for permission to build something. Don't wait for a task assignment. See something repetitive? Build a skill. Have an idea? Start prompting. The sandbox is yours — go experiment.

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
| Get unstuck | "I'm trying to [goal] but I'm stuck on [problem]. Help me figure out the next step." |
| Learn something new | "Explain [topic] to me like I'm new to it. What do I need to know?" |
| Turn a conversation into a skill | "Look at what we just did. Turn it into a reusable skill in ~/.claude/skills/ following the SKILL.md format." |
