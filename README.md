# Emberlamp Organization

Automated software engineering organization with centralized control.

## Overview

Emberlamp is a fully automated organization with 13 repositories managed through a centralized system.

## Architecture

### Central Control
- **config** - Single source of truth with repos.json
- **skills** - Agent capabilities and CLI extensions
- **swe-agent** - Agent that knows all repos
- **bot** - Automation workflow for syncing

### Repositories (13)

| Category | Repos |
|----------|-------|
| Applications | general |
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

© 2026 Emberlamp