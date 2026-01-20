# Vercel Skills

Curated Vercel developer toolkit packaged as a Claude Code plugin.

## Included Skills

This plugin contains four high-quality skills from Vercel Labs repositories:

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

### 4. Browser Automation (`agent-browser`)

Headless browser automation for testing and data extraction:
- Navigate pages and capture structure via accessibility tree
- Fill forms, click elements, and automate interactions
- Extract page content, attributes, and element state
- Save/load browser sessions for authentication workflows
- Screenshot capture, PDF generation, and video recording
- Network monitoring and console message tracking

**Trigger phrases:** "test the website", "automate browser", "fill out form automatically", "scrape web page"

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

**Automate browser testing:**
```
You: Test the login flow on the staging site
Claude: [Triggers agent-browser skill and automates form filling, submission, and verification]
```

## Updating Skills

The skills are included as git submodules pointing to upstream Vercel repositories. To update to the latest version:

```bash
cd ~/.claude/plugins/vercel-skills
git submodule update --remote skills browser-automation
```

## Structure

```
vercel-skills/
├── .claude-plugin/
│   └── plugin.json              # Plugin manifest
├── skills/                      # Git submodule → vercel-labs/agent-skills
│   ├── react-best-practices/
│   ├── web-design-guidelines/
│   └── vercel-deploy-claimable/
├── browser-automation/          # Git submodule → vercel-labs/agent-browser
│   └── skills/
│       └── agent-browser/
├── commands/
│   └── sync-skills.md           # Command to update skills
└── README.md                    # This file
```

## Credits

Skills are curated from Vercel Labs repositories:
- [agent-skills](https://github.com/vercel-labs/agent-skills) - React best practices, web design guidelines, Vercel deployment
- [agent-browser](https://github.com/vercel-labs/agent-browser) - Browser automation

All credit goes to the Vercel team and contributors.

## License

MIT License - See LICENSE file for details.

Skills are subject to their original licenses in the upstream repository.
