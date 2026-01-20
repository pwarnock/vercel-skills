---
name: sync-skills
description: Update Vercel skills from upstream repositories
---

# Sync Vercel Skills

This command updates the Vercel agent skills from the upstream repositories.

## Usage

Run the following commands to update the skills to the latest version:

```bash
cd ~/.claude/plugins/vercel-skills
git submodule update --remote skills browser-automation
```

This pulls the latest skills from:
- [vercel-labs/agent-skills](https://github.com/vercel-labs/agent-skills)
- [vercel-labs/agent-browser](https://github.com/vercel-labs/agent-browser)

## What Gets Updated

- **react-best-practices** - Latest React and Next.js optimization guidelines
- **web-design-guidelines** - Latest accessibility and UX rules
- **vercel-deploy-claimable** - Latest Vercel deployment capabilities
- **agent-browser** - Latest browser automation features

## After Update

The updated skills will be available in your next Claude Code session.
