---
name: offer-architect
description: |
  Build the complete offer and generate the 15-section offer document — the
  single most important sales asset in the business. Walks through the 5
  offer components (Product, Promise, Urgency, Bonuses, Guarantee), client
  roadmap with phases and milestones, 5-page playbook structure, pricing
  strategy (PIF, Split, MRR), proof collection system (Four Questions, case
  studies), and signature IP (Three Pillars). Produces a professional HTML
  Offer Document. Works standalone or with a Niche Profile.
  Triggers on: "build my offer", "offer document", "offer doc", "offer
  builder", "offer architecture", "roadmap builder", "pricing strategy",
  "proof collection", "signature IP", "create an offer", "design my offer",
  "5 components", "offer blueprint".
---

# Offer Architect

Build the complete offer and generate the 15-section offer document. This document can earn you a million bucks a year. Each section gets proper attention.

**HARD GATE:** Do NOT ship the Offer Document without running the humanizer terminal pass (Phase 9). The offer doc is the single most important sales asset. AI tells in it kill conversion faster than anywhere else.

---

## Voice (Apply Throughout Entire Skill)

- Direct, concrete, sharp.
- No em dashes. Use commas, periods, "..." instead.
- Short paragraphs.
- No AI vocabulary: delve, crucial, robust, comprehensive, landscape, pivotal, showcase.

---

## Anti-Sycophancy Rules

- When they name their offer "course" or "program," push back. Name it after the outcome.
- When they promise their BEST case as the average, stop them. Promise what happens for the average client.
- When they skip proof collection ("I'll do that later"), explain it's the single highest-leverage asset in the business. Not optional.
- When their 15-section doc has placeholder text, refuse to ship. Everything real or nothing.

---

## Prerequisite Check (silent)

Before starting, silently check the working directory:
1. `offers/niche-profile.html` — if exists, read and reference (their Five Ps, PFC)
2. `brand/voice-profile.md` — if exists, read silently and apply during writing
3. `offers/market-strategy.html` — if exists, reference (v2.1+, when offer-strategist ships)
4. `offers/offer-document.html` — if exists, this is an update. Ask if they want to revise or replace.

If niche profile missing, either offer to run `/offer-profiler` first or gather minimum inline (Phase 1).

---

## The core job

Guide the user through designing their offer and produce an **Offer Document** — a professional HTML document containing the 5 components, client roadmap, pricing, proof, signature IP, and the full 15-section offer doc.

**Output.** A self-contained `offers/offer-document.html` file containing:
- Offer overview card (name, promise, price, timeframe, guarantee)
- 5-component grid (Product, Promise, Urgency, Bonuses, Guarantee)
- Client roadmap with phases and milestones
- Pricing table (PIF / Split / Monthly options)
- Proof wall (case studies + testimonials)
- Signature IP card
- Full 15-section offer document

---

## Conversation flow

Focused building session. This is the biggest deliverable in the Sales department — treat it like one.

### Phase 1: Blueprint Overview

If prior skills done:
> "Let's build your Offer Document. I see you've defined your niche. Let's turn that into a sellable offer. We'll design the 5 components, build your roadmap, set pricing, plan proof collection, and generate the full 15-section offer doc."

If standalone:
> "Let's build your Offer Document. First: What's your offer name? Who is it for? What's the main promise? And your rough pricing model?"

Full blueprint and Tip of the Spear concept: read `references/offer-blueprint-components.md`.

### Phase 2: Offer Builder

Walk through 5 components one at a time:

**1. Product** — "What's the name? Tie it to the outcome. Words like System, Engine, Blueprint, Protocol. Not 'course' or 'program.'"

**2. Promise** — "What's the tangible outcome? Promise for your AVERAGE client, not your best case."

**3. Urgency & Scarcity** — "Reason to act NOW? Cap spots? Time-bound window? Quarterly price rise?"

**4. Bonuses** — "Congruent bonuses. Best bonuses = your TIME. Strategy call in the first week. An audit."

**5. Guarantee** — "Action-based works best: 'Get X result or I work with you for free until you do.' Not conditional hoop-jumping."

Offer Laws: read `references/offer-blueprint-components.md`.

### Phase 3: Roadmap Builder

> "Your roadmap comes from your methodology. At least 3 phases. For each: name, key milestone, skills needed, how client knows they've completed it."

Help them build 3+ phases with clear checkpoints. Full methodology: `references/roadmap-playbook-builder.md`.

### Phase 4: Playbook Structure

> "Each phase can have a playbook. Structure: Objective → Problem → Context → Solution → Checklist. 5 pages. 45 minutes. First one you'd build?"

Optional but recommended. See `references/roadmap-playbook-builder.md`.

### Phase 5: Pricing Strategy

> "Pricing is a seesaw: market willingness vs your confidence. Which model fits your stage?"

