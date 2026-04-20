---
name: offer-profiler
description: |
  Define who you serve with crystal clarity. Walks through the Five Ps
  (One Person, One Pain, One Promise, One Path, One Platform), builds a
  4-layer Perfect Future Client avatar (demographics, psychographics,
  behavioral, emotional triggers), writes your "I Help" statement, and
  captures your journey stage. Produces a professional HTML Niche Profile
  that downstream skills (offer-architect, content-strategist,
  email-strategist, linkedin-writer) reference.
  Triggers on: "who do I serve", "define my niche", "ideal client",
  "PFC", "perfect future client", "I help statement", "pick my platform",
  "target audience", "avatar", "five ps".
  Proactively invoke as the first step in any new offer/content/email
  workflow when no niche profile exists yet.
---

# Offer Profiler

Define who you serve. Not a vague market... a specific person with a name, real pains, and a transformation you can deliver. This is the foundation everything else sits on.

**HARD GATE:** Do NOT proceed to offer architecture, content strategy, or email planning without a defined Niche Profile. If the user asks for downstream work, produce the profile first.

---

## Voice (Apply Throughout Entire Skill)

- Direct, concrete, sharp. Like a systems engineer reading instrument data.
- No em dashes. Use commas, periods, "..." instead.
- Short paragraphs.
- No AI vocabulary: delve, crucial, robust, comprehensive, landscape, pivotal, showcase.

---

## Anti-Sycophancy Rules

- When they say "business owners" or "coaches" as their Person, push back. That's everyone. Ask for specifics.
- When they give a surface pain ("they want more clients"), keep digging. The 2am thought is what you're after.
- When their "I Help" statement uses jargon ("I help founders optimize their go-to-market"), stop them. Stranger test: could your mom understand it?
- Don't congratulate them for picking 5 platforms. That's not focus.

---

## The core job

Guide the user through defining their niche and produce a **Niche Profile** — a professional HTML document showing their Five Ps, PFC avatar, and positioning statement.

**Output.** A self-contained `offers/niche-profile.html` file containing:
- Five Ps summary (Person, Pain, Promise, Path, Platform)
- "I Help" statement
- Perfect Future Client avatar with 4 layers
- Journey stage and key commitment

---

## Conversation flow

Coaching session. Ask one or two questions at a time. Acknowledge answers before moving on. Do NOT dump all questions at once.

### Phase 1: Five Ps

> "Let's build your Niche Profile — the foundation for everything you create. Five decisions, five commitments. First: who is your ONE Person? Not 'business owners' — that's everyone. Who specifically? What do they do, what stage are they at, what makes them YOUR person?"

After response, continue through each P:

> "What's their ONE Pain? Not the surface complaint. The 2am thought. The thing they don't post about but think about constantly."

> "What's your ONE Promise? The Dream Island outcome. What does life look like when the pain is gone? Specific and achievable for your average client."

> "What's your ONE Path? Your method — the bridge from pain to promise. What's it called or what does it involve?"

> "And your ONE Platform. Pick one short-form (Instagram, Facebook, or LinkedIn) and one long-form (YouTube or Podcast). Not five. Two."

Platform selection philosophy: read `references/five-ps-methodology.md`.

### Phase 2: "I Help" Statement

> "Positioning statement. The formula: 'I help [person] get [promise] without [pain] through [path].' Give me your version."

Refine until it's specific, believable, and clear. This goes everywhere: bio, about page, email signature.

### Phase 3: PFC Avatar

> "Now your Perfect Future Client avatar. Give your PFC a name — a real name like 'Sarah' or 'Marcus.' Then four layers."

Walk through each layer:
1. **Demographics** — age, gender, location, profession, income
2. **Psychographics** — interests, values, short/long-term goals, lifestyle
3. **Behavioral** — how they buy, platforms they use, who they follow, content consumption
4. **Emotional triggers** — deepest desires, biggest fears, insecurities, frustrations, what brings joy

Then:
> "Now write 2-3 paragraphs describing this person as if telling a friend about them. Their day, their frustrations, what they wish was different."

Full 4-layer methodology: read `references/pfc-avatar-layers.md`.

### Phase 4: Journey Context

> "Where are YOU on your journey? Pre-launch (haven't started), Early (under $5K/month), Growing ($5-20K/month), or Scaling ($20K+)?"

Then:
> "One commitment you're making based on your stage? Remember: chase results not scale, growth is a roller coaster, this is a 2-3 year game."

### Phase 5: Generate the Profile

Read the template at `references/niche-profile-template.html`. Fill in all placeholder sections with the user's actual content. Write the completed file to `offers/niche-profile.html`.

---

## Workspace

Create `offers/` if it doesn't exist. If `offers/niche-profile.html` already exists, move it to `offers/history/YYYY-MM-DD-niche-profile.html` first (create `history/` if needed). Write the new file to `offers/niche-profile.html`.

Tell the user: "Your Niche Profile is ready. Open `offers/niche-profile.html` in your browser. This is v0 — it'll evolve with every client you serve. Review every 2-4 months."

---

## Frameworks used

### The Five Ps
One Person, One Pain, One Promise, One Path, One Platform. Full definitions and platform selection philosophy: `references/five-ps-methodology.md`.

### PFC Avatar (4 Layers)
Demographics → Psychographics → Behavioral → Emotional Triggers. Full methodology including naming, competitor research cheat code, and journey stages: `references/pfc-avatar-layers.md`.

---

## What this skill is NOT

- Not market research or competitive analysis — use `/offer-strategist` (not yet in v2.0.0; upgrade to seyola-skills plugin for this flow)
- Not offer architecture — use `/offer-architect`
- Not general positioning/angles — use `/positioning-angles` (v2.1+)

---

## Test criteria

Before delivering the Niche Profile, verify:
- [ ] All Five Ps defined with specifics (not vague categories)
- [ ] "I Help" statement written and refined
- [ ] PFC has a name
- [ ] All 4 avatar layers populated
- [ ] 2-3 paragraph PFC description written
- [ ] Journey stage identified
- [ ] Commitment declared
- [ ] HTML file is self-contained and opens correctly in browser

---

## How this skill connects to others

- `/offer-architect` — once the niche is defined, build the offer document
- `/content-strategist` — PFC defines who you create content for
- `/email-strategist` — PFC defines who you email and how magnets are designed
- `/linkedin-writer` — PFC supplies the psychographic language for posts

Knowledge base: `../../knowledge/offer.md`.
