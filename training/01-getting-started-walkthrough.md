# Training Walkthrough: Your First Skill with Claude Code

**Time:** ~30 minutes | **Difficulty:** Beginner | **Prerequisites:** See pre-meeting checklist

This walkthrough takes you from zero to running your first Claude Code skill. By the end, you'll have cloned a repo, explored a skill, and run it live — all by prompting Claude Code in plain English.

---

## Setup (do this once at the start)

### Open your terminal

- **Mac:** Press `Cmd + Space`, type `Terminal`, press Enter
- **Windows:** Press `Win + R`, type `powershell`, press Enter

### Start Claude Code

Type this one command and press Enter:

```
claude
```

That's the last terminal command you need to type. From here on, everything is done by talking to Claude Code.

### Open Obsidian

Open the Obsidian app. We'll connect it to your working folder in a moment so you can watch Claude Code make changes in real time.

---

## Part 1: Connect to GitHub (5 min)

Prompt Claude Code:

> **Log me into GitHub using the GitHub CLI. Walk me through the steps.**

Claude Code will run `gh auth login` and guide you through the browser login flow. Follow the prompts it gives you.

Once logged in, confirm it worked:

> **Am I logged into GitHub? What account am I using?**

---

## Part 2: Clone the Skills Repo (5 min)

Prompt Claude Code:

> **Clone the NovaeoGit/clawd-skills repo into my home directory and open it as our working folder.**

Claude Code will clone the repo and `cd` into it. Now connect Obsidian to the same folder so you can see the files:

1. In Obsidian, click **Open another vault** (vault icon, bottom left)
2. Click **Open folder as vault**
3. Navigate to your home folder and select the `clawd-skills` folder
   - **Mac:** `/Users/[your-username]/clawd-skills`
   - **Windows:** `C:\Users\[your-username]\clawd-skills`
4. Click Open

You should now see the repo's files in Obsidian's sidebar. As Claude Code creates and edits files, you'll see the changes appear here in real time.

---

## Part 3: Set Up Your Environment (5 min)

Prompt Claude Code:

> **Create a .env file from the .env.example template. I have these API keys from Dashlane — help me fill them in.**

Then paste your API keys from Dashlane when Claude Code asks for them. At minimum:

> **Set ANTHROPIC_API_KEY to [paste your key]**

Watch Obsidian — you'll see the `.env` file appear and get populated.

---

## Part 4: Explore the Hello World Skill (5 min)

Prompt Claude Code:

> **Show me the hello-world skill in the skills folder. Explain each section and what it does.**

Claude Code will read `skills/hello-world/SKILL.md` and walk you through:
- **Frontmatter** — how the agent knows when to use this skill
- **Routing** — trigger phrases and disambiguation
- **Workflow** — the step-by-step instructions
- **Templates** — output formatting
- **Post-Run** — how skills self-improve after every run

Follow along in Obsidian — open `skills/hello-world/SKILL.md` in the sidebar to read it yourself while Claude Code explains it.

---

## Part 5: Install the Skill Natively (5 min)

Skills in the `skills/` folder are just reference copies in the repo. To make Claude Code natively recognize a skill (auto-trigger it and make it available as a `/slash-command`), it needs to be installed to your personal skills folder.

Prompt Claude Code:

> **Install the hello-world skill as a global Claude Code skill. Copy it from the skills/ folder into ~/.claude/skills/hello-world/ so it's available across all my projects.**

Claude Code picks up new skills live — no restart needed. The skill is now available everywhere:
- **Claude Code CLI** (terminal)
- **Claude Code Desktop app**
- **Claude Cowork** (multi-agent collaboration)
- **VS Code / JetBrains extensions**
- **Claude Code web app** (claude.ai/code)

**How native skills work:**
- **Auto-trigger** — Claude reads the skill's description and automatically uses it when your prompt matches
- **Slash command** — you can also type `/hello-world` directly to invoke it
- **Global skills** in `~/.claude/skills/` load across all your projects and all Claude Code surfaces
- **Project skills** in `.claude/skills/` only load for that specific project

---

## Part 6: Run the Skill (10 min)

Now trigger it. Prompt Claude Code:

> **Summarize the skills directory**

Claude Code will recognize this matches the hello-world skill and run it — counting files, measuring sizes, finding recently modified files, and outputting a formatted report.

Or invoke it directly:

> **/hello-world**

Try a few more:

> **What's in the docs folder?**

> **Show me recently modified files in this repo**

> **How big is this project?**

---

## Part 7: Look at a Production Skill (5 min)

Now see what a real skill looks like. Prompt Claude Code:

> **Show me the PDF skill and compare its structure to hello-world. What's the same and what's different?**

Then browse the full catalog:

> **List all the skills in this repo organized by category**

Want to install more? Just ask:

> **Install the PDF skill globally too, same as hello-world.**

---

## Part 8: Create Your Own Skill (Bonus)

Ready to build? Prompt Claude Code:

> **Create a new global skill called "my-first-skill" in ~/.claude/skills/. Base it on the hello-world template. I want it to [describe what you want it to do].**

Claude Code will create the folder and write the SKILL.md following the same structure — frontmatter, routing, workflow, templates, post-run. The skill is immediately available everywhere — try invoking it with `/my-first-skill`.

Some ideas to try:
- A skill that summarizes a git repo's recent activity
- A skill that generates a daily standup report
- A skill that checks a project for missing documentation

---

## What's Next?

Ask Claude Code:

> **What other repos are in the NovaeoGit organization? Give me a summary of each.**

> **Clone the procurement-agent repo and show me how its skills connect to the agent system.**

Explore on your own:
- **Org README** — [github.com/NovaeoGit](https://github.com/NovaeoGit) has links to all repos and reference docs
- **Discussions** — [github.com/orgs/NovaeoGit/discussions](https://github.com/orgs/NovaeoGit/discussions) for questions and knowledge sharing
- **Official docs** — [docs.anthropic.com/en/docs/claude-code/skills](https://docs.anthropic.com/en/docs/claude-code/skills)

---

## Troubleshooting

| Problem | What to tell Claude Code |
|---------|--------------------------|
| Can't clone the repo | "I'm getting a permission error cloning from NovaeoGit. Help me fix it." |
| Claude Code doesn't recognize the skill | "I'm in the clawd-skills directory but the skill isn't triggering. What's wrong?" |
| .env not working | "My API keys aren't being loaded. Can you check my .env file?" |
| Obsidian not showing changes | Close and reopen the vault, or click a different folder and back |
| General confusion | "I'm stuck. Can you explain what just happened and what I should do next?" |

The best part about Claude Code: when in doubt, just ask it. Describe what you're trying to do and it will help you get there.