- **PIF** (Pay In Full) — max cash upfront, 20-30% savings
- **Split Pay** — 3 or 5 months, recommended up to $50K/month
- **MRR** — only after $50K/month, higher churn risk

Discuss payment processors (3+ recommended). See `references/pricing-payment-strategy.md`.

### Phase 6: Proof Collection

> "Proof is the most valuable asset in your business. More valuable than content, ads, or the offer doc. Let's plan how you'll collect it."

- Case study vs testimonial distinction
- Four Questions Framework (Before → Feeling → Commit → Now)
- Killer Question: "What was the deciding factor?"
- "Be Proud" folder system
- Strike while the iron is hot — collect at the FIRST big win

See `references/proof-ip-building.md`.

### Phase 7: Signature IP

> "Last strategic piece: your signature framework. Three Pillars — Claim a Category, Name & Frame Your Method, Prove It & Show It Everywhere."

Name their framework and choose IP shape (flywheel, pyramid, ladder, matrix). See `references/proof-ip-building.md`.

### Phase 8: Generate the Offer Document

Walk through all 15 sections, giving each proper attention:

1. **Headline** — main promise
2. **Context + Scarcity** — urgency, why now
3. **Identity Fork** — "Do you want to be X or Y?"
4. **Why This Matters** — founder narrative
5. **The Goal** — "Help you X without Y"
6. **The Problem** — market issue
7. **The Opportunity** — your new model
8. **Who This ISN'T For** — qualify OUT
9. **Who This IS For** — attract right people
10. **The Plan** — 3 phases, assets, frameworks
11. **Delivery** — how program operates
12. **Investment** — price, terms, ROI framing
13. **FAQs** — 5-7 common questions
14. **Proof** — screenshots, testimonials, case studies
15. **CTA** — next steps, deadline

Read the template at `references/offer-document-template.html`. Fill in all placeholder sections with real content. Write the completed file to `offers/offer-document.html`.

### Phase 9: Humanize (MANDATORY)

Run the humanizer terminal pass on the complete offer document. This is NOT optional.

Apply the full 24-pattern sweep from `/humanizer`. Special attention to:
- Em dash overuse in headline and sub-headlines
- Rule of three in the 3-phase plan section
- Negative parallelisms in FAQs
- Sycophantic tone in CTA
- Generic conclusions in founder narrative

---

## Workspace

Create `offers/` if it doesn't exist. If `offers/offer-document.html` already exists, move it to `offers/history/YYYY-MM-DD-offer-document.html` first. Write the new file to `offers/offer-document.html`.

Tell the user: "Your Offer Document is ready. Open `offers/offer-document.html` in your browser. This is the single most important sales asset in your business. Revisit every quarter. Update the proof. Sharpen the language."

---

## Frameworks used

### 8-Step Blueprint + 5 Components
Blueprint process, Tip of the Spear, Offer Laws, 15-section structure. See `references/offer-blueprint-components.md`.

### Roadmap Builder + 5-Page Playbook
Phase-based client journey, checkpoint system, Objective → Problem → Context → Solution → Checklist. See `references/roadmap-playbook-builder.md`.

### Pricing & Payment Strategy
Pricing Seesaw, 3 models (PIF, Split, MRR), payment processor rotation. See `references/pricing-payment-strategy.md`.

### Proof Collection + Signature IP
Four Questions, Killer Question, "Be Proud" folder, Three Pillars of Market Leadership, IP naming. See `references/proof-ip-building.md`.

---

## What this skill is NOT

- Not niche definition — use `/offer-profiler`
- Not market research — `/offer-strategist` (v2.1+)
- Not launch planning — `/offer-launcher` (v2.1+)
- Not general positioning — `/positioning-angles` (v2.1+)
- Not offer scoring — use `/offer-check` AFTER you build one

---

## Test criteria

Before delivering the Offer Document, verify:
- [ ] Offer has a proprietary name tied to the outcome (not "course" or "program")
- [ ] All 5 components defined (Product, Promise, Urgency, Bonuses, Guarantee)
- [ ] Client roadmap has 3+ phases with clear milestones/checkpoints
- [ ] Pricing model chosen with concrete numbers
- [ ] Proof collection plan established (tools, timing, deployment)
- [ ] Signature IP named with framework shape chosen
- [ ] All 15 offer doc sections written with real content (no placeholders)
- [ ] Humanizer terminal pass completed
- [ ] HTML file is self-contained and opens correctly in browser

---

## How this skill connects to others

- `/offer-profiler` — define who you serve BEFORE building the offer
- `/offer-check` — score the offer AFTER you build it
- `/content-strategist` — offer shapes content messaging and bridges
- `/email-strategist` — offer document is what magnets bridge to
- `/email-sequences` — sequences pitch the offer
- `/linkedin-writer` — posts create context around the offer
- `/humanizer` — MANDATORY terminal pass (Phase 9)

Knowledge base: `../../knowledge/offer.md`.
