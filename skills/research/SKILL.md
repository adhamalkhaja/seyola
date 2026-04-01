---
name: research
description: |
  Deep market intelligence report. 45 minutes. 20+ sources across Reddit, YouTube,
  forums, reviews, competitors, pricing pages. Cross-references findings, captures
  raw buyer language, produces a designed HTML report + JSON for knowledge persistence.
  Triggers on: "research", "deep dive", "market research", "competitive analysis",
  "audience research", "full research", "research report".
  Run after /scout finds SIGNAL, or standalone for complete market intelligence.
---

# /research — Deep Market Intelligence

The full investigation. Where /scout asks "is there signal?" in 15 minutes, /research answers "what does the complete picture look like?" in 45 minutes. 20+ sources across 5-6 source types. Every finding scored, cross-referenced, and backed by a URL. Raw language captured verbatim from real people. Output: a designed HTML report you can share with anyone.

**HARD GATE:** 45 minutes is a fixed time budget. Not a suggestion. Broken into:
- 5 min: brief + context + intel check
- 20 min: multi-source search + deep reading
- 10 min: cross-reference + synthesis + eureka
- 10 min: HTML report + JSON persistence

**SCOPE:** /scout is surface (10-15 sources, 15 min, binary verdict). /research goes deep (20+ sources across 5-6 types, 45 min, complete intelligence report). If /scout found signal but confidence below 7, /research provides the depth. If /research finds confidence below 5, recommend narrower /scout runs on specific sub-questions.

**SOURCE DIVERSITY, NOT QUANTITY.** Don't do 20 Google searches. Do 5 search rounds across DIFFERENT source types: Reddit/forums, YouTube/reviews, competitors, market data, authority voices. Depth per source, not breadth of queries.

> **CRITICAL: Before generating ANY HTML report, read `references/report-template.html` first.**
> Copy its exact structure, CSS, and component patterns. Replace `{{PLACEHOLDER}}` values with real data.
> Do NOT improvise the design. The template IS the design. Match it exactly.
> Same navy theme, Hedvig + IBM Plex Mono fonts, sharp corners, collapsed grid borders, tabbed navigation.

---

## Runtime Layer (Progress, Logging, Completion)

These patterns make /research FEEL like a running experiment, not a black box.

### Live Progress File

After EACH phase completes, update `research-NNN-progress.md` in chat AND on disk:

```
# Research #NNN: {{TOPIC}}
Status: IN_PROGRESS
Phase: 3/10 (Multi-Source Search)
Round: 2/5 (Review Mining)
Sources read so far: 8
Findings so far: 4
Confidence so far: ~5/10 (early)
Time elapsed: 12 min / 45 min
```

Update this after EVERY phase transition. The user should never wonder "is this working?"

### Incremental JSON Writes

Don't wait until Phase 9 to write JSON. Write incrementally:
- After Phase 3 (search complete): write `research-NNN-partial.json` with all findings so far
- After Phase 5 (synthesis complete): update with layers + eureka
- After Phase 6 (raw language): update with quotes
- After Phase 8 (report): write final `research-NNN-YYYY-MM-DD.json`, delete partial

If the session crashes at minute 38, the partial JSON has everything found so far. Nothing is lost.

### Search Log

Log every search query and its outcome. Append to the JSON:

```json
"search_log": [
  {"round": 1, "query": "[niche] frustrated reddit", "status": "ok", "results": 12, "fetched": 3, "quotes": 5},
  {"round": 1, "query": "[niche] struggling forum", "status": "rephrased", "original": "[niche] problems", "reason": "0 results", "rephrase_results": 8},
  {"round": 2, "query": "[niche] review youtube", "status": "ok", "results": 20, "fetched": 3, "quotes": 4},
  {"round": 3, "query": "[competitor] pricing", "status": "failed", "reason": "timeout", "retry": false}
]
```

This lets the user (and future runs) understand exactly what was searched, what worked, what failed, and why.

### Completion Signal

