---
description: Straight Line, Branch, and Hybrid sequence patterns, send frequency tables, best send times, architecture selection criteria
connections:
  - "[[welcome-sequence-framework]]"
  - "[[conversion-launch-sequences]]"
  - "[[automation-segmentation]]"
  - "[[nurture-reengagement]]"
---

# Sequence Architecture

## Three Patterns

Every email sequence follows one of three architecture patterns. Pick the one that matches your stage and complexity tolerance.

### 1. Straight Line

Email 1 → Email 2 → Email 3 → ... → Pitch.

Everyone gets the same emails in the same order. No branches. No conditions. No "if they clicked, send this instead."

**Best for:** People just starting out. First welcome sequence. First conversion sequence. When you have fewer than 2,000 subscribers and no automation experience.

**Pros:** Simple to build, simple to debug, simple to maintain. You can build this in 20 minutes in Kit's visual [[automation-segmentation|automation]] builder.

**Cons:** No personalization. Someone who's clearly interested gets the same emails as someone who's barely engaged. But honestly? That's fine when you're starting. Optimization comes later.

### 2. Branch

Behavioral triggers create different paths. The sequence adapts based on what the subscriber does.

```
Email 1 → Email 2 → [Did they click?]
  YES → Pitch sequence (they're interested)
  NO  → More value emails → Try again
```

**Best for:** Once you have a working Straight Line sequence and want to improve conversions. Typically after 2,000+ subscribers when you have enough data to know what behaviors matter.

**Pros:** Higher conversion rates. Interested people get the offer faster. Disengaged people get more nurturing instead of premature pitches.

**Cons:** More complex to build and maintain. More things that can break. Requires understanding Kit's [[automation-segmentation|tagging and trigger system]].

**Common branch triggers:**
- Clicked a specific link → send offer email
- Opened 3+ emails in sequence → send pitch earlier
- Didn't open last 2 emails → send re-engagement
- Purchased → remove from sales sequence, add to [[nurture-reengagement|post-purchase]]

### 3. Hybrid

The full lifecycle. Welcome → Conversion → Nurture → Re-engagement all connected in one architecture.

```
Opt-in → Welcome Sequence (7 emails)
  → Conversion Sequence (4-7 emails)
    → Purchased? YES → Post-purchase onboarding
    → Purchased? NO → Nurture sequence (ongoing)
      → Gone cold? → Re-engagement (3-4 emails)
        → Still cold? → Remove from list
```

**Best for:** Established businesses with 5,000+ subscribers, multiple offers, and someone who can monitor automations. This is the "built once, runs forever" system.

**Pros:** Complete lifecycle coverage. No subscriber falls through the cracks. Every stage has an appropriate sequence.

**Cons:** Complex to build initially. Requires all four sequence types ([[welcome-sequence-framework|welcome]], [[conversion-launch-sequences|conversion]], [[nurture-reengagement|nurture]], re-engagement) to be written and tested before connecting them.

## Architecture Selection

| Stage | List Size | Recommended | Why |
|-------|-----------|-------------|-----|
| Starting | 0-2K | Straight Line | Get something running. Don't optimize what doesn't exist yet. |
| Growing | 2K-5K | Branch | You have data now. Start personalizing the path to purchase. |
| Established | 5K+ | Hybrid | Full lifecycle. Every subscriber has a path. |

Don't skip stages. A working Straight Line sequence beats a half-built Hybrid every time.

## Send Frequency Table

| Sequence Type | Frequency | Why |
|---------------|-----------|-----|
| Welcome | Every 2 days | Builds rhythm without overwhelming |
| Conversion | Every 2 days (daily for launches) | Enough breathing room to process |
| Launch | Daily (2x on open/close days) | Urgency demands frequency |
| Nurture | 2-3x/week | Maintains presence, matches [[email-cadence|broadcast cadence]] |
| Re-engagement | Every 3 days | Less frequent, pattern interrupt |
| Post-purchase | Every 3-4 days | Supportive, not salesy |

## Best Send Times

Send at the SAME time every day. Consistency matters for [[esp-deliverability|deliverability]] and for subscriber habits.

**Sweet spots:**
- 10am-12pm local time (desk workers checking email)
- 2-4pm local time (afternoon inbox check)

Pick one and stick with it. If your audience is multi-timezone, optimize for where your [[pfc-avatar-layers|PFC]] lives. For example, 10am Dubai time catches UK/Europe at lunch and North America in the morning.

## Transition Points

The most important design decision in any architecture is what happens BETWEEN sequences:

- **Welcome → Conversion:** 2-3 day gap. Let the welcome sequence breathe before pitching.
- **Conversion → Nurture:** Immediate. If they didn't buy, start nurturing the same week.
- **Nurture → Re-engagement:** Triggered by behavior (90 days no opens), not by time alone.
- **Re-engagement → Remove:** If 3-4 re-engagement emails get no response, remove them. A clean list beats a big list.
