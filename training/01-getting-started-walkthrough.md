# Training Walkthrough: Your First Skill with Claude Code

**Time:** ~30 minutes | **Difficulty:** Beginner | **Prerequisites:** See pre-meeting checklist

This walkthrough takes you from zero to running your first Claude Code skill. By the end, you'll have cloned a repo, explored a skill, and run it live.

---

## Part 1: Verify Your Setup (5 min)

### 1.1 Confirm Claude Code is installed

Open your terminal (Terminal on Mac, PowerShell on Windows) and run:

```bash
claude --version
```

You should see a version number. If not, revisit the install instructions.

### 1.2 Authenticate Claude Code

If this is your first time, Claude Code will prompt you to log in:

```bash
claude
```

Follow the browser prompt to authenticate with your Anthropic account.

### 1.3 Confirm GitHub CLI access

```bash
gh auth status
```

You should see your GitHub account. If not:

```bash
gh auth login
```

Choose **GitHub.com > HTTPS > Login with a web browser** and follow the prompts.

---

## Part 2: Clone the Skills Repo (5 min)

### 2.1 Clone clawd-skills

```bash
cd ~
gh repo clone NovaeoGit/clawd-skills
cd clawd-skills
```

### 2.2 Take a quick look around

```bash
ls
```

You'll see:
- `README.md` — full skill catalog
- `CLAUDE.md` — project guide (Claude Code reads this automatically)
- `docs/` — design guides
- `skills/` — 75+ production skills
- `.env.example` — environment variable template

### 2.3 Set up your environment file

```bash
cp .env.example .env
```

Now edit `.env` and add the API keys from Dashlane. At minimum you need:

```
ANTHROPIC_API_KEY=your_key_here
```

The rest can be added later as you explore different skills.

---

## Part 3: Explore the Hello World Skill (5 min)

### 3.1 Look at the skill structure

```bash
ls skills/hello-world/
```

There's one file: `SKILL.md`. This is all a skill needs.

### 3.2 Read through it

```bash
cat skills/hello-world/SKILL.md
```

Notice the structure:
1. **YAML frontmatter** (top) — name + description for routing
2. **Routing** — when to use / when not to use
3. **Prerequisites** — what's needed
4. **Workflow** — step-by-step instructions
5. **Examples** — concrete input/output pairs
6. **Templates** — output formatting
7. **Troubleshooting** — common issues
8. **Post-Run: Self-Improvement** — mandatory in every skill

This pattern is the same across all 75+ skills.

---

## Part 4: Run the Skill with Claude Code (10 min)

### 4.1 Fire up Claude Code in the repo

```bash
cd ~/clawd-skills
claude
```

Claude Code automatically reads the `CLAUDE.md` and knows about the skill system.

### 4.2 Install the hello-world skill

Inside Claude Code, type:

```
Copy the hello-world skill to my OpenClaw skills directory
```

Or do it manually:

```bash
mkdir -p ~/.openclaw/skills
cp -r skills/hello-world ~/.openclaw/skills/
```

### 4.3 Trigger the skill

Now ask Claude Code something that matches the skill's routing:

```
Summarize the skills directory
```

Claude Code should:
1. Recognize this matches the hello-world skill
2. Run the file analysis commands
3. Output a formatted directory summary with file counts, sizes, and recent files

### 4.4 Try variations

```
What's in the docs folder?
```

```
How big is this repo?
```

```
Show me recently modified files in skills/
```

---

## Part 5: Look at a Production Skill (5 min)

Now that you understand the format, look at a real production skill:

### 5.1 Browse a simple one

```bash
cat skills/pdf/SKILL.md
```

Notice how it follows the same structure as hello-world, but does real work.

### 5.2 Browse the skill catalog

```bash
cat README.md
```

Scroll through the tables to see all 75+ skills organized by category.

### 5.3 Read the design guide

```bash
cat docs/SKILL-DESIGN-GUIDE.md
```

This is the reference for building your own skills — routing logic, progressive disclosure, anti-patterns, and testing.

---

## Part 6: Create Your Own Skill (Bonus)

Ready to build something? Start from the template:

```bash
cp -r skills/hello-world skills/my-first-skill
```

Then ask Claude Code:

```
Help me turn skills/my-first-skill into a skill that [describe what you want].
Update the SKILL.md with the correct routing, workflow, and templates.
```

Claude Code will rewrite the SKILL.md for your use case, following the patterns from the design guide.

---

## What's Next?

- **Explore other repos** — check out `procurement-agent` or `sourcing-agent` to see how skills plug into full agent systems
- **Read the org README** — [github.com/NovaeoGit](https://github.com/NovaeoGit) has links to all reference docs
- **Ask questions** — post in [Org Discussions](https://github.com/orgs/NovaeoGit/discussions)
- **Anthropic docs** — [docs.anthropic.com/en/docs/claude-code/skills](https://docs.anthropic.com/en/docs/claude-code/skills) for the official skill reference

---

## Troubleshooting

| Problem | Solution |
|---------|----------|
| `claude: command not found` | Reinstall: `npm install -g @anthropic-ai/claude-code` |
| `gh: command not found` | Install GitHub CLI: `brew install gh` (Mac) or `winget install GitHub.cli` (Windows) |
| Permission denied cloning repo | Make sure you accepted the NovaeoGit org invite |
| Claude Code doesn't recognize the skill | Make sure you're running `claude` from inside the `clawd-skills` directory |
| `.env` not loading | Check the file is named `.env` (not `.env.example`) and is in the repo root |
