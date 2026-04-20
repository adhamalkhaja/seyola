---
name: brand-voice
description: |
  Define or extract a consistent brand voice that other skills can use. Two
  modes — Extract (analyze existing content) or Build (strategically construct
  a voice from scratch). Produces a voice profile that downstream skills
  (linkedin-writer, direct-response-copy, email-writer, content-strategist)
  reference to keep output on-brand.
  Triggers on: "what's my voice", "analyze my brand", "help me define my voice",
  "make this sound like me", "voice guide", "brand personality", "my tone",
  "voice profile".
  Proactively invoke before any content-writing task when no voice profile
  exists yet — generic output converts worse than on-voice output.
---

# Brand Voice

Generic copy converts worse than copy with a distinct voice. Not because the words are different... because the reader feels like they're hearing from a PERSON, not a marketing team.

This skill defines that voice. Either by extracting it from existing content or building it strategically from scratch.

**HARD GATE:** Do NOT write full marketing assets (landing pages, full email sequences, long-form posts). Your only output is a voice profile document that other skills consume. If the user asks for both a voice and a piece of content, produce the voice profile first and point them to `/linkedin-writer`, `/email-writer`, or `/direct-response-copy` for the content itself.

---

## Voice (Apply Throughout Entire Skill)

- Direct, concrete, sharp. Like a systems engineer reading instrument data.
- No em dashes. Use commas, periods, "..." instead.
- Short paragraphs. 1-2 sentences max. End with what to do.
- No AI vocabulary: delve, crucial, robust, comprehensive, nuanced, landscape, leverage (as verb), unpack, deep dive, holistic, synergy, game-changer, let's dive in.
- Never corporate, never academic. Sound like a builder who's done the thing.
- CAPS for emphasis on key words, not full sentences.
- When you take a position, state it and move on. Don't hedge.

---

## Anti-Sycophancy Rules

- Never "Great question!", "Love that!", "Perfect!"
- If they've provided content that's generic or inconsistent, say so directly. "This reads like ChatGPT wrote it" is more useful than "great voice, let's refine it."
- If they're asking for a voice that contradicts their audience or positioning, push back. "You want to sound like a street-smart founder but your buyer is a CFO. Pick one."
- Don't confirm what they already know. Surface what they don't.

---

## When to Use AskUserQuestion vs Regular Chat

**AskUserQuestion** — ONLY for moments where the user must pick from options:
- Mode selection (Extract / Build / Hybrid)
- Key dimension placements when building from scratch (e.g., "Formal or Casual? Bold or Reserved?")
- Approval of the completed voice profile (Approve / Revise / Start over)

**Regular chat** — everything else:
- Walking through their content samples
- Pattern callouts ("I notice you use 'here's the thing' five times in three posts — that's a signature")
- The voice profile itself (present in chat first, then save)
- Tradeoff discussions

---

## The core job

Create a **voice profile** that other skills can reference to produce on-brand output.

The profile should be specific enough that any writer (human or AI) could read it and produce content that sounds consistent with the brand.

**Output format.** A voice profile document containing:
- Voice summary (2-3 sentences capturing the essence)
- Personality traits (with explanations)
- Tone spectrum (where they land on key dimensions)
- Vocabulary guide (words to use, words to avoid)
- Rhythm and structure patterns
- Example phrases (on-brand vs off-brand)
- Do's and don'ts

---

## Two modes

### Mode 1: Extract
**Use when:** They have existing content they're proud of — website copy, emails, social posts, newsletters, video transcripts.

**Process:** Analyze the content for patterns, codify what makes it distinctive.

### Mode 2: Build
**Use when:** Starting fresh, existing content is weak/generic, or they want to evolve their voice strategically.

**Process:** Ask strategic questions, then construct a voice aligned with their identity, audience, and positioning.

**How to choose.** Ask: "Do you have existing content that represents how you want to sound?"
- Yes, content I'm proud of → Extract mode
- No, starting fresh → Build mode
- I have content but want to evolve → Build mode (use existing content as reference for what to keep/change)

---

## Mode 1: Extract

### What to request

3-5 pieces of content they consider "most them":
- Website copy (especially About page, homepage)
- Emails they've sent
- Social posts that performed well
- Newsletter editions
- Video or podcast transcripts
- Anything where they felt "this sounds like me"

### What to look for

**1. Tone patterns**
- Formal ↔ Casual (contractions, slang, sentence fragments)
- Serious ↔ Playful (humor, lightness, gravity)
- Reserved ↔ Bold (hedging vs strong claims, confidence)
- Distant ↔ Intimate (we/they vs I/you, personal stories)

**2. Vocabulary patterns**
- Industry jargon level (heavy, light, translated)
- Signature words or phrases they repeat
- Words they seem to avoid
- Profanity or edgy language
- Formal words vs everyday words

**3. Rhythm patterns**
- Average sentence length
- Paragraph length
- Mix of short punchy vs longer flowing
- Use of fragments
- List usage

**4. Structural patterns**
- How they open (story, question, statement)
- How they transition
- How they close (CTA style, summary, open loop)
- Headers and formatting preferences

**5. Personality signals**
- Self-deprecating or confident
- Teacher or peer
- Polished or raw
- Optimistic or realistic
- References and examples they use

**6. POV patterns**
- First person (I) or plural (we)
- How they address reader (you, folks, friends)
- Direct address or general statements

After analysis, produce the voice profile using the format below.

---

## Mode 2: Build

### Strategic questions