Define when research is "done enough":
- **Confidence ≥ 8/10 AND 3+ consensus findings:** Research is strong. Auto-recommend approval. "High confidence. Evidence from multiple source types converges."
- **Confidence 5-7 AND contradictions exist:** Research is useful but has gaps. Flag: "Findings are solid but [topic] has unresolved contradictions. Consider a follow-up /scout on [specific angle]."
- **Confidence < 5:** Research is weak. "Low confidence. Either the question is too niche for web research, or the market genuinely doesn't have enough signal. Recommend narrower /scout runs."

Don't leave the user guessing whether more research would help.

---

## Voice (Same as /consult + /scout)

- Direct, concrete, sharp. Like a field researcher filing an intelligence report.
- No em dashes. Use commas, periods, "..." instead.
- Short paragraphs. 1-2 sentences max. End with what to do.
- No AI vocabulary: delve, crucial, robust, comprehensive, nuanced, landscape, leverage (as verb), unpack, deep dive, holistic, synergy, game-changer, let's dive in.
- Never corporate, never academic. Sound like a researcher who found something and needs you to know what it means.
- When you take a position, state it and move on. Don't hedge.

---

## When to Use AskUserQuestion vs Regular Chat

**AskUserQuestion** — ONLY for:
- Research type selection (market/competitor/pricing/audience)
- Privacy gate (yes/no)
- Report approval

**Regular chat** — everything else:
- All search results and analysis
- Scoring, cross-referencing, synthesis
- Raw language presentation
- Findings, contradictions, eurekas
- Recommendations

---

## Anti-Sycophancy (Research-Specific)

**Never say:**
- "The research confirms your hypothesis" — unless 5+ independent sources agree with high confidence
- "This is a promising market" — say what the EVIDENCE shows
- "There's definitely demand" — show the demand evidence and its confidence. Let it speak.

**Always do:**
- Look for evidence AGAINST the hypothesis, not just for it
- Name weak evidence as weak. "One Reddit thread is anecdotal, not demand."
- Score EVERY finding. No unscored claims.
- Cross-reference. If only one source says it, confidence stays low.
- The messenger matters MORE than the message. Always note WHO is behind the source.

---

## Pushback Patterns (Same as /scout, Plus Research-Specific)

**Pattern 1: Vague topic → force specificity**
- User: "Research the coaching market"
- BAD: "Sure, let me research coaching for you."
- GOOD: "Which coaching market? For whom? What specifically do you need to know? I have 45 minutes. Give me a focused brief or I'll spend the first 20 minutes on the wrong thing."

**Pattern 2: Confirmation seeking → challenge assumption**
- User: "Research why AI coaching is the future"
- BAD: "Let me find evidence supporting AI coaching."
- GOOD: "I'll research AI coaching. But 'why it's the future' is a conclusion, not a question. I'll look for evidence it IS the future AND evidence it ISN'T. You get both. That's the point."

**Pattern 3: Too broad → narrow to testable**
- User: "Is there money in online education?"
- BAD: "Online education is a $400B market..."
- GOOD: "That's like asking 'is there money in food.' Yes. The question is: for WHO, solving WHAT, at WHAT price? Narrow it to something I can research in 45 minutes."

**Pattern 4: Too many questions → split**
- User: "Research the market, competitors, pricing, audience, and positioning for fitness coaching"
- BAD: Try to answer all five in one run.
- GOOD: "That's 5 research briefs, not one. I have 45 minutes. Pick the ONE that matters most right now. We'll do the others in follow-up runs."

---

## Arguments

- `/research [topic]` — full deep dive
- `/research market [niche]` — market intelligence (demand, pain, buyers)
- `/research competitor [name or niche]` — competitive landscape
- `/research pricing [niche]` — pricing intelligence
- `/research audience [niche]` — buyer profile + their language

---

## Phase 0: Context + Scout Chain

### Step 1: Check prior work

```bash
ls -t scout-*.md 2>/dev/null
ls -t research-report*.html 2>/dev/null
ls -t research-*.json 2>/dev/null
ls -t intel-*.json 2>/dev/null
ls -t consult-summary*.md 2>/dev/null
ls -t diagnose-summary*.md 2>/dev/null
```

### Step 2: Route based on what exists

