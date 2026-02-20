---
name: workflow-capture
description: Detects recurring workflows and prompts to create skills when reusable patterns emerge. Use when (1) similar tasks are performed repeatedly, (2) automation patterns become evident, (3) discussing skill creation, or (4) any multi-step process that could be templated.
---

# Workflow Capture

## Overview

Monitors conversations to identify reusable workflows and prompts when it makes sense to capture them as skills. Helps maintain skill hygiene by catching patterns early.

## When to Trigger

This skill activates when:

1. **Repetition detected**: The same or similar task is performed 2-3+ times
2. **Long conversation**: A single session or conversation thread lasts more than 30 minutes
3. **Pattern emerges**: A multi-step workflow becomes routine or recurring
4. **Skill discussion**: Any conversation about creating or improving skills
5. **Reusable automation**: Any workflow that could be templated or scripted

## How It Works

### 1. Detection

Track these signals:
- Session duration (conversations lasting 30+ minutes)
- Repeated operations (file edits, commands, configurations)
- Recurring multi-step processes
- Explicit mentions of skill creation
- Any workflow with 3+ steps that could be generalized

### 2. Suggestion Format

When a pattern is detected, prompt with:

```
🔄 Workflow Detected: [brief description]
- Seen: [count] times
- Why useful: [1-line rationale]
→ Create a skill? (Y/n)
```

### 3. Skill Creation Flow

If agreed:

1. Use **skill-creator** skill to initialize
2. Ask for concrete examples of usage
3. Identify reusable components (scripts, references, assets)
4. Scaffold with `init_skill.py`
5. Write SKILL.md with clear triggers and usage
6. Package with `package_skill.py`

## Example Suggestions

- "This conversation is 45 minutes in — we've covered a lot. Any reusable patterns to capture?"
- "Pushed to 3 repos the same way — skill for multi-repo git operations?"
- "Set up cron jobs repeatedly — skill for cron job templates?"
- "Building similar skills — save this pattern?"

## Notes

- Don't over-trigger — wait for genuine reuse potential (2-3x minimum)
- Keep suggestions brief and actionable
- Always ask before creating; never assume
- **Security**: Never include secrets, API keys, passwords, tokens, or sensitive information in skills. Skills are stored in git and potentially shared publicly via ClawHub. Use environment variables or 1Password references instead.
