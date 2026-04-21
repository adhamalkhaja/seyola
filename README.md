# Seyola Skills

![version](https://img.shields.io/badge/version-2.0.0-0a1f3d?style=flat-square&labelColor=0a1f3d&color=e8d9a0)
![skills](https://img.shields.io/badge/skills-17-0a1f3d?style=flat-square&labelColor=0a1f3d&color=e8d9a0)
![departments](https://img.shields.io/badge/departments-5-0a1f3d?style=flat-square&labelColor=0a1f3d&color=e8d9a0)
![workflows](https://img.shields.io/badge/workflows-15-0a1f3d?style=flat-square&labelColor=0a1f3d&color=e8d9a0)
![license](https://img.shields.io/badge/license-MIT-0a1f3d?style=flat-square&labelColor=0a1f3d&color=e8d9a0)

AI-powered business infrastructure for consultants and coaches. One Advisor, four Departments, 17 workflows. Built by [Adham Alkhaja](https://seyola.com).

## Install

```bash
git clone https://github.com/adhamalkhaja/seyola.git ~/.claude/skills/seyola
cd ~/.claude/skills/seyola && ./setup
```

That's it. Skills are now installed and discoverable.

## The Team

Hire an advisor to find what's broken. Deploy four departments to fix it.

### Advisor — `finds the constraint, routes the work`

| Skill | What It Does |
|---|---|
| `/consult` | Five forcing questions, 5-dimension scoring, constraint identification. Diagnostic or Builder mode. |
| `/diagnose` | Full business diagnostic with HTML report. Progressive interview, bow-tie funnel, process swimlanes, 24-asset scorecard. |
| `/briefing` | Weekly retrospective. Tracks promises vs delivery, metrics, streaks. |

### Research — `finds the truth, remembers the findings`

| Skill | What It Does |
|---|---|
| `/scout` | 15-minute market intelligence scan. SIGNAL or NOISE verdict. |
| `/research` | 45-minute deep intelligence report. 20+ sources, HTML report, JSON for persistence. |
| `/intel` | Research knowledge base. Shows, searches, prunes findings. Detects stale and contradictions. |

### Marketing — `your voice, your content, shipped`

| Skill | What It Does |
|---|---|
| `/brand-voice` | Extract or build a voice profile. Foundation for all content. |
| `/content-strategist` | Hummer Protocol content engine blueprint. |
| `/linkedin-writer` | LinkedIn posts using the Perspective-Shifting Code. |

(`/humanizer` runs as a terminal pass on all content, automatically.)

### Sales — `define the buyer, build the offer, score it against $1M+`

| Skill | What It Does |
|---|---|
| `/offer-profiler` | Five Ps, PFC avatar, "I Help" statement. |
| `/offer-architect` | 15-section Offer Document. The single most important sales asset. |
| `/offer-check` | Scores any offer against 16 iterations that did $1M+. |

### Operations — `build the email engine, write the sequences, audit the broadcasts`

| Skill | What It Does |
|---|---|
| `/email-strategist` | Email Engine Blueprint. ESP, DNS, magnets, automation architecture. |
| `/email-sequences` | Welcome, conversion, launch, nurture, re-engagement sequences. |
| `/email-xray` | Scores broadcasts against 153-broadcast dataset and 8,182 emails from 47 creators. |

## Update

```bash
cd ~/.claude/skills/seyola && git pull && ./setup
```

Or run `/seyola-upgrade` from an agent session.

## How It Works

Each skill is a `SKILL.md` file your agent reads as instructions. The `setup` script symlinks them into `~/.claude/skills/` so they're discoverable as slash commands.

```
seyola/
├── setup                    # Install script
├── VERSION                  # Version tracking
├── CHANGELOG.md             # What's new
├── bin/                     # CLI utilities
│   ├── seyola-config        # Config management
│   └── seyola-update-check  # Version checker
├── skills/                  # 17 shipped skills
│   ├── consult/
│   ├── diagnose/
│   ├── briefing/
│   ├── research/
│   ├── scout/
│   ├── intel/
│   ├── brand-voice/
│   ├── content-strategist/
│   ├── linkedin-writer/
│   ├── humanizer/
│   ├── offer-profiler/
│   ├── offer-architect/
│   ├── offer-check/
│   ├── email-strategist/
│   ├── email-sequences/
│   ├── email-xray/
│   └── seyola-upgrade/
└── knowledge/               # Shared reference files
    ├── brand.md
    ├── content.md
    ├── copywriting.md
    ├── email.md
    ├── growth.md
    ├── offer.md
    └── strategy.md
```

## For Teams

Install into a specific project (not global):

```bash
git clone https://github.com/adhamalkhaja/seyola.git .claude/skills/seyola
cd .claude/skills/seyola && ./setup --local
```

Commit `.claude/skills/seyola/` to your repo. Teammates get the skills on `git clone`.

## Prefix Mode

By default, skills use flat names (`/consult`). If you have naming conflicts:

```bash
./setup --prefix    # Skills become /seyola-consult, /seyola-upgrade, etc.
./setup --no-prefix # Back to flat names
```

## Created By

**Adham Alkhaja** — Space engineer turned systems thinker. Building the infrastructure layer for consultants and coaches.

[seyola.com](https://seyola.com)
