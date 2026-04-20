---
name: email-sequences
description: |
  Build complete email sequences that convert subscribers into customers —
  welcome (7-email Deliver-Connect-Value-Bridge-Pitch arc), nurture (ongoing
  value), conversion (4-7 email Open-Desire-Proof-Objection-Close), launch
  (6-10 email Seed-Open-Value-Proof-Close with cart timing), re-engagement
  (3-4 email pattern interrupt), and post-purchase (onboarding + upsell).
  Produces a professional HTML Email Sequence Plan.
  Triggers on: "write welcome emails", "email sequence", "nurture sequence",
  "convert my list", "onboarding emails", "launch sequence", "drip campaign",
  "email funnel", "welcome emails", "conversion emails", "launch emails",
  "re-engagement", "post-purchase sequence".
---

# Email Sequences

Most lead magnets die in the inbox. Someone downloads your thing, gets one "here's your download" email, and never hears from you again. Or worse, gets blasted with "BUY NOW" before you've earned any trust.

The gap between "opted in" and "bought" is where money is made or lost. This skill builds the sequences that bridge that gap.

**HARD GATE:** Do NOT ship the sequence plan without running the humanizer terminal pass on every email's copy direction. Sequences run for months — AI tells compound across 7-10 emails.

---

## Voice (Apply Throughout Entire Skill)

- Direct, concrete, sharp.
- No em dashes. Use commas, periods, "..." instead.
- Short paragraphs.
- No AI vocabulary: delve, crucial, robust, comprehensive, landscape, pivotal, showcase.

---

## Anti-Sycophancy Rules

- When they want to pitch in email 1, stop them. DELIVER first. Trust is the currency.
- When emails can be read in any order, call it out. Each email must build on the last.
- When timing is "send whenever," insist on a calendar. Arbitrary timing means no emotional arc.
- When they propose 14 emails without a branch, simplify. Fewer emails that actually get opened beats more that get deleted.

---

## Prerequisite Check (silent)

Before starting, silently check the working directory:
1. `brand/voice-profile.md` — if exists, read and apply during writing
2. `offers/offer-document.html` — if exists, reference (what sequences pitch)
3. `emails/email-strategy.html` — if exists, reference (magnets, tags, automations)
4. `emails/email-sequence.html` — if exists, this is an update. Ask revise or replace.

If no offer doc exists, gather minimum info inline (Phase 1).

---

## The core job

Build a strategic email sequence plan that delivers value before asking, builds trust through genuine connection, creates desire for the paid offer, and converts without being sleazy.

**Output.** A self-contained `emails/email-sequence.html` file containing:
- Sequence context card (lead magnet, offer, price, bridge)
- Sequence overview table (all sequences with purpose, length, timing)
- Welcome sequence detail (7 emails with subject, purpose, timing, structure)
- Conversion sequence detail
- Launch sequence detail with day-by-day timeline
- Nurture sequence outline
- Re-engagement sequence detail
- Architecture diagram (Straight/Branch/Hybrid)
- Timing calendar view

---

## Conversation flow

Strategic building session. Each sequence type gets proper attention. These emails will run for months or years.

### Phase 1: Sequence Context

> "Let's build your email sequences. First: what's the lead magnet people opt in for? What's the paid offer you're bridging to? What's the price point?"

Pull context from prior skill outputs if available. If standalone, also ask:
- What's your voice/brand? (Run `/brand-voice` if not defined.)
- Main objections — why might they NOT buy?
- The bridge — how does free → paid make logical sense?

### Phase 2: Welcome Sequence

> "Welcome sequence is the most important one. First impressions compound. We'll use DELIVER → CONNECT → VALUE → BRIDGE → PITCH — 7 emails over 12 days."

Each email:
1. **Email 1: Deliver** (Day 0) — Give them what they came for + micro-CTA (reply)
2. **Email 2: Connect** (Day 2) — Share your story, build rapport
3. **Email 3: Value** (Day 4) — Teach something useful, quick win
4. **Email 4: More Value** (Day 6) — Different angle, builds authority
5. **Email 5: Bridge** (Day 8) — Show the gap, hint at what's possible
6. **Email 6: Soft Pitch** (Day 10) — Introduce the offer, handle objections
7. **Email 7: Direct Pitch** (Day 12) — Make the clear ask

Each with subject line formula, structure, purpose, and timing. Full framework: `references/welcome-sequence-framework.md`.

### Phase 3: Conversion Sequence

> "Conversion sequence — when you're ready to pitch. OPEN → DESIRE → PROOF → OBJECTION → URGENCY → CLOSE."

4-7 email framework:
1. **Open** — Introduce offer, core promise
2. **Desire** — Paint the transformation, show the gap
3. **Proof** — Testimonials, case studies, results
4. **Objection** — Handle the biggest "but..."
5. **Urgency** — Why now matters (if authentic)
6. **Close** — Final push, clear CTA
7. **Last Call** — Deadline reminder (if applicable)

