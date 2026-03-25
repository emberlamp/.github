# Emberlamp Organization

✨ Fully automated software engineering organization with centralized control.

[![Release](https://img.shields.io/github/v/release/emberlamp/general?include_prereleases&label=latest)](https://github.com/emberlamp/general/releases/latest)
[![CI](https://img.shields.io/github/actions/workflow/status/emberlamp/general/ci.yml?label=CI)](https://github.com/emberlamp/general/actions)
[![Contributors](https://img.shields.io/github/contributors/emberlamp/general?label=contributors)](https://github.com/emberlamp/general/graphs/contributors)

## Overview

Emberlamp is a fully automated organization with 14 repositories managed through a centralized system.

## Architecture

```
       ┌───────────┐
       │  config   │
       │repos.json │
       └─────┬─────┘
             │
┌────────────┼────────────┐
│            │            │
▼            ▼            ▼
 skills   swe-agent    bot
 repo      repo       repo
  └─────────┴──────────┘
            │
            ▼
       ┌──────────┐
       │   hub    │
       │(central) │
       └──────────┘
```

## Repositories (14)

### 🏛️ Central Control
| Repo | Purpose |
|------|---------|
| [hub](https://github.com/emberlamp/hub) | Central hub with architecture |
| [config](https://github.com/emberlamp/config) | Single source of truth (repos.json) |
| [skills](https://github.com/emberlamp/skills) | Agent capabilities & CLI extensions |
| [swe-agent](https://github.com/emberlamp/swe-agent) | Software engineering agent |
| [bot](https://github.com/emberlamp/bot) | Automation workflows |

### 📦 Applications
| Repo | Purpose |
|------|---------|
| [general](https://github.com/emberlamp/general) | Main application |

### 📋 Templates
| Repo | Purpose |
|------|---------|
| [react-template](https://github.com/emberlamp/react-template) | React + Vite + TypeScript |

### 🛠️ CLI Tools
| Repo | Purpose |
|------|---------|
| [cli](https://github.com/emberlamp/cli) | Master CLI for all repos |
| [gh-pin-repo](https://github.com/emberlamp/gh-pin-repo) | CLI for pinning repos |

### 📚 Resources
| Repo | Purpose |
|------|---------|
| [license](https://github.com/emberlamp/license) | MIT License |
| [warnings](https://github.com/emberlamp/warnings) | Warning messages |
| [json-repo](https://github.com/emberlamp/json-repo) | JSON schemas |
| [gitkeep](https://github.com/emberlamp/gitkeep) | Placeholder |

## 🤖 Automated System

Each repo has 5 workflows: **CI**, **Release**, **Automation**, **Label PRs**, **Emberlamp Auto Bot**

### 🚀 Release Automation
- `feat:` commits → minor version bump
- `fix:` commits → patch version bump

## 🔗 Quick Links

- [Hub](https://github.com/emberlamp/hub) - Start here
- [Config](https://github.com/emberlamp/config) - Repository list
- [Bot](https://github.com/emberlamp/bot) - Automation
- [Releases](https://github.com/emberlamp/general/releases) - Latest releases

## Contact

For inquiries, reach out through GitHub.

© 2026 Emberlamp