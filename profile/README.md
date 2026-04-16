# Novaeo

**AI-native e-commerce operations** — we build agents, skills, and automated pipelines that run our supplement brands end-to-end.

This organization houses the internal tools, agent systems, and reference libraries that power Novaeo's operations across sourcing, procurement, content, SEO, and product analysis.

---

## Repositories

### Agent Systems

| Repo | Description |
|------|-------------|
| [**procurement-agent**](https://github.com/NovaeoGit/procurement-agent) | PO lifecycle management — from DRAFT through DELIVERED. Dual-writes to Baserow + Google Sheets, issues POs through Zoho Inventory, monitors the purchasing inbox, and tracks carrier shipments. |
| [**sourcing-agent**](https://github.com/NovaeoGit/sourcing-agent) | Supplier discovery, RFQ management, Alibaba automation, quote comparison, and sample tracking. The front end of our supply chain before a PO is ever issued. |

### Skill Library

| Repo | Description |
|------|-------------|
| [**clawd-skills**](https://github.com/NovaeoGit/clawd-skills) | 75+ production skills for OpenClaw agents. The reference library for how we build modular, reusable agent capabilities — from inbox monitoring to freight booking to quote extraction. **Start here if you're learning to build skills.** |

### Content & Marketing

| Repo | Description |
|------|-------------|
| [**seo-geo-project**](https://github.com/NovaeoGit/seo-geo-project) | SEO/GEO content hubs for 8 Shopify brands. Static Astro sites deployed to Cloudflare Pages, routed via Workers, managed autonomously by agents. Currently live on whyz.com/learn. |
| [**supplement-video-engine**](https://github.com/NovaeoGit/supplement-video-engine) | Programmatic YouTube Shorts production for IngredientHQ. Remotion + ElevenLabs + AI-driven QA pipeline. Renders educational ingredient science videos from structured data. |

### Analysis & Research

| Repo | Description |
|------|-------------|
| [**Amazon-Listing-Analysis**](https://github.com/NovaeoGit/Amazon-Listing-Analysis) | Multi-AI Amazon listing analysis framework. Combines GPT-5.2, Claude Opus, and Gemini to analyze SQP data, PPC reports, competitor listings, and product images for optimization recommendations. |

---

## Reference & Learning

### Claude Code, Skills & Agents

| Resource | Description |
|----------|-------------|
| [Claude Code Documentation](https://docs.anthropic.com/en/docs/claude-code) | Official docs — installation, usage, permissions, configuration |
| [Claude Code Best Practices](https://docs.anthropic.com/en/docs/claude-code/best-practices) | Patterns for effective Claude Code usage |
| [Claude Code Hooks](https://docs.anthropic.com/en/docs/claude-code/hooks) | Automate actions before/after tool calls with shell hooks |
| [Claude Code Skills](https://docs.anthropic.com/en/docs/claude-code/skills) | How to build and use custom skills (SKILL.md files) |
| [Claude Code Agent SDK](https://docs.anthropic.com/en/docs/claude-code/sdk) | Build custom multi-agent systems with the SDK |
| [Claude Code Sub-agents](https://docs.anthropic.com/en/docs/claude-code/sub-agents) | Patterns for spawning and coordinating sub-agents |
| [Claude Code GitHub Actions](https://docs.anthropic.com/en/docs/claude-code/github-actions) | CI/CD integration — automated PR reviews, issue triage |
| [Claude Code MCP](https://docs.anthropic.com/en/docs/claude-code/mcp) | Extend Claude Code with Model Context Protocol servers |

### Anthropic Platform

| Resource | Description |
|----------|-------------|
| [Anthropic API Docs](https://docs.anthropic.com/en/api) | Full API reference |
| [Anthropic Cookbook](https://github.com/anthropics/anthropic-cookbook) | Code examples and patterns for building with Claude |
| [Prompt Engineering Guide](https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering) | How to write effective prompts |
| [Tool Use (Function Calling)](https://docs.anthropic.com/en/docs/build-with-claude/tool-use) | Connecting Claude to external tools and APIs |

### Claude Cowork

| Resource | Description |
|----------|-------------|
| [Claude Cowork Overview](https://docs.anthropic.com/en/docs/claude-code/cowork) | Multi-agent collaboration with shared plans and parallel execution |

### Community & Articles

| Resource | Description |
|----------|-------------|
| [Claude Code GitHub](https://github.com/anthropics/claude-code) | Open issues, discussions, changelog |
| [Anthropic Engineering Blog](https://www.anthropic.com/engineering) | Technical deep dives from the Anthropic team |
| [Claude Code Tips (Community)](https://github.com/anthropics/claude-code/discussions) | Community tips, patterns, and workflows |

---

## Getting Started

1. **Install Claude Code** — `npm install -g @anthropic-ai/claude-code`
2. **Clone a repo** — start with `clawd-skills` to see how production skills are structured
3. **Read the CLAUDE.md** — every repo has one; it's the agent's instruction manual for that project
4. **Join Discussions** — use the [org discussions](https://github.com/orgs/NovaeoGit/discussions) for questions, ideas, and knowledge sharing

---

*Built with Claude Code and a lot of caffeine.*
