# Vercel Skills

Curated collection of Vercel agent skills packaged as a Claude Code plugin.

## Included Skills

This plugin contains three high-quality skills from the [vercel-labs/agent-skills](https://github.com/vercel-labs/agent-skills) repository:

### 1. React Best Practices (`react-best-practices`)

Comprehensive React and Next.js optimization guidelines covering:
- Component architecture and patterns
- Performance optimization strategies
- State management best practices
- Server/client component usage
- API route design
- 40+ specific rules and recommendations

**Trigger phrases:** "optimize React component", "React best practices", "improve Next.js performance"

### 2. Web Design Guidelines (`web-design-guidelines`)

Extensive web design and UX rules focusing on:
- Accessibility (WCAG compliance)
- Performance optimization
- User experience patterns
- Responsive design principles
- Form design and validation
- 100+ specific guidelines

**Trigger phrases:** "improve accessibility", "web design best practices", "UX guidelines"

### 3. Vercel Deploy (`vercel-deploy-claimable`)

Deploy applications to Vercel directly from conversations:
- Project creation and deployment
- Environment variable configuration
- Domain setup
- Deployment status tracking

**Trigger phrases:** "deploy to Vercel", "create Vercel project", "set up Vercel deployment"

## Installation

### Add Marketplace

```bash
/plugin marketplace add pwarnock/pwarnock-cc-plugins
```

### Install Plugin

```bash
/plugin install vercel-skills@pwarnock-cc-plugins
```

## Usage

Once installed, the skills are automatically available in your Claude Code sessions. Claude will invoke them based on context and trigger phrases.

### Example Workflows

**Optimize a React component:**
```
You: This React component is rendering slowly. Can you help optimize it?
Claude: [Triggers react-best-practices skill and applies optimization guidelines]
```

**Audit accessibility:**
```
You: Review this page for accessibility issues
Claude: [Triggers web-design-guidelines skill and checks WCAG compliance]
```

**Deploy to Vercel:**
```
You: Deploy this Next.js app to Vercel
Claude: [Triggers vercel-deploy-claimable skill and guides through deployment]
```

## Updating Skills

The skills are included as a git submodule pointing to the upstream Vercel repository. To update to the latest version:

```bash
cd ~/.claude/plugins/vercel-skills
git submodule update --remote skills
```

## Structure

```
vercel-skills/
├── .claude-plugin/
│   └── plugin.json          # Plugin manifest
├── skills/                  # Git submodule → vercel-labs/agent-skills
│   ├── react-best-practices/
│   ├── web-design-guidelines/
│   └── vercel-deploy-claimable/
├── commands/
│   └── sync-skills.md       # Command to update skills
└── README.md                # This file
```

## Credits

Skills are curated from the [Vercel Labs Agent Skills](https://github.com/vercel-labs/agent-skills) repository. All credit goes to the Vercel team and contributors.

## License

MIT License - See LICENSE file for details.

Skills are subject to their original licenses in the upstream repository.
