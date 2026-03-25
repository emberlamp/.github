# Emberlamp Organization

Automated software engineering organization with centralized control.

## Overview

Emberlamp is a fully automated organization with 14 repositories managed through a centralized system.

## Architecture

### Central Control
- **config** - Single source of truth with repos.json
- **skills** - Agent capabilities and CLI extensions
- **swe-agent** - Agent that knows all repos
- **bot** - Automation workflow for syncing

### Repositories (14)

| Category | Repos |
|----------|-------|
| Applications | general, hub |
| Templates | react-template, swe-agent |
| CLI | cli, gh-pin-repo, config |
| Automation | bot |
| Resources | license, warnings, json-repo, gitkeep, skills |
| Meta | .github |

## Automated System

### Workflows

Each repo has 3 automated workflows:

| Workflow | Trigger | Purpose |
|----------|---------|---------|
| **CI** | push to main | Lint & test |
| **Release** | push to main | Auto version bump & GitHub release |
| **Automation** | schedule/manual | Sync, backup, report |

### Release Automation

Release workflow automatically:
1. Checks commits since last tag
2. Detects `feat:` → minor bump
3. Detects `fix:` → patch bump
4. Creates tag and pushes
5. Generates release notes
6. Creates GitHub release

### Controlling All Repos

```bash
# Clone all repos to /tmp/emberlamp/
python swe-agent/agent.py clone-all

# List all repos
python swe-agent/agent.py list

# Check capabilities
python swe-agent/agent.py capabilities
```

### Centralized Config

All repos are defined in `config/repos.json`:
```json
{
  "repos": ["general", "react-template", "swe-agent", ...],
  "org": "emberlamp"
}
```

## Quick Links

- [Config Repo](https://github.com/emberlamp/config) - Repository list
- [Skills Repo](https://github.com/emberlamp/skills) - Agent capabilities
- [Bot Repo](https://github.com/emberlamp/bot) - Automation workflows
- [SWE Agent](https://github.com/emberlamp/swe-agent) - Agent template
- [CLI](https://github.com/emberlamp/cli) - Master CLI

## Contributing

1. Make changes in local cloned repos (in /tmp/emberlamp/)
2. Push changes - CI and Release workflows run automatically
3. For major changes, use conventional commits:
   - `feat:` for new features (triggers minor release)
   - `fix:` for bug fixes (triggers patch release)

---

## Summary: How We Control All Repos

### Centralized System

| Component | Purpose |
|-----------|---------|
| config/repos.json | Single source of truth for all 14 repos |
| skills repo | Agent capabilities and CLI extensions |
| swe-agent | Agent that knows all repos, can clone to /tmp |
| bot repo | Automation workflow for syncing/reporting |

### Automated Workflows

| Workflow | Trigger | Action |
|----------|---------|--------|
| CI | push to main | Lint & test |
| Release | push to main | Auto version bump, create tag & release |
| Automation | schedule/manual | Sync repos, backup, report |

### How It Works

1. Add a repo → Update config/repos.json
2. Code change → CI runs, then Release creates version bump + release
3. Need agent skills → Add to skills repo
4. Need automation → Use bot workflow

### Commands

```bash
# Clone all repos
python /tmp/swe-agent/agent.py clone-all

# List all repos
python /tmp/swe-agent/agent.py list

# Trigger release manually
gh workflow run release.yml -f version=minor -R emberlamp/repo
```

The entire emberlamp organization is now automated end-to-end!

© 2026 Emberlamp