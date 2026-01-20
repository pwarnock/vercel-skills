# Setup Instructions for vercel-skills Plugin

Follow these steps to create and publish the vercel-skills plugin repository.

## Step 1: Create GitHub Repository

1. Go to https://github.com/new
2. Set repository name: `vercel-skills`
3. Description: "Curated Vercel agent skills for Claude Code"
4. Make it public
5. **Do NOT** initialize with README, .gitignore, or license (we already have these)
6. Click "Create repository"

## Step 2: Initialize Local Repository

```bash
cd /tmp/vercel-skills
git init
git add .
git commit -m "Initial plugin setup"
```

## Step 3: Add Git Submodule

This is the critical step that connects to the upstream Vercel skills:

```bash
cd /tmp/vercel-skills
git submodule add https://github.com/vercel-labs/agent-skills.git skills
git add .gitmodules skills
git commit -m "Add vercel-labs/agent-skills as submodule"
```

## Step 4: Push to GitHub

```bash
git remote add origin git@github.com:pwarnock/vercel-skills.git
git branch -M main
git push -u origin main
```

## Step 5: Verify Submodule

Check that the submodule is properly configured:

```bash
git submodule status
# Should show: [commit-hash] skills (heads/main)

ls skills/
# Should show: react-best-practices  web-design-guidelines  vercel-deploy-claimable
```

## Step 6: Test Installation

Once the repository is published, test the installation:

```bash
# Add marketplace (if not already added)
/plugin marketplace add pwarnock/pwarnock-cc-plugins

# Install the plugin
/plugin install vercel-skills@pwarnock-cc-plugins

# Verify installation
ls ~/.claude/plugins/vercel-skills/skills/
# Should show the three skill directories
```

## Troubleshooting

### Submodule not showing up on GitHub

If you push without adding the submodule first, GitHub will show an empty `skills/` directory. Solution:

```bash
git rm -r skills
git submodule add https://github.com/vercel-labs/agent-skills.git skills
git commit -m "Fix submodule configuration"
git push
```

### Submodule appears as a folder icon on GitHub

This is correct! Git submodules appear as special folder icons (📁 with arrow) and link to the upstream repository.

### Skills not loading in Claude Code

Make sure the plugin was installed from the marketplace, not cloned directly. Claude Code handles submodule initialization during installation.

## Future Updates

To update the skills to the latest version from Vercel:

```bash
cd /tmp/vercel-skills  # or wherever you have the repo
git submodule update --remote skills
git add skills
git commit -m "Update skills from upstream"
git push
```

Then users can update their installation with:
```bash
/plugin update vercel-skills
```