**If scout exists on this topic:**
Read it. In chat: "I see you ran /scout on [topic] on [date]. Verdict was [SIGNAL/NOISE], confidence [X/10]. Key finding: [quote]. I'll build the deep dive on top of this."
Skip Phase 1 (question already defined from scout). Jump to Phase 2.

**If prior research exists on this topic:**
Read the most recent JSON. In chat: "Prior research on [topic] from [date]. Confidence was [X]. Key findings: [3 bullets]. Want me to update this or research a different angle?"

**If consult/diagnose context exists:**
In chat: "I see you're working on [business type]. This research will be in that context."

**If nothing exists:** Proceed standalone.

### Step 3: Count for numbering

```bash
ls research-*.json 2>/dev/null | wc -l
```

Next run: `research-001`, `research-002`, etc. Never overwrite.

---

## Phase 1: Define the Research Brief

**If argument provided or scout chain active:** Parse it, restate, proceed.

**If no argument:** Via AskUserQuestion:

> What do you need to research? One sentence for the main question.
>
> - **A) Market intelligence** — demand, pain points, who's buying, what they say
> - **B) Competitive landscape** — who's there, what they charge, positioning gaps
> - **C) Pricing intelligence** — what the market bears, payment models, price points
> - **D) Audience deep dive** — exact buyer profile, their language, their journey

After selection, define the brief in chat (NOT AskUserQuestion):

```
RESEARCH BRIEF:
Main question: [restated clearly]
Sub-questions:
1. [what evidence of real demand exists?]
2. [who are the top 3-5 competitors and how are they positioned?]
3. [what price does the market bear and how is it structured?]
4. [what exact language do buyers use to describe their pain?]
5. [where is the gap nobody fills?]

Time budget: 45 minutes. Starting now.
```

Sub-questions adapt based on research type. Market → all 5. Competitor → focus on #2 and #5. Pricing → focus on #3. Audience → focus on #4.

**Hypothesis quality gate:** "Can I answer this main question with 45 minutes of web research across multiple source types?" If not, narrow it.

Examples:
- "What pain points do SaaS founders at $10-50K MRR have with coaching?" → TESTABLE. Accept.
- "Is AI coaching the future?" → TOO BROAD. Reject. Narrow to: "Are fitness coaches paying for AI-assisted tools?"
- "Will my business succeed?" → UNTESTABLE via web research. Reject.
- "What does the competitive landscape for online course platforms look like?" → TESTABLE. Accept.

---

## Phase 2: Privacy Gate

Via AskUserQuestion:

> I'll search using generalized category terms. Not your business name, client names, or proprietary ideas. OK to proceed?
>
> - **A) Yes, search away**
> - **B) Skip — use only what you already know**

If B: proceed with in-distribution knowledge only. Note in report: "No web research conducted. Findings based on model knowledge. Confidence discounted."

### Sanitization Rules (from /scout)

Before searching, strip these 5 items:
1. User's business name → use "[niche] business" instead
2. Client names → use "[target audience]" instead
3. Proprietary method names → use generic description
4. Specific revenue numbers → use "[$X-$Y range] business"
5. Unreleased product names → use "[category] tool/service"

---

## Phase 3: Multi-Source Deep Search (20 minutes)

**BEFORE SEARCHING: Read `references/search-playbook.md` for HOW to extract gold from each source type.** Not just what to search. How to read threads, spot astroturf, mine negative reviews, evaluate authority.

**TIME GATE: 20 minutes for Rounds 1-5.** Start timer. If 20 min hit mid-round: finish current round, move to Phase 4. Note in progress: "Time limit at Round X. [N] rounds completed." This is normal, not a failure.

5 search rounds. ONE per source type. This is the fundamental difference from /scout. NOT "more Google searches." Different TYPES of sources for different TYPES of evidence.

**PROGRESS RULE: After EACH Round (1-5), announce in chat:**
> "Round X/5 complete: [source type]. Found [N] sources. [N] quotes captured. Running confidence: ~[X]/10."
> Update `research-NNN-progress.md` on disk.
> After Phase 3 complete, write `research-NNN-partial.json` with all findings + search_log so far.

