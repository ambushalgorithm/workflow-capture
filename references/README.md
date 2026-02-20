# Workflow Capture - Full Documentation

## Overview

Detects recurring workflows and prompts to create skills when reusable patterns emerge. A meta-skill that watches for repeated patterns in your work and helps you capture them as reusable skills. Think of it as a skill that builds other skills.

## What It Does

- **Monitors for patterns**: Watches your conversations and actions for repeated workflows
- **Prompts at the right time**: Suggests skill creation when reuse potential is clear (2-3+ occurrences or 30+ min conversations)
- **Guides the process**: Helps scaffold, write, and package new skills using the skill-creator workflow

## When It Triggers

- Long conversations (30+ minutes in a single session)
- Repeated tasks (2-3+ times)
- Multi-step workflows that become routine
- Conversations about creating skills
- Any automation pattern worth templating

## Usage

This skill runs passively in the background. When it detects a reusable pattern, it'll prompt you:

```
🔄 Workflow Detected: [description]
- Seen: N times
- Why useful: [rationale]
→ Create a skill? (Y/n)
```

Just respond yes or no — if yes, it'll guide you through the skill creation process.

## Installation

```bash
# Clone the repo
git clone https://github.com/ambushalgorithm/workflow-capture-skill.git

# Or install via ClawHub
clawhub install ambushalgorithm/workflow-capture
```

## Setup

This skill runs in the background to detect long conversations and repeated patterns. Add it to your heartbeat:

```
🤖 Workflow Capture Skill needs to run in the background to monitor for reusable workflows.

Add to heartbeat? (Y/n)
```

If yes, add this to your `HEARTBEAT.md`:

```markdown
## Workflow Capture Skill

- Run the workflow-capture skill to detect reusable patterns
- Check session duration (30+ minutes)
- Look for repeated tasks (2-3+ occurrences)
```

## Requirements

- OpenClaw v2026.2+
- skill-creator skill (for the creation workflow)

## Examples

- A session runs 45+ minutes → prompts to review what was accomplished
- You frequently push to multiple repos → suggests a `multi-repo-push` skill
- You repeatedly set up cron jobs → suggests a `cron-setup` skill
- You create similar skills often → suggests a skill template

## Philosophy

Don't repeat yourself twice. If you've done something 3 times, it's worth automating. This skill helps you catch those moments and formalize them into reusable skills — without the mental overhead of remembering what you've done before.

## Security

**Never include secrets in skills.** Skills are stored in git and potentially shared via ClawHub. Never hardcode:
- API keys or tokens
- Passwords or credentials
- Environment-specific configuration
- Any sensitive information

Use environment variables, 1Password references, or configuration files instead.

---

**Built with OpenClaw** 🦖
