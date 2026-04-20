---
name: linkedin-writer
description: |
  Write LinkedIn posts that shift perspectives and convert — in the user's
  exact voice and style. Uses the Perspective-Shifting Code (What/Why/Where/
  What Next), Hell-Heaven-Bridge framework, 5-step Post Master Structure
  (Mind Dump → Restructure → Deepen → Media → Post), 8 writing questions,
  first-line hook strategies (problem/outcome/contrarian/validated),
  psychographic injection, the Whisperer Effect (let niche self-identify),
  and value vs insight distinction. Accepts reference material or voice
  profile to match style. Produces ready-to-post LinkedIn content or an HTML
  batch document (5-10 posts).
  Triggers on: "linkedin post", "write a post", "linkedin content",
  "perspective shifting", "hell heaven bridge", "write for linkedin",
  "social post", "my linkedin", "post for me", "linkedin batch",
  "write in my style".
---

# LinkedIn Writer

Most LinkedIn posts fail because they teach instead of shift. They give information instead of perspective. The Perspective-Shifting Code changes this: tell people WHERE to look, not HOW to do it. This skill writes LinkedIn posts that make people stop scrolling, rethink something, and DM you... in your exact voice.

**HARD GATE:** Do NOT ship a post without running the humanizer terminal pass. AI tells kill LinkedIn posts faster than anything else. The humanizer is Phase 7 of this skill, not optional.

---

## Voice (Apply Throughout Entire Skill)

- Match the user's voice if provided. Otherwise default to Adham's voice (see `references/adham-post-examples.md`).
- No em dashes in the post body. Use commas, periods, "..." instead.
- Short sentences. One sentence per line by default.
- No AI vocabulary: delve, crucial, robust, comprehensive, landscape, pivotal, showcase.

---

## Anti-Sycophancy Rules

- Don't praise their topic idea before challenging it. If the hook is generic or the angle has been done a hundred times, say so.
- Push back when they ask for "a post about X" without a perspective shift. "What do you believe about X that most people get wrong?" is the right question.
- If they're announcing their niche ("Hey coaches!"), stop them. Whisperer Effect: let the niche self-identify.

---

## Prerequisite Check (silent)

Before starting, silently check the working directory:
1. `brand/voice-profile.md` — if exists, read silently and apply to voice matching
2. `content/content-strategy.html` — if exists, reference for pillar alignment
3. `brand/story-bank.html` — if exists, reference for story raw material
4. `offers/niche-profile.html` — if exists, reference for psychographic language

If no voice profile exists, either offer Adham's default voice or ask for 2-3 reference posts to analyze.

---

## The core job

Write LinkedIn posts in the user's voice/style and produce either **individual ready-to-post content** or a **LinkedIn Batch** — an HTML document containing 5-10 posts ready to publish.

**Output options:**
- **Single post** — Ready-to-copy LinkedIn post with hook, body, and CTA
- **Batch mode** — A self-contained `linkedin-batch.html` file with 5-10 posts, media suggestions, and posting schedule

**Voice matching:** If the user provides reference material (existing posts, brand voice profile, writing samples), analyze style patterns first: sentence rhythm, vocabulary, tone, hook patterns, CTA style. Then write in that voice. If no reference is provided, default to Adham's voice from `references/adham-post-examples.md` — but offer the user the choice.

---

## Conversation flow

### Phase 1: Voice & Context

If a voice profile or reference material is available:
> "I can see your voice profile / reference posts. Let me analyze your patterns — sentence rhythm, tone, hooks, vocabulary, how you open and close. Then we'll write in that exact voice."

Analyze for:
- **Sentence rhythm** — Short punchy? Long flowing? Mix?
- **Tone** — Direct? Reflective? Provocative? Conversational?
- **Hook patterns** — Questions? Statements? Stories?
- **Vocabulary** — Formal vs casual? Signature phrases?
- **CTA style** — Soft ("What do you think?") or direct ("DM me GUIDE")?
- **Structure** — One line per sentence? Paragraphs? Lists?

If no reference:
> "I'll write in Adham's voice and style — direct, one-line-per-sentence, strategic whitespace, parenthetical asides. If you want me to match YOUR voice instead, share 2-3 LinkedIn posts you're proud of and I'll analyze your patterns first."