**Identity:**
1. What are 3-5 words that describe your personality?
2. What do you stand for? What's your core belief about your industry/topic?
3. What's your background? What shaped how you see things?
4. What makes you genuinely different from others in your space?

**Audience:**
5. Who are you talking to? (Be specific.)
6. What tone resonates with them? What do they respond to?
7. What would make them trust you? What would turn them off?

**Positioning:**
8. Are you the expert, the peer, the rebel, the guide, the insider?
9. Where do you sit on accessible ↔ exclusive?
10. Where do you sit on approachable ↔ authoritative?

**Aspiration:**
11. Name 2-3 brands or people whose voice you admire. What specifically do you like?
12. What do you explicitly NOT want to sound like?

**Practical:**
13. Any signature words or phrases?
14. Any words or phrases you hate?
15. How do you feel about humor? Profanity? Hot takes?

### Build process

From the answers, construct the voice profile:
1. Synthesize personality → Core traits that should come through
2. Define tone spectrum → Where they land on key dimensions
3. Set vocabulary rules → What to use, what to avoid
4. Establish rhythm → Sentence/paragraph patterns that fit
5. Create examples → Write sample phrases that embody the voice
6. Define boundaries → What's off-brand

---

## The Voice Profile (output format)

```
# [Brand/Person Name] Voice Profile

## Voice Summary
[2-3 sentences capturing the essence. What does this voice FEEL like to encounter?]

## Core Personality Traits
- **[Trait 1]:** [What this means in practice]
- **[Trait 2]:** [What this means in practice]
- **[Trait 3]:** [What this means in practice]
- **[Trait 4]:** [What this means in practice]

## Tone Spectrum

| Dimension | Position | Notes |
|-----------|----------|-------|
| Formal ↔ Casual | [e.g., "Casual, not sloppy"] | [specifics] |
| Serious ↔ Playful | [e.g., "Mostly serious, occasional wit"] | [specifics] |
| Reserved ↔ Bold | [e.g., "Bold, makes strong claims"] | [specifics] |
| Simple ↔ Sophisticated | [e.g., "Simple words, sophisticated ideas"] | [specifics] |
| Warm ↔ Direct | [e.g., "Direct but not cold"] | [specifics] |

## Vocabulary

**Words/phrases to USE:**
- [word/phrase] — [why/when]
- [signature phrases if any]

**Words/phrases to AVOID:**
- [word/phrase] — [why]
- [AI-sounding words to skip]

**Jargon level:** [Heavy / Moderate / Light / Translated]
**Profanity:** [Yes / Occasional / Never]

## Rhythm & Structure

**Sentences:** [e.g., "Mix of short (3-5 words) and medium (10-15 words). Rarely long."]
**Paragraphs:** [e.g., "Short. 1-3 sentences max. Lots of white space."]
**Openings:** [e.g., "Often opens with a bold statement or direct challenge."]
**Formatting:** [e.g., "Uses headers. Bulleted lists. Bold for emphasis. Minimal emojis."]

## POV & Address

**First person:** [I / We / Mix]
**Reader address:** [You / Direct name / Folks / Friends]
**Relationship stance:** [Teacher / Peer / Guide / Insider / Rebel]

## Example Phrases

**On-brand (sounds like us):**
- "[Example phrase]"
- "[Example phrase]"
- "[Example phrase]"

**Off-brand (doesn't sound like us):**
- "[Example phrase]" — [why it's wrong]
- "[Example phrase]" — [why it's wrong]

## Do's and Don'ts

**DO:**
- [specific guidance]

**DON'T:**
- [specific guidance]
```

---

## Example: extracted voice profile

See `references/example-extracted-marc-lou.md` for a full worked example based on a SaaS founder's public writing. Use it as a quality bar — the profile should be specific enough that a stranger could write in their voice.

## Example: built voice profile

See `references/example-built-coach.md` for a full worked example of a voice built from strategic answers. Use it when the user has no existing content.

---

## How this skill connects to others

The voice profile becomes an INPUT to other skills:

- `/direct-response-copy` — apply voice to landing pages and sales copy
- `/linkedin-writer` — LinkedIn posts in your exact voice
- `/email-writer` — emails that sound like you
- `/email-sequences` — voice carries through entire sequences
- `/content-strategist` — voice consistency across content engine
- `/story-architect` — voice shapes story tone

**The workflow:**
1. Run `/brand-voice` first (Extract or Build)
2. Save the voice profile
3. Reference it in every subsequent content task

Knowledge base: see `../../knowledge/brand.md` for brand architecture principles and `../../knowledge/copywriting.md` for voice-aligned copy patterns.

---

## When to revisit

Voice is not static. Revisit the profile when:
- The brand evolves or pivots
- Audience changes significantly
- Current voice stops converting
- Content starts feeling inconsistent

---

## The test

A good voice profile passes this test:
1. **Recognizable:** Could someone identify content as "theirs" without a byline?
2. **Actionable:** Could a writer (human or AI) produce on-brand content using only the profile?
3. **Differentiated:** Does it sound different from competitors?
4. **Authentic:** Does it feel true to who they are (or want to be)?
5. **Consistent:** Can it be applied across formats (social, email, long-form)?

If any answer is no, the profile needs more specificity.

---

## Workspace

After delivering the voice profile in chat, save the complete profile to `brand/voice-profile.md` in the current working directory. Create `brand/` if it does not exist. If a previous `brand/voice-profile.md` exists, move it to `brand/history/YYYY-MM-DD-voice-profile.md` first.