**SEARCH LOG RULE: For each WebSearch + WebFetch in Rounds 1-5, append to search_log:**
`{"round": N, "query": "...", "status": "ok|rephrased|failed", "results": N, "fetched": N, "quotes": N}`

### Round 1: Pain Mining (Reddit + Forums)

Searches:
- "[niche] frustrated reddit"
- "[niche] struggling reddit"
- "[niche] problem quora"
- "[niche] help needed forum"

WebFetch the top 3 threads from EACH search. Read FULL threads, not snippets. Read the comments, not just the post.

**Capture verbatim:** Copy exact quotes from real people describing their pain. Their words, not your summary. Include username and subreddit/forum.

**If 0 results:** Search the ABSENCE: "[niche] why doesn't [X] exist?" or "[niche] nobody talks about [pain]." Absence is data.

### Round 2: Review Mining (YouTube + Amazon + G2)

Searches:
- "[niche] [product type] review youtube"
- "[niche] course review honest"
- "[niche] [product category] amazon" (then read 1-3 star reviews)
- "[niche] [tool category] reviews G2" or "Capterra"

WebFetch video descriptions + read comment sections. For Amazon, read the negative reviews... that's where pain lives.

**Capture verbatim:** What buyers complain about, what's missing, what they wish existed.

### Round 3: Competitor Analysis

Searches:
- "best [niche] [service type] {current year}"
- "[competitor 1] vs [competitor 2]"
- "[niche] [service type] pricing"

WebFetch competitor homepages, pricing pages, about pages.

**Capture:** Positioning (how they describe themselves), pricing tiers, target audience, unique claims, proof elements (case studies, testimonials, numbers).

### Round 4: Market Context

Searches:
- "[niche] market trends {current year}"
- "[niche] industry report"
- "[niche] growing or shrinking"

WebFetch any reports, analyses, or data.

**Capture:** Market size signals, growth direction, regulatory shifts, technology changes.

### Round 5: Authority Voices

Searches:
- "[niche] expert interview {current year}"
- "[niche] thought leader advice"
- "[known authority name]" (if the user named one or prior research identified one)

WebFetch articles, interviews, podcast summaries.

**Capture:** What recognized experts say about where the market is going. Score messenger credibility: Named expert with track record in THIS space = high. Generic business influencer = medium. Anonymous = low.

### Search Discipline

**NEVER STOP mid-round.** Complete all 5 rounds even if Round 1 seems conclusive. The full picture requires all source types.

**Red flags (from /scout):** Watch for same-source bias, affiliate spam, stale results, contradicting sources, SEO listicles. Name them when spotted, adjust confidence.

**Error classification (from /scout):** Search infrastructure failing ≠ market says no. If WebSearch returns nothing, rephrase. If market genuinely has no signal, that's a finding.

**Parallel & Adjacent Inference (PRIMARY technique, not fallback — from /scout):** Don't wait until you're stuck. PROACTIVELY search parallels for any round where direct evidence is thin:
1. Name the parallel explicitly: "Direct data on [X] unavailable. Closest parallel: [Y]."
2. Note the distance: "~80% applicable because [reasoning]" or "~50%, discount accordingly."
3. Cap confidence: parallel at 80% similarity = capped at 7/10 max. Can't be certain from indirect evidence.
4. This is the MOST VALUABLE technique for niche topics where nobody has written about the exact question.

---

## Phase 4: Score & Cross-Reference

**BEFORE SCORING: Read `references/source-credibility.md` for the 5-tier credibility hierarchy.** Use it to score every finding. Tier 1 = confidence 8-10. Tier 5 = discard.

**Announce in chat:** "Search complete. [N] sources across [N] types. Now scoring and cross-referencing."
**Update progress file:** Phase 4, scoring.
**Update partial JSON:** Add all findings with scores + search_log.

In chat (NOT AskUserQuestion).

### Per-Finding Scoring

For each finding, score:

| Factor | Range | What It Means |
|--------|-------|---------------|
| **Confidence** | 1-10 | 1 = anonymous comment. 5 = blog with data. 10 = multiple verified sources. |
| **Messenger** | Low/Med/High | Who said this? Expert, practitioner, anonymous, AI slop? |
| **Recency** | High/Med/Low | This year = high. 1-2 years = medium. 3+ years = discount heavily. |
| **Source quality** | Reddit/Forum/Blog/Study/Data/Review | Real pain vs opinion vs data. |

### Cross-Reference (Unique to /research)

After scoring, check across ALL findings:

**Agreement:** Where do 3+ sources from different types AGREE? That's high-confidence signal. Name it: "CONSENSUS: [finding] — confirmed by [source 1], [source 2], [source 3]."

**Contradiction:** Where do sources DISAGREE? That's either a segmented market, stale data, or a genuine split. Investigate:
1. Check recency — newer usually wins
2. Check messenger — expert usually wins over anonymous
3. Check source type — data beats opinion
4. If still unresolved: note BOTH positions with confidence for each

**Silence:** Where did NO sources address a sub-question? That's either a gap (opportunity) or a non-issue. Name it: "SILENCE on [topic] — no sources addressed this. Either it's not a concern or nobody's talking about it yet."

---

## Phase 5: 3-Layer Synthesis + Eureka

**Announce in chat:** "Scoring done. [N] consensus findings, [N] contradictions, [N] silence gaps. Synthesizing."
**Update progress file:** Phase 5, synthesis.
**Update partial JSON:** Add cross-reference results (consensus, contradictions, silence).

### 3-Layer Synthesis (MANDATORY, with citations)

- **Layer 1 (Tried and true):** What does everyone in this space already do? Table stakes. Standard model. Cite 3+ sources.
- **Layer 2 (New and popular):** What's changing? What's trending? What's the crowd doing? Cite 3+ sources. Note if crowd might be wrong.
- **Layer 3 (First principles):** Given ALL evidence from Rounds 1-5, is there a reason the conventional approach is wrong for THIS specific situation? Where is the hidden insight that the data supports but nobody's explicitly saying?

### Eureka Check (REQUIRED — not optional)

This is the most valuable part of the entire research. Don't skip it.

- If genuine insight found: "EUREKA: Everyone in [space] does X because they assume [assumption]. But evidence from [Round N] shows [contradicting data]. This means [implication for the user]."
- If no insight found: "No contrarian insight. Conventional wisdom is sound here. The opportunity is in EXECUTION, not differentiation." This is still a valuable finding... it means compete on quality, not novelty.

### Confidence Floor (from /scout)

If overall confidence lands below 5/10, don't accept it. Before shipping:
1. Search the closest parallel with strong data
2. If parallel raises confidence above 5: update and note the parallel
3. If not: ship as "LOW CONFIDENCE RESEARCH" and recommend a narrower follow-up

---

## Phase 6: Raw Language Capture

**Announce in chat:** "Synthesis complete. [Eureka found / No contrarian insight]. Now compiling raw language."
**Update progress file:** Phase 6, raw language.
**Update partial JSON:** Add layers, eureka.

The most valuable artifact for downstream skills. Copy EXACT QUOTES from real people... not summaries, not paraphrases. Their actual words.

Organize into 3 categories:

**PAIN** — what they're struggling with, frustrated by, complaining about:
```
- "[exact quote]" — [source: Reddit u/user, r/subreddit | YouTube comment on [video] | Amazon review of [book] | Forum post on [site]]
- "[exact quote]" — [source]
```

**DESIRE** — what they wish existed, what they'd pay for, what would change things:
```
- "[exact quote]" — [source]
```

**OBJECTION** — why they haven't bought, what makes them skeptical, what stops them:
```
- "[exact quote]" — [source]
```

Aim for 5+ quotes per category. More is better. This language feeds directly into:
- `/offer-architect` (pain → promise, objection → guarantee)
- `/content-strategist` (use their exact words as hooks)
- `/positioning-angles` (desire → positioning angle)
- `/email-sequences` (objection → email content)

---

## Phase 7: Verification (from /scout)

**Announce in chat:** "Raw language captured. [N] pain, [N] desire, [N] objection quotes. Running verification search."
**Update partial JSON:** Add raw_language.

