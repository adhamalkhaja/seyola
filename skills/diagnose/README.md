# Seyola Diagnose

**Map, diagnose, and optimize your entire business with AI.**

The Seyola Diagnose pulls everything out of your head and turns it into clear visual diagrams — so you can see bottlenecks, automation opportunities, and exactly what to build next.

---

## Quick Setup

### Option 1: Claude Code (Recommended)

1. Open this folder in VS Code
2. Install the **Claude Code** extension (`Ctrl+Shift+X` → search "Claude Code")
3. Install the **Draw.io Integration** extension (for viewing diagrams)
4. Open Claude Code and type:

```
Let's do a business x-ray of my business
```

Claude interviews you about your business and generates your complete X-Ray.

### Option 2: Claude.ai (Web App)

1. Download this repo as a [ZIP file](https://github.com/the2hourclo/business-x-ray/archive/refs/heads/master.zip)
2. Go to [claude.ai](https://claude.ai) → Profile → Settings → Capabilities
3. Scroll to **Skills** → **Add Skill** → **Upload Skill** → drop the ZIP
4. Go to **Settings → Connectors** → **Add Connector** → paste `https://mcp.draw.io/mcp`
5. Start a new chat: *"Let's do a business x-ray of my business"*

The Draw.io MCP lets Claude generate and preview diagrams live in your conversation.

---

## What You Get

| Output | What It Shows |
|--------|---------------|
| **Business Map** | Your entire business on one screen — traffic, products, funnels, team, goals |
| **Bow-Tie Funnel** | Customer journey from stranger → paying customer → results |
| **Process Swimlanes** | WHO does WHAT with WHICH systems (3-level drill-down) |
| **24 Digital Assets** | Score the building blocks that make a business run without you |
| **Opportunity Roadmap** | Prioritized action plan based on what you discover |

---

## How It Works

Claude acts as a business consultant, asking you questions one at a time. You answer — it does all the heavy lifting.

1. **Business Map** — Extracts your traffic sources, products, funnels, team, and goals
2. **Bow-Tie Funnel** — Maps your customer journey from awareness to results
3. **Process Drill-Down** — Digs into how each process actually works, who does what, and which systems handle it
4. **Digital Assets** — Scores your 24 business building blocks and shows what to build next
5. **Roadmap** — Generates a prioritized action plan

### What It Finds

As you map your business, the AI flags:

- **Bottlenecks** — Steps slowing everything down
- **Automation opportunities** — AI or tools could handle this
- **High-value work** — Keep doing this yourself
- **Missing assets** — Templates, SOPs, and systems you need

---

## Viewing Diagrams

The X-Ray generates `.drawio` diagram files. To view and edit them:

**In VS Code:** Install the "Draw.io Integration" extension. Click any `.drawio` file and it opens visually.

**In Claude.ai:** Connect the Draw.io MCP server (Settings → Connectors → Add Connector → `https://mcp.draw.io/mcp`). Diagrams render inline in your conversation.

**In browser:** Go to [app.diagrams.net](https://app.diagrams.net) → File → Open from Device → select your `.drawio` file.

---

## Resume Later

Claude saves your progress as a YAML block. To pick up where you left off:

1. Start a new Claude conversation
2. Paste the progress block Claude gave you
3. Say *"Continue my Seyola Diagnose"*

---

## Getting Updates

You have collaborator access to this repo. To get the latest version:

**Git users:** `git pull` in this folder.

**ZIP users:** Download the latest ZIP from [this link](https://github.com/the2hourclo/business-x-ray/archive/refs/heads/master.zip).

---

## Folder Structure

```
business-x-ray/
├── SKILL.md                 ← Main skill file
├── workflows/               ← Step-by-step AI workflows
├── references/              ← Supporting methodology docs
├── examples/                ← Templates and examples
├── README.md                ← You are here
├── LICENSE
└── diagrams/                ← Your .drawio diagrams go here
```

---

## Need Help?

Email [rashid@thepeakperformer.io](mailto:rashid@thepeakperformer.io) — I'll personally help you get set up.

---

