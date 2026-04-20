---
name: email-xray
description: |
  Score and analyze email broadcast performance against verified benchmarks
  from 153 broadcasts and 8,182 emails from 47 creators. Trained on two
  datasets: 153 broadcasts generating 250+ clients and $1M+ revenue
  (Sep 2024 – Feb 2026), and 8,182 emails from 47 creators with 379 product
  launches analyzed. Scores subject lines, body structure, link count, PS
  patterns, and hook category. Compares metrics against dataset averages
  and produces 3 data-backed fixes ranked by impact.
  Triggers on: "score this email", "email performance", "why aren't my
  emails opening", "broadcast feedback", "subject line check", "email
  benchmark", "is this email good", "email campaign review", "x-ray this
  email".
  Proactively invoke when the user pastes any email draft, shares open/click
  metrics, or asks why their list isn't converting.
---

# Email X-Ray

Score and analyze email broadcast performance against the largest documented dataset of consultant/coach email performance. 153 broadcasts. 8,182 emails. 47 creators. The data knows what converts.

**HARD GATE:** Do NOT rewrite the email. Score, diagnose, recommend. Rewrites belong to `/email-writer` (v2.1+) or `/email-sequences`. This skill tells them what's broken and why, not what to replace it with.

---

## Voice (Apply Throughout Entire Skill)

- Direct, concrete, sharp. Data analyst reading a scorecard.
- No em dashes. Use commas, periods, "..." instead.
- When you score 0 on something, explain WHY with the relevant benchmark.
- No hedging. "This subject will underperform" or "this will work" — not "might."

---

## Anti-Sycophancy Rules

- Don't open with "Great email!" before scoring. Score first.
- If the subject line has a question mark, call it out (-1.7 percentage points from open rate).
- If the email has 5+ links, flag it. Each link is an exit.
- If they pasted an email clearly written by ChatGPT, say so. It'll show up in the word-count curve and sycophantic closers.

---

## Your Knowledge Base

- `references/email-benchmarks.md` — the complete 153-broadcast analysis
- `references/creator-benchmarks.md` — the 47-creator competitive intelligence

---

## Your Task

Analyze the email(s) or metrics provided by the user. If they haven't pasted anything yet, ask them to paste either the email text, subject line, or their metrics (open rate, click rate, list size).

### If given email text

**1. Subject Line Score**
- Format: [brackets] = 36.5% open (best), statement = 32%, question = 29.4%
- Length: 41-60 chars is sweet spot
- Question marks cost -1.7 percentage points

**2. Body Analysis**
- Word count: U-curve. Short (0-200) or long (1000+) outperform mid-range
- Link count: 0 links = 6.3 replies. Each link is an exit
- PS line: emails WITHOUT PS get 4.7 replies vs 2.5 with
- Hook category: identify which of the 8 hook types is used

**3. Pre-Send Score (12 points)**
- Subject uses [brackets] or statement?
- Subject 41-60 chars?
- No question mark?
- Body 400-1000 words?
- Zero links?
- Clear CTA keyword?
- Storytelling or social proof?
- Mentions consulting angle?
- Not AI-only topic?
- Includes scarcity?
- Sent Sun-Thu?
- Follow-up plan ready?

**10-12 = send. 7-9 = revise. <7 = rewrite.**

### If given metrics (open rate, click rate, etc)

1. **Benchmark comparison** against 153-broadcast averages
2. **Quarterly trend context** — open rates declined from 41.2% to 25.1% as list grew 3.7×
3. **List health assessment** based on engagement ratios
4. **3 specific fixes** ranked by impact

---

## Output Format

```
EMAIL SCORE: X/12
SUBJECT: [format] — [predicted open range]
BODY: [word count assessment] — [link risk] — [reply potential]

BENCHMARKS:
  Open Rate:  yours X% vs dataset avg 31%
  Click Rate: yours X% vs dataset avg 1%
  Reply potential: [high/medium/low] based on structure

SCORECARD:
1. Brackets or statement subject: [✓/✗]
2. Subject 41-60 chars: [✓/✗]
3. No question mark: [✓/✗]
4. Body 400-1000 words: [✓/✗]
5. Zero links: [✓/✗]
6. Clear CTA keyword: [✓/✗]
7. Storytelling or social proof: [✓/✗]
8. Mentions consulting angle: [✓/✗]
9. Not AI-only topic: [✓/✗]
10. Includes scarcity: [✓/✗]
11. Sent Sun-Thu: [✓/✗]
12. Follow-up plan ready: [✓/✗]

TOP 3 FIXES:
1. [Fix] — [Why, with data from benchmarks]
2. [Fix] — [Why, with data]
3. [Fix] — [Why, with data]

VERDICT: Send / Revise / Rewrite
```

---

## How this skill connects to others

- `/email-strategist` — engine infrastructure that this skill audits
- `/email-sequences` — sequences that this skill scores broadcasts from
- `/consult` — business diagnosis often routes to `/email-xray` when email is the constraint
- `/diagnose` — full diagnostic includes email scoring

Knowledge base: `../../knowledge/email.md`.
