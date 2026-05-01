# Agent Architect

Scope and cost-estimate any AI agent build in seconds, right inside Cursor.

A Cursor marketplace plugin by [BMD PAT LLC](https://bmdpat.com).

## What it does

Describe the agent you want to build in plain English. Agent Architect returns a formatted scope report with:

- **Complexity tier** — DIY / Startup / Growth / Enterprise
- **Cost breakdown** — monthly API costs, infra costs, dev hours, total build cost
- **Architecture** — orchestration pattern, tools, memory approach, key decisions
- **Timeline** — weeks-to-launch range
- **Top 3 risks** for this specific agent

The Cursor agent does the work — no extra API keys, no separate process.

## Install

### From the Cursor Marketplace

Search for **Agent Architect** in the Cursor Marketplace and click Install.

### From source (local)

Clone this repo, then symlink or copy into Cursor's plugins directory:

```bash
# macOS / Linux
ln -s "$(pwd)/agent-architect" ~/.cursor/plugins/agent-architect

# Windows (PowerShell, run as admin)
New-Item -ItemType SymbolicLink -Path "$env:USERPROFILE\.cursor\plugins\agent-architect" -Target "$(Get-Location)\agent-architect"
```

Restart Cursor. The skill will be auto-discovered.

## Use

In Cursor's Agent chat:

- **Auto-trigger** — describe what you want and ask for a scope:
  > Scope an agent that reads my unread Gmail every morning, drafts replies for the routine ones, and posts a summary to Slack.

- **Manual** — type `/` and search for `scope-agent`, then paste your description.

You'll get back a Markdown scope report.

## Free tier

5 scopes per calendar month, tracked locally at `~/.agent-architect/usage.json`. The counter resets on the 1st of each month.

Need more? [Upgrade →](https://bmdpat.com/plugin-pro?utm_source=cursor&utm_medium=plugin&utm_campaign=agent-architect-readme)

## File layout

```
agent-architect/
├── .cursor-plugin/
│   └── plugin.json              # Plugin manifest
├── skills/
│   └── scope-agent/
│       └── SKILL.md             # The skill (frontmatter + instructions)
└── README.md
```

Two files do all the work: `.cursor-plugin/plugin.json` (manifest) and `skills/scope-agent/SKILL.md` (the skill itself).

That's the entire plugin. No build step, no Node dependencies, no compiled code.

## Tier definitions

| Tier | Build cost | Timeline | Profile |
| --- | --- | --- | --- |
| DIY | $500–$2K | 1–2 weeks | Single-purpose, minimal state, weekend build |
| Startup | $2K–$15K | 2–6 weeks | Multi-step, tool use, basic memory |
| Growth | $15K–$50K | 6–16 weeks | Multi-agent, complex state, production reliability |
| Enterprise | $50K–$150K | 16+ weeks | Mission-critical, multi-system, compliance |

## Want it built?

If your scope comes back as Startup tier or higher, BMD PAT LLC builds these for a living.

→ [bmdpat.com/audit](https://bmdpat.com/audit?utm_source=cursor&utm_medium=plugin&utm_campaign=agent-architect-readme)

## License

MIT
