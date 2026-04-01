# Seyola Skills

AI-powered business diagnostic tools for Claude Code. Built by [Adham Al Khaja](https://seyola.com).

## Install

```bash
git clone https://github.com/adhamalkhaja/seyola.git ~/.claude/skills/seyola
cd ~/.claude/skills/seyola && ./setup
```

That's it. Skills are now available in Claude Code.

## Skills

| Skill | What It Does |
|-------|-------------|
| `/consult` | Business diagnostic. Two modes: Diagnostic (existing business owners) and Builder (pre-business). Five forcing questions, 5-dimension scoring, constraint identification, forced alternatives, and a consult summary you can run again and again. |

More skills shipping soon.

## Update

```bash
cd ~/.claude/skills/seyola && git pull && ./setup
```

Or type `/seyola-upgrade` inside Claude Code.

## How It Works

Each skill is a `SKILL.md` file that Claude Code reads as instructions. The `setup` script symlinks them into `~/.claude/skills/` so they're discoverable as slash commands.

```
seyola/
├── setup                    # Install script
├── VERSION                  # Version tracking
├── CHANGELOG.md             # What's new
├── bin/                     # CLI utilities
│   ├── seyola-config        # Config management
│   └── seyola-update-check  # Version checker
├── skills/                  # Published skills
│   └── consult/
│       └── SKILL.md
├── seyola-upgrade/          # Self-upgrade skill
│   └── SKILL.md
└── knowledge/               # Shared reference files
```

## For Teams

Install into a specific project (not global):

```bash
git clone https://github.com/adhamalkhaja/seyola.git .claude/skills/seyola
cd .claude/skills/seyola && ./setup --local
```

Commit `.claude/skills/seyola/` to your repo. Teammates get the skills on `git clone`.

## Prefix Mode

By default, skills use flat names (`/consult`). If you have naming conflicts with other skills:

```bash
./setup --prefix    # Skills become /seyola-consult, /seyola-upgrade, etc.
./setup --no-prefix # Back to flat names
```

## Created By

**Adham Al Khaja** — Space engineer turned systems thinker. Building the infrastructure layer for consultants and coaches.

[seyola.com](https://seyola.com)
