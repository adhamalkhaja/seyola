# Research Eval Criteria

Binary yes/no checks for evaluating /research output quality. Use as a self-check before shipping a report.

Binary eval methodology for research quality.

---

## The 6 Evals

```
EVAL 1: Source Diversity
Question: Did the research use all 5 source types (Reddit/forums, YouTube/reviews, competitors, market data, authority voices)?
Pass: All 5 rounds completed with at least 2 sources fetched per round (10+ total sources minimum).
Fail: Any round skipped entirely, or only 1-2 source types used across the whole research.
```

```
EVAL 2: Cross-Referencing
Question: Are there at least 2 consensus findings (3+ sources from different types agreeing)?
Pass: Consensus section identifies 2+ findings, each backed by 3+ sources from at least 2 different source types.
Fail: No consensus findings, or "consensus" based on sources from only 1 type (e.g., 3 Reddit threads = 1 source type, not 3).
```

```
EVAL 3: Raw Language Authenticity
Question: Are captured quotes verbatim from real people with full source attribution?
Pass: 5+ quotes per category (pain/desire/objection), each with: exact quoted text in quotation marks, source platform, author/username where available, and link or reference.
Fail: Quotes appear paraphrased ("users generally feel..."), or fewer than 5 per category, or missing source attribution.
```

```
EVAL 4: Eureka Check Fired
Question: Does the synthesis include either a genuine Layer 3 insight OR an explicit "no contrarian insight found"?
Pass: Layer 3 produces a named insight ("EUREKA: Everyone does X because [assumption]. But [evidence] suggests [different conclusion].") OR states "No contrarian insight. Conventional wisdom is sound. The opportunity is in execution, not differentiation."
Fail: Layer 3 is skipped, or produces a vague statement ("there are opportunities"), or doesn't reference specific evidence from the research.
```

```
EVAL 5: Confidence Is Justified
Question: Is the overall confidence score backed by per-finding scores, not vibes?
Pass: Each finding has an individual confidence score (1-10) with reasoning (source tier, recency, messenger credibility). Overall confidence is clearly derived from the individual scores (not higher than the average of top findings).
Fail: Overall confidence appears arbitrary, or individual findings lack scores, or overall confidence exceeds the evidence quality.
```

```
EVAL 6: Report Completeness
Question: Does the HTML report have all 6 tabs populated with substantive content (not placeholders)?
Pass: Summary (key findings + confidence + eureka), Pain & Demand (verbatim quotes in 3 categories), Competition (3+ competitors in table), Market Context (data + authority voices), Evidence (full table with all sources), Next Steps (confirmed vs needs-data + skill recommendations) — all tabs have real data.
Fail: Any tab is empty, contains only placeholder text ({{PLACEHOLDER}}), or has fewer than 3 data points.
```

---

## How to Use These Evals

### Self-Check (during /research execution)
Before shipping the report in Phase 8, mentally run each eval. If any would FAIL, go back and fix it before generating the HTML.

### With Eval Runner
Run eval tests on /research with these 6 evals. Test inputs:

1. `/research market business coaching for SaaS founders at $10-50K MRR`
2. `/research competitor online course platforms for fitness coaches`
3. `/research pricing executive coaching in the Middle East`
4. `/research audience who buys $500+ personal development courses`

Runs per experiment: 3. Max score: 18 (6 evals x 3 runs).

### Quality Bar
- 6/6 on all runs = research is production-quality
- 5/6 consistently = one pattern needs fixing (mutate the SKILL.md)
- 4/6 or below = structural issue (review the methodology, not just the prompt)

---

## What Makes a GOOD Eval vs BAD Eval

**Good:** Binary (yes/no), specific enough to be consistent, not so narrow it games the eval.
**Bad:** Scales (1-7), vague ("is it good?"), or so narrow the skill optimizes for the eval instead of quality.

These 6 evals test the METHODOLOGY (did you do the work?) not the CONTENT (are the findings correct?). Content quality is tested by running the skill on real topics and checking findings against known data.