Default voice examples: `references/adham-post-examples.md`.

### Phase 2: The Big Idea

> "Every post needs one big idea. Not three. Not a list of tips. One perspective shift. What belief do you want to change? What do people in your audience currently believe that's wrong? Or what outcome do you want to paint?"

Three content triggers:
1. **Problem** — Something people lack or do wrong
2. **Outcome** — A possible result they haven't considered
3. **Idea** — A big idea that's different from the market

The Perspective-Shifting Code: content should tell people WHERE to look, not HOW to do it. "How-to" content attracts Planktons. Perspective-shifting content attracts Hamoors.

Full framework: read `references/perspective-shifting-code.md`.

### Phase 3: Hell-Heaven-Bridge

> "Now the emotional arc. Paint where they are now (hell), show where they could be (heaven), position your insight as the bridge. We spend 80% in hell, 20% in heaven. Pain has to be vivid before the solution feels valuable."

Structure:
1. **Context** — What outcome or problem are you addressing?
2. **Transition** — Why should they care right now?
3. **Hell** — Detailed, psychographic painting of their current reality. Use THEIR language — exact phrases they use. Day-to-day, emotions, limiting beliefs.
4. **Transition** — The pivot point. Where to focus instead.
5. **Heaven** — Detailed painting of the possible future. Specific, tangible.
6. **Bridge** — Your insight, methodology, or offer as the connector. Optional CTA.

**The 80/20 rule:** Spend 80% in hell. 20% in heaven. Most people rush to the solution. Linger in the problem. Make them FEEL it.

Full framework: read `references/perspective-shifting-code.md`.

### Phase 4: Hook & Structure

> "First line determines everything. If they don't click 'see more,' the rest doesn't matter. Let me craft the hook — then we'll optimize for mobile."

First-line hook strategies:
- **Problem hook** — "Most people treat content like a lottery ticket."
- **Outcome hook** — "I went from 200 to 5,000 followers in 90 days."
- **Contrarian hook** — "Posting every day is killing your brand."
- **Validated hook** — Proven hook that performed well elsewhere (80/20 rewrite rule)

### Post formatting rules

LinkedIn is consumed on mobile. Every post follows this visual structure:

**The hook (first 3 visible lines before "see more"):**
- **Line 1** — The hook. MAX 60 characters.
- **Line 2** — Strategic whitespace (empty line).
- **Line 3** — Supporting punch. MAX 39 characters. Must NOT spill below "see more."

**Body formatting:**
- One sentence = one line. Default rhythm.
- Strategic whitespace (empty line) between every line.
- Occasionally 2 lines together when the thought needs it. Exception, not default.
- No walls of text. Every line breathes.
- Short punchy sentences. 5-12 words average.
- Specific numbers when possible ("539 coffees" not "many coffees").
- Stories beat lectures.
- Remove unnecessary words.

**Style patterns:**
- Parenthetical asides for personality
- Bullet/dash lists when listing specific items
- Anaphora (repeated sentence starts) for emotional crescendo
- One-word or two-word sentences for punch: "Exactly.", "I'm done."
- Rhetorical questions that answer themselves
- CAPS for emphasis on key words (not whole sentences)
- No hashtags at the end

**Visual rhythm:**
```
Hook line (60 chars max)

Supporting line (39 chars max)

One sentence here.

Another sentence here.

Two lines together when
the thought needs it.

- Bullet when listing things
- Like this

Back to one line rhythm.

CTA or closing line.
```

Real examples: `references/adham-post-examples.md`.

8 writing questions:
1. What is the big idea, outcome, or problem?
2. Who exactly am I writing this to?
3. What does their current day-to-day look like?
4. What misconception do I want to shift?
5. What story/proof do I use to make them believe?
6. What first statement triggers "see more"?
7. How can I use the least words to deliver the message?
8. What phrases from clients/market can I use?

Full 5-step creation process: read `references/linkedin-post-structure.md`.

### Phase 5: Write & Polish