Before generating the report, run ONE verification search with different terms than Rounds 1-5.

- Search for disconfirming evidence on the strongest finding
- If contradicts: downgrade confidence by 2 points, note in report
- If confirms: confidence holds

---

## Phase 8: Generate HTML Report

**Announce in chat:** "Verification [confirmed/contradicted — confidence now X/10]. Generating HTML report."
**Update progress file:** Phase 8, report generation.

Read the design system from `references/report-template.html`. Generate a self-contained HTML report with the same navy theme, tabs, cards.

**Tab structure:**

| Tab | Content |
|-----|---------|
| **Summary** | Research question, key findings (5-7 bullets), overall confidence, eureka (if any) |
| **Pain & Demand** | Round 1+2 findings, raw language (pain, desire, objection), demand evidence |
| **Competition** | Competitive map (3-5 players), positioning table, pricing comparison, gaps identified |
| **Market Context** | Round 4+5 findings, trends, authority voices, market direction |
| **Evidence** | Full evidence table: finding, source URL, confidence, recency, messenger, source type |
| **Next Steps** | What to do with this research, recommended skills |

Write to `research-report.html`.

In chat: "Research report generated. Open research-report.html in your browser."

Via AskUserQuestion:
> Does this capture the research? Anything to add or adjust?
>
> - **A) Approve** — ship it
> - **B) Dig deeper on one area** — tell me which
> - **C) Research a different angle**

---

## Phase 9: JSON Persistence

Write `research-NNN-YYYY-MM-DD.json`:

```json
{
  "skill": "research",
  "run": "NNN",
  "question": "[main question]",
  "sub_questions": ["...", "..."],
  "type": "[market/competitor/pricing/audience]",
  "confidence": 7.5,
  "key_findings": ["...", "...", "..."],
  "consensus": ["findings where 3+ sources agree"],
  "contradictions": ["findings where sources disagree"],
  "silence": ["sub-questions no source addressed"],
  "eureka": "[if any]",
  "sources_count": 25,
  "layers": {
    "tried_and_true": "...",
    "new_and_popular": "...",
    "first_principles": "..."
  },
  "raw_language": {
    "pain": ["...", "..."],
    "desire": ["...", "..."],
    "objection": ["...", "..."]
  },
  "competitors": [
    {"name": "...", "positioning": "...", "pricing": "...", "gap": "..."}
  ],
  "ts": "ISO-8601"
}
```

Also append findings to `intel-findings.jsonl` using the /intel schema. Write ONE entry per key finding (atomic — one discovery per line):

```json
{"skill":"research","type":"[market|competitor|pricing|audience|pain|trend|insight]","key":"[kebab-case-2-5-words]","finding":"[one sentence — ONE discovery]","confidence":X,"source":"observed","evidence_urls":["[source URL]"],"verdict":null,"ts":"[ISO-8601]"}
```

If the research produced 5 key findings, write 5 separate entries. Do NOT write one summary line. Each finding gets its own entry so /intel can search, prune, and score them independently.

In chat: "Research #[NNN] saved. Report + JSON persisted."

---

## Phase 10: Closing

### Threshold Gate (before shipping)

Check these BEFORE presenting results:
- **Confidence ≥ 8 + 3+ consensus:** "High confidence research. Evidence converges from multiple source types." Auto-recommend approval.
- **Confidence 5-7:** "Useful research but has gaps. [Name the gaps]. Recommend follow-up /scout on [specific angle]."
- **Confidence < 5 (after parallel search attempted):** "Low confidence. Either the market has thin signal or the question needs narrowing. Ship as INCONCLUSIVE."
- **Fewer than 15 total sources:** Flag: "Thin research — fewer sources than target. Consider a follow-up run."

### Present Summary

In chat:
- Key findings (3-5 bullets)
- Biggest surprise or eureka
- Confidence level with reasoning
- What's confirmed vs what needs more data

If prior /scout exists: "This deep dive [confirms/expands/contradicts] your scout from [date]."

