# Source Credibility Framework

The hierarchy of what counts as evidence. Read this BEFORE Phase 4 (Score & Cross-Reference).

The messenger matters MORE than the message. "Known expert says X" ≠ "random blog says X." Always check WHO is behind the source before scoring confidence.

---

## The 5 Tiers

### Tier 1: Gold (Confidence 8-10)

- **Named expert** with verifiable track record in THIS specific niche (not adjacent, not general)
- **Published research** with visible methodology (sample size, time period, data source)
- **Data from named companies** (e.g., "Stripe reported 289 transactions showed...")
- **Practitioner sharing specific numbers** from their own business ("I charge $3K/month and have 12 clients")
- **Government or industry body data** (Bureau of Labor Statistics, IBISWorld, etc.)

**Example:** Rob Walling (MicroConf founder, 3 SaaS exits) saying "bootstrapped SaaS founders at $10-50K MRR need operational coaching, not motivational coaching" = Tier 1.

### Tier 2: Strong (Confidence 6-7)

- **Named practitioner** sharing experience without hard numbers ("I've been coaching for 5 years and this is what I see")
- **Verified customer reviews** with 100+ reviews on a credible platform (G2, Capterra, Amazon Verified Purchase)
- **Industry reports** from known firms (McKinsey, First Round, a]z16z, etc.)
- **Forum posts** with detailed context, specific outcomes, and visible expertise
- **Journalist/analyst coverage** in known publications (TechCrunch, Forbes contributor with domain expertise)

**Example:** A G2 review of a coaching platform with 120 verified reviews averaging 4.2/5 = Tier 2.

### Tier 3: Moderate (Confidence 4-5)

- **Blog posts** with some data but unclear methodology
- **Single expert opinion** without corroboration from other sources
- **Small sample reviews** (10-50 reviews)
- **YouTube comments** with detail and specificity (but unverifiable)
- **Reddit posts** with upvotes and engagement but from anonymous accounts
- **Podcast guest claims** without cited sources

**Example:** A Reddit thread with 47 upvotes where u/SaaSgrinder42 describes their coaching experience in detail = Tier 3. Useful signal but can't verify.

### Tier 4: Weak (Confidence 1-3)

- **Anonymous comments** without specifics ("coaching is a scam")
- **Listicles and "top 10" articles** (usually SEO-driven, not researched)
- **Undated content** (can't determine if relevant or stale)
- **AI-generated SEO content** (recognizable by: perfect grammar, no personal experience, generic claims, unusual word choices)
- **Affiliate reviews** (recognizable by: always positive, affiliate links in body, "use my code" CTAs)
- **Social media posts** without engagement (< 5 likes, 0 comments)

**Example:** "Top 10 Best Business Coaching Programs 2026" from a site with affiliate links to all 10 = Tier 4. Discard or use only for identifying competitor names.

### Tier 5: Discard (Confidence 0 — do not use)

- **No attribution** (can't determine who wrote it or where the data comes from)
- **Contradicts ALL other sources** without explanation (likely an outlier or error)
- **Promotional content disguised as editorial** (press releases, sponsored posts not labeled as such)
- **Content from the entity being researched** (their own marketing copy is NOT evidence of market demand)
- **Outdated content** (5+ years in a fast-moving space)

**Example:** A company's own landing page claiming "95% of our clients see results" = Tier 5. That's marketing, not evidence.

---

## Scoring Rules

| Tier | Confidence Range | How to Use |
|------|-----------------|-----------|
| **Tier 1** | 8-10 | Anchor findings on this. If Tier 1 says X and Tier 3 says not-X, trust Tier 1. |
| **Tier 2** | 6-7 | Strong supporting evidence. Good for corroboration. |
| **Tier 3** | 4-5 | Useful signal but needs corroboration. Don't build a conclusion on Tier 3 alone. |
| **Tier 4** | 1-3 | Weak. Note it exists, discount heavily. Only use if pattern matches higher-tier sources. |
| **Tier 5** | 0 | Do not cite. Do not include in findings. Log in search_log as "discarded: [reason]." |

---

## Cross-Reference Rules

- **Consensus:** 3+ sources from different tiers ALL agree → confidence = highest tier's score
- **Contradiction:** Sources disagree →
  1. Higher tier wins over lower tier
  2. More recent wins over older (within same tier)
  3. If same tier and same recency: note BOTH positions, mark as "unresolved"
- **Silence:** No sources address a topic →
  - Could be a gap (opportunity)
  - Could be a non-issue (nobody cares)
  - Note it explicitly. Don't fill silence with assumptions.

---

## AI Slop Detection

How to recognize AI-generated content (Tier 4 at best, Tier 5 usually):

- Perfect grammar with zero personal voice
- Uses "delve," "crucial," "robust," "comprehensive," "nuanced" unnaturally frequently
- Claims are generic and could apply to any niche ("the market is growing rapidly")
- No specific numbers, names, dates, or experiences
- Article structure follows a rigid template (intro → 5 points → conclusion)
- "In conclusion" or "In summary" as a section header
- No author bio, or author bio is generic
- Published on a content mill or recently created domain

**When in doubt:** Check if the same article exists on other sites with different author names. If yes, it's AI slop. Discard.