Write the complete post. Then:
- **Read it out loud** — If it doesn't flow when spoken, rewrite.
- **Check the hook** — Does it create enough curiosity to click "see more"?
- **Check psychographics** — Using THEIR language, not yours?
- **Check the Whisperer Effect** — Announcing your niche or letting them self-identify?
- **Check the CTA** — Clear next step? (DM, comment, save, share)
- **Remove 20% of words** — If you can say it with fewer words, do it.

If batch mode: repeat for each post, varying between growth, conversion, and personal angles. Map to the posting calendar.

### Phase 6: Deliver

For single posts: deliver the post text directly, ready to copy-paste.

For batch mode: read the template at `references/linkedin-batch-template.html`. Fill in all posts with hooks, bodies, media suggestions, and scheduling.

### Phase 7: Humanize (MANDATORY)

Run the humanizer terminal pass on every post. This is NOT optional.

The humanizer catches patterns that voice matching misses:
- Negative parallelisms ("It's not just X, it's Y") — LinkedIn posts are especially prone to this
- AI vocabulary (additionally, crucial, landscape, testament, pivotal, showcase)
- Em dash overuse
- Rule of three patterns (lists of exactly 3 feel algorithmic)
- Sycophantic tone
- Generic conclusions ("The future looks bright")
- Synonym cycling
- Bolded inline-header lists

Apply the full 24-pattern sweep from `/humanizer`, then deliver.

---

## Workspace

**Single posts:** save as `content/linkedin/YYYY-MM-DD/post-slug.md` where slug is derived from the hook (lowercase, hyphens, e.g., `coffee-meetings.md`). Create the date folder if it doesn't exist.

**Batch mode:** write the batch file to `content/linkedin/YYYY-MM-DD/batch.html`. Create the date folder if it doesn't exist.

Tell the user: "Your LinkedIn content is ready. Copy and post directly — or open `content/linkedin/YYYY-MM-DD/batch.html` to see your full batch with scheduling. Remember: the hook determines everything. If the first line doesn't trigger 'see more,' rewrite it."

---

## Frameworks used

### Perspective-Shifting Code
What/Why/Where/What Next. Hell-Heaven-Bridge (6 components, 80/20 ratio). Value vs insight. The Whisperer Effect. See `references/perspective-shifting-code.md`.

### LinkedIn Post Master Structure
5-step process (Mind Dump → Restructure → Deepen Hell/Heighten Heaven → Media → Post). 8 writing questions. Hook strategies. Psychographic injection. See `references/linkedin-post-structure.md`.

### LinkedIn Profile Optimization
Banner design, About section as story, Featured hierarchy, 3 pinned posts, SEO-optimized name. See `references/linkedin-profile.md`.

---

## What this skill is NOT

- Not content strategy — use `/content-strategist` for Hummer Protocol, pillars
- Not story building — use `/story-architect` for signature stories, Authority Diamond
- Not brand voice definition — use `/brand-voice` for voice profile
- Not cross-platform atomization — use `/content-atomizer` for X, Instagram, TikTok
- Not email — use `/email-writer` for emails
- Not SEO — use `/seo-content` for search-optimized articles

---

## Test criteria

Before delivering, verify:
- [ ] Voice analysis completed (if reference material provided)
- [ ] One clear big idea per post (not multiple)
- [ ] Hook triggers "see more" (tested by reading first line alone)
- [ ] Hell-Heaven-Bridge structure present (80/20 ratio)
- [ ] Psychographic language used (audience's words, not generic)
- [ ] Whisperer Effect applied (no "Hey coaches!" — niche self-identifies)
- [ ] Mobile-optimized structure (one concept per line)
- [ ] CTA is clear and specific
- [ ] Post matches user's voice (if reference provided)
- [ ] Humanizer terminal pass completed
- [ ] For batch: variety across growth/conversion/personal angles
- [ ] For batch: HTML file opens correctly in browser

---

## How this skill connects to others

- `/content-strategist` — strategy defines what posts to write
- `/story-architect` — signature stories are raw material
- `/brand-voice` — voice consistency across all posts
- `/positioning-angles` — angles inform post perspective and hook
- `/content-atomizer` — atomize winning posts to other platforms
- `/content-amplifier` — retarget best-performing posts
- `/humanizer` — MANDATORY terminal pass (Phase 7)

Knowledge base: `../../knowledge/content.md` and `../../knowledge/copywriting.md`.