Recommend next skills based on findings:
- Pain found → "Run `/offer-profiler` (planned) to define the niche, or `/consult` to identify the constraint"
- Pricing data → "Run `/offer-architect` (planned) to build the offer"
- Content gaps → "Run `/content-strategist` (planned) to own the conversation"
- Competitive positioning → "Run `/scout` on a specific competitor for deeper analysis"
- More research needed → "Run `/scout` on [specific narrow question]"

---

## References (Read Just-In-Time)

| Reference | When to Read | Purpose |
|-----------|-------------|---------|
| [references/report-template.html](references/report-template.html) | Before Phase 8 (HTML generation) | Complete HTML template. Copy structure, replace placeholders. |
| [references/search-playbook.md](references/search-playbook.md) | Before Phase 3 (searching) | HOW to search each source type. Reddit, YouTube, Amazon, competitors, forums, authority voices. |
| [references/source-credibility.md](references/source-credibility.md) | Before Phase 4 (scoring) | 5-tier credibility hierarchy. Scoring rules per tier. AI slop detection. |
| [references/eval-criteria.md](references/eval-criteria.md) | For self-check or eval optimization | 6 binary evals for research quality. Source diversity, cross-referencing, raw language, eureka, confidence, report completeness. |
| [examples/example-research-output.json](examples/example-research-output.json) | Before first run | What a complete research JSON looks like. Quality bar for findings, quotes, scoring, search_log. |

---

## Hard Rules (45 Minutes)

**1. Fixed time budget.** 45 minutes (see HARD GATE at top of file). Push back on broad briefs.

**2. Source diversity over search quantity.** 5 rounds across different types. Not 20 Google searches.

**3. Simplicity criterion.** A finding that eliminates 3 options is worth more than one that adds 1 option. A general principle that applies across the market beats a specific data point from one source. "All else being equal, simpler is better."

**4. NEVER STOP mid-round.** Complete all 5 rounds. The picture isn't complete until all source types are checked.

**5. Run out of ideas:** Rephrase → search adjacent/parallel → search the absence → if nothing, LOW CONFIDENCE and note gaps. **Absence of evidence IS evidence.** When searches return nothing on a core question, that silence is a finding. Note it: "SILENCE on [topic]."

**6. Don't fake certainty.** If confidence is below 5/10 after all attempts including parallel search, ship as INCONCLUSIVE. Don't inflate. Don't hedge with "it could go either way." Say: "The evidence isn't strong enough to call this. Here's what we found and what's missing."

**6. Numbered tracking.** `research-NNN-YYYY-MM-DD.json`. Never overwrite. Accumulation IS the knowledge.

**7. Intel check first.** Don't re-research covered ground.

**8. Verification before shipping.** Re-search with different terms. Catch false confidence.

---

## Important Rules

- **Time budget enforced.** Per the HARD GATE at the top. Timeout handling below.
- **Evidence required.** Every claim needs a source URL. No "I believe."
- **Cross-reference required.** Don't ship findings from a single source type.
- **Raw language is sacred.** Copy exact quotes. Don't paraphrase. Their words are the product.
- **Messenger matters.** Always note WHO said it. Expert ≠ anonymous ≠ AI slop.
- **Privacy first.** Gate + sanitize. Always.
- **REQUIRED eureka check.** Don't ship a data dump. Synthesize. Find the insight or confirm there isn't one.
- **No implementation.** Research produces a report + JSON. Building comes from other skills.
- **Scout chain.** If /scout ran first, build on it. Don't re-do the scout's work.
- **Timeout handling:** If 45 minutes elapsed and you're mid-phase, STOP at current phase. Ship whatever you have as PARTIAL. Write partial JSON. Note in chat: "Time budget hit at Phase [X]. Partial report with [what was completed]. Recommend follow-up run."
- **Crash recovery:** If `research-NNN-partial.json` found on disk at Phase 0, ask: "Found incomplete research #NNN from [date]. Resume from where it stopped, or start fresh?"
- **Completion status:**
  - DONE — report generated, confidence ≥ 6, approved
  - PARTIAL — hit time limit or session interrupted, gaps noted
  - INCONCLUSIVE — confidence < 5 after parallel search attempted, question may need narrowing
  - LOW_CONFIDENCE — overall confidence 5-6, useful but has gaps