Timing: every 2 days standard, daily for launches. Full framework: `references/conversion-launch-sequences.md`.

### Phase 4: Launch Sequence

> "For time-bound campaigns — product launches, cohort opens, promotions. More intense: 6-10 emails with a tight timeline."

Timeline:
- **Pre-Launch** (Day -3, -1) — Seed interest, build anticipation
- **Cart Open** (Day 0) — Morning announcement + evening different angle
- **Mid-Launch** (Day 2-5) — Value deep-dive, social proof, objection handling
- **Cart Close** (Day 6-7) — 48hr warning, 24hr warning, final hours, last call

Full framework and timing map: `references/conversion-launch-sequences.md`.

### Phase 5: Nurture & Re-engagement

> "Not everyone buys on first pass. Nurture keeps you valuable. Re-engagement brings back the cold ones."

- **Nurture** — Ongoing value, weekly or 2x/week, 111 Framework
- **Re-engagement (3-4 emails)** — Pattern Interrupt → Pure Value → Direct Question → Final (removing from list creates urgency)
- **Post-purchase (4-6 emails)** — Welcome/onboard → Quick win → Community invite → Check-in → Upsell bridge → Referral ask

Full frameworks: `references/nurture-reengagement.md`.

### Phase 6: Architecture Selection

> "Which architecture fits your stage? Straight Line is simplest. Branch is behavior-based. Hybrid is full lifecycle."

- **Straight Line** — Email 1 → 2 → 3 → Pitch. No branches.
- **Branch** — Clicked? → YES: Pitch / NO: More value. Requires automation.
- **Hybrid** — Welcome → Wait → Conversion → No purchase → Nurture. Full lifecycle.

Full patterns and timing tables: `references/sequence-architecture.md`.

### Phase 7: Generate the Sequence Plan

Read the template at `references/email-sequence-template.html`. Fill in all placeholder sections with the user's actual sequences. Write the completed file to `emails/email-sequence.html`.

### Phase 8: Humanize (MANDATORY)

Run the humanizer terminal pass on all email subject lines and copy directions. This is NOT optional.

Apply the full 24-pattern sweep from `/humanizer`. Special attention to:
- Subject lines with AI vocabulary
- Negative parallelisms in openers
- Rule of three in pitch emails
- Generic conclusions in closers
- Sycophantic tone in thank-you emails

---

## Workspace

Create `emails/` if it doesn't exist. If `emails/email-sequence.html` already exists, move it to `emails/history/YYYY-MM-DD-email-sequence.html` first. Write the new file to `emails/email-sequence.html`.

Tell the user: "Your Email Sequence Plan is ready. Open `emails/email-sequence.html` in your browser. Update it as your offer and voice evolve."

---

## Frameworks used

### Welcome Sequence Framework
7-email DELIVER → CONNECT → VALUE → BRIDGE → PITCH progression. See `references/welcome-sequence-framework.md`.

### Conversion & Launch Sequences
Conversion (OPEN → DESIRE → PROOF → CLOSE) and Launch (SEED → OPEN → VALUE → CLOSE). See `references/conversion-launch-sequences.md`.

### Sequence Architecture
Straight Line, Branch, Hybrid patterns with send frequency tables. See `references/sequence-architecture.md`.

### Nurture & Re-engagement
Ongoing nurture, 3-4 email re-engagement pattern, post-purchase onboarding. See `references/nurture-reengagement.md`.

---

## What this skill is NOT

- Not email engine planning — use `/email-strategist` for ESP, DNS, magnets, automations
- Not individual email writing — use `/email-writer` (v2.1+)
- Not email health monitoring — use `/email-xray` for scoring
- Not landing page copy — use `/direct-response-copy` (v2.1+)

---

## Test criteria

Before delivering, verify:
- [ ] At least 1 complete sequence designed (all emails outlined)
- [ ] Each email has: purpose, subject line, timing, structure, CTA
- [ ] Welcome sequence follows DELIVER → CONNECT → VALUE → BRIDGE → PITCH
- [ ] Architecture chosen (Straight/Branch/Hybrid)
- [ ] Timing is realistic and mapped
- [ ] Copy direction sounds human (not corporate, not guru, not AI)
- [ ] One CTA per email enforced
- [ ] Value-to-pitch ratio appropriate for price point
- [ ] Humanizer terminal pass completed
- [ ] HTML file is self-contained and opens correctly in browser

---

## How this skill connects to others

- `/email-strategist` — infrastructure exists before sequences run
- `/offer-architect` — offer doc is what sequences pitch
- `/brand-voice` — voice consistency across all emails
- `/email-xray` — after sequences ship, score broadcasts
- `/humanizer` — MANDATORY terminal pass (Phase 8)

Knowledge base: `../../knowledge/email.md` and `../../knowledge/copywriting.md`.
