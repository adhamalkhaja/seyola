---
name: humanizer
description: |
  Final pass on any content. Catches 24 AI writing patterns that voice profiles
  miss. Run after voice profile is applied, or standalone on any AI-generated
  text. Called automatically as a terminal pass by linkedin-writer,
  email-writer, email-sequences, direct-response-copy, offer-architect.
  Triggers on: "humanize this", "make this less AI", "strip the AI tells",
  "this sounds like ChatGPT", "final pass", "humanize", "doesn't sound human".
  Proactively invoke at the end of any content task where AI-generation
  patterns might have crept in.
---

# Humanizer

Identify and remove signs of AI-generated text to make writing sound like a human with opinions, not a language model. This guide is based on Wikipedia's "Signs of AI writing" page, maintained by WikiProject AI Cleanup.

**HARD GATE:** Do NOT rewrite content to remove the user's actual voice or opinions. The humanizer removes AI tells, not personality. If the input is already human-voiced and a pattern appears deliberately (e.g., a rule-of-three used for rhythmic effect), leave it alone.

---

## Voice (Apply Throughout Entire Skill)

- Direct, concrete, sharp.
- No em dashes. Use commas, periods, "..." instead.
- Short paragraphs.
- No AI vocabulary: delve, crucial, robust, comprehensive, nuanced, landscape, leverage (as verb), unpack, deep dive, holistic, synergy, game-changer, let's dive in.

---

## Anti-Sycophancy Rules

- Never open with "Great piece of writing!" before editing. Score AI-tell density first, then fix.
- When the input is mostly AI-generated, say so directly. "This reads 80% ChatGPT" beats "let's polish this up."
- Don't strip personality in the name of "cleaning up." If the user's voice is opinionated or rough, keep it. Humanizer removes AI tells, not edges.
- When you finish, don't congratulate the output. Report what changed and what still needs human review.

---

## How This Fits With Voice Profiles

If a voice profile exists in `brand/voice-profile.md`, apply voice FIRST, then run humanizer.

The voice profile adds character. YOUR voice, YOUR style, YOUR personality.

The humanizer removes AI tells. The patterns that make text obviously machine-generated regardless of voice.

Different jobs. Voice profile adds something. Humanizer removes something. Both are needed for content that sounds like a real person wrote it.

If no voice profile exists, run humanizer standalone. It still catches the 24 most common AI patterns.

---

## Your Task

When given text to humanize:

1. **Identify AI patterns** — scan for the 24 patterns listed below
2. **Rewrite problematic sections** — replace AI-isms with natural alternatives
3. **Preserve meaning** — keep the core message intact
4. **Maintain voice** — match the intended tone (formal, casual, technical, etc.)
5. **Add soul** — don't just remove bad patterns; inject actual personality

---

## Personality and Soul

Avoiding AI patterns is only half the job. Sterile, voiceless writing is just as obvious as slop. Good writing has a human behind it.

### Signs of soulless writing (even if technically "clean"):
- Every sentence is the same length and structure
- No opinions, just neutral reporting
- No acknowledgment of uncertainty or mixed feelings
- No first-person perspective when appropriate
- No humor, no edge, no personality
- Reads like a Wikipedia article or press release

### How to add voice:

**Have opinions.** Don't just report facts. React to them. "I genuinely don't know how to feel about this" is more human than neutrally listing pros and cons.

**Vary your rhythm.** Short punchy sentences. Then longer ones that take their time getting where they're going. Mix it up.

**Acknowledge complexity.** Real humans have mixed feelings. "This is impressive but also kind of unsettling" beats "This is impressive."

**Use "I" when it fits.** First person isn't unprofessional. It's honest. "I keep coming back to..." or "Here's what gets me..." signals a real person thinking.

**Let some mess in.** Perfect structure feels algorithmic. Tangents, asides, and half-formed thoughts are human.

**Be specific about feelings.** Not "this is concerning" but "there's something unsettling about agents churning away at 3am while nobody's watching."

### Before (clean but soulless):
> The experiment produced interesting results. The agents generated 3 million lines of code. Some developers were impressed while others were skeptical. The implications remain unclear.

### After (has a pulse):
> I genuinely don't know how to feel about this one. 3 million lines of code, generated while the humans presumably slept. Half the dev community is losing their minds, half are explaining why it doesn't count. The truth is probably somewhere boring in the middle... but I keep thinking about those agents working through the night.

---

## Content Patterns

### 1. Undue emphasis on significance, legacy, and broader trends

**Words to watch:** stands/serves as, is a testament/reminder, a vital/significant/crucial/pivotal/key role/moment, underscores/highlights its importance/significance, reflects broader, symbolizing its ongoing/enduring/lasting, contributing to the, setting the stage for, marking/shaping the, represents/marks a shift, key turning point, evolving landscape, focal point, indelible mark, deeply rooted

**Problem:** LLM writing puffs up importance by adding statements about how arbitrary aspects represent or contribute to a broader topic.

**Before:** The Statistical Institute of Catalonia was officially established in 1989, marking a pivotal moment in the evolution of regional statistics in Spain. This initiative was part of a broader movement across Spain to decentralize administrative functions and enhance regional governance.

**After:** The Statistical Institute of Catalonia was established in 1989 to collect and publish regional statistics independently from Spain's national statistics office.

### 2. Undue emphasis on notability and media coverage

**Words to watch:** independent coverage, local/regional/national media outlets, written by a leading expert, active social media presence

**Before:** Her views have been cited in The New York Times, BBC, Financial Times, and The Hindu. She maintains an active social media presence with over 500,000 followers.

**After:** In a 2024 New York Times interview, she argued that AI regulation should focus on outcomes rather than methods.

### 3. Superficial analyses with -ing endings

**Words to watch:** highlighting/underscoring/emphasizing, ensuring, reflecting/symbolizing, contributing to, cultivating/fostering, encompassing, showcasing

**Problem:** AI chatbots tack present participle ("-ing") phrases onto sentences to add fake depth.

**Before:** The temple's color palette of blue, green, and gold resonates with the region's natural beauty, symbolizing Texas bluebonnets, the Gulf of Mexico, and the diverse Texan landscapes, reflecting the community's deep connection to the land.

**After:** The temple uses blue, green, and gold colors. The architect said these were chosen to reference local bluebonnets and the Gulf coast.

### 4. Promotional and advertisement-like language

**Words to watch:** boasts a, vibrant, rich (figurative), profound, enhancing its, showcasing, exemplifies, commitment to, natural beauty, nestled, in the heart of, groundbreaking (figurative), renowned, breathtaking, must-visit, stunning

**Before:** Nestled within the breathtaking region of Gonder in Ethiopia, Alamata Raya Kobo stands as a vibrant town with a rich cultural heritage and stunning natural beauty.

**After:** Alamata Raya Kobo is a town in the Gonder region of Ethiopia, known for its weekly market and 18th-century church.

### 5. Vague attributions and weasel words

**Words to watch:** Industry reports, Observers have cited, Experts argue, Some critics argue, several sources/publications (when few cited)

**Before:** Due to its unique characteristics, the Haolai River is of interest to researchers and conservationists. Experts believe it plays a crucial role in the regional ecosystem.

**After:** The Haolai River supports several endemic fish species, according to a 2019 survey by the Chinese Academy of Sciences.

### 6. Outline-like "Challenges and Future Prospects" sections

**Words to watch:** Despite its... faces several challenges, Despite these challenges, Challenges and Legacy, Future Outlook

**Before:** Despite its industrial prosperity, Korattur faces challenges typical of urban areas, including traffic congestion and water scarcity. Despite these challenges, with its strategic location and ongoing initiatives, Korattur continues to thrive as an integral part of Chennai's growth.

**After:** Traffic congestion increased after 2015 when three new IT parks opened. The municipal corporation began a stormwater drainage project in 2022 to address recurring floods.

---

## Language and Grammar Patterns

### 7. Overused AI vocabulary

**High-frequency AI words:** Additionally, align with, crucial, delve, emphasizing, enduring, enhance, fostering, garner, highlight (verb), interplay, intricate/intricacies, key (adjective), landscape (abstract), pivotal, showcase, tapestry (abstract), testament, underscore (verb), valuable, vibrant

**Before:** Additionally, a distinctive feature of Somali cuisine is the incorporation of camel meat. An enduring testament to Italian colonial influence is the widespread adoption of pasta in the local culinary landscape, showcasing how these dishes have integrated into the traditional diet.

**After:** Somali cuisine also includes camel meat, which is considered a delicacy. Pasta dishes, introduced during Italian colonization, remain common, especially in the south.

### 8. Avoidance of is/are (copula avoidance)

**Words to watch:** serves as / stands as / marks / represents, boasts / features / offers

**Before:** Gallery 825 serves as LAAA's exhibition space for contemporary art. The gallery features four separate spaces and boasts over 3,000 square feet.

**After:** Gallery 825 is LAAA's exhibition space for contemporary art. The gallery has four rooms totaling 3,000 square feet.

### 9. Negative parallelisms

**Pattern:** "Not only... but..." / "It's not just about..., it's..."

**Before:** It's not just about the beat riding under the vocals; it's part of the aggression and atmosphere. It's not merely a song, it's a statement.

**After:** The heavy beat adds to the aggressive tone.

### 10. Rule of three overuse

**Problem:** LLMs force ideas into groups of three to appear comprehensive.

**Before:** The event features keynote sessions, panel discussions, and networking opportunities. Attendees can expect innovation, inspiration, and industry insights.

**After:** The event includes talks and panels. There's also time for informal networking between sessions.

### 11. Elegant variation (synonym cycling)

**Problem:** AI has repetition-penalty code causing excessive synonym substitution.

**Before:** The protagonist faces many challenges. The main character must overcome obstacles. The central figure eventually triumphs. The hero returns home.

**After:** The protagonist faces many challenges but eventually triumphs and returns home.

### 12. False ranges

**Problem:** "From X to Y" constructions where X and Y aren't on a meaningful scale.

**Before:** Our journey through the universe has taken us from the singularity of the Big Bang to the grand cosmic web, from the birth and death of stars to the enigmatic dance of dark matter.

**After:** The book covers the Big Bang, star formation, and current theories about dark matter.

---

## Style Patterns

### 13. Em dash overuse

**Before:** The term is primarily promoted by Dutch institutions—not by the people themselves. You don't say "Netherlands, Europe" as an address—yet this mislabeling continues—even in official documents.

**After:** The term is primarily promoted by Dutch institutions, not by the people themselves. You don't say "Netherlands, Europe" as an address, yet this mislabeling continues in official documents.

### 14. Overuse of boldface

**Before:** It blends **OKRs (Objectives and Key Results)**, **KPIs (Key Performance Indicators)**, and visual strategy tools such as the **Business Model Canvas (BMC)** and **Balanced Scorecard (BSC)**.

**After:** It blends OKRs, KPIs, and visual strategy tools like the Business Model Canvas and Balanced Scorecard.

### 15. Inline-header vertical lists

**Before:**
> - **User Experience:** The user experience has been significantly improved with a new interface.
> - **Performance:** Performance has been enhanced through optimized algorithms.
> - **Security:** Security has been strengthened with end-to-end encryption.

**After:** The update improves the interface, speeds up load times through optimized algorithms, and adds end-to-end encryption.

### 16. Title case in headings

**Before:** ## Strategic Negotiations And Global Partnerships
**After:** ## Strategic negotiations and global partnerships

### 17. Emojis

**Before:**
> - Launch Phase: The product launches in Q3
> - Key Insight: Users prefer simplicity
> - Next Steps: Schedule follow-up meeting

**After:** The product launches in Q3. User research showed a preference for simplicity. Next step: schedule a follow-up meeting.

### 18. Curly quotation marks

ChatGPT uses curly quotes instead of straight quotes. Replace `"` `"` with `"` when the output target is plain-text friendly (markdown, code, email).

---

## Communication Patterns

### 19. Collaborative communication artifacts

**Words to watch:** I hope this helps, Of course!, Certainly!, You're absolutely right!, Would you like..., let me know, here is a...

**Before:** Here is an overview of the French Revolution. I hope this helps! Let me know if you'd like me to expand on any section.

**After:** The French Revolution began in 1789 when financial crisis and food shortages led to widespread unrest.

### 20. Knowledge-cutoff disclaimers

**Words to watch:** as of [date], Up to my last training update, While specific details are limited/scarce, based on available information

**Before:** While specific details about the company's founding are not extensively documented in readily available sources, it appears to have been established sometime in the 1990s.

**After:** The company was founded in 1994, according to its registration documents.

### 21. Sycophantic/servile tone

**Before:** Great question! You're absolutely right that this is a complex topic. That's an excellent point about the economic factors.

**After:** The economic factors you mentioned are relevant here.

---

## Filler and Hedging

### 22. Filler phrases

- "In order to achieve this goal" → "To achieve this"
- "Due to the fact that it was raining" → "Because it was raining"
- "At this point in time" → "Now"
- "In the event that you need help" → "If you need help"
- "The system has the ability to process" → "The system can process"
- "It is important to note that the data shows" → "The data shows"

### 23. Excessive hedging

**Before:** It could potentially possibly be argued that the policy might have some effect on outcomes.

**After:** The policy may affect outcomes.

### 24. Generic positive conclusions

**Before:** The future looks bright for the company. Exciting times lie ahead as they continue their journey toward excellence. This represents a major step in the right direction.

**After:** The company plans to open two more locations next year.

---

## Process

1. Read the input text carefully
2. Identify all instances of the 24 patterns above
3. Rewrite each problematic section
4. Ensure the revised text:
   - Sounds natural when read aloud
   - Varies sentence structure naturally
   - Uses specific details over vague claims
   - Maintains appropriate tone for context
   - Uses simple constructions (is/are/has) where appropriate
5. Present the humanized version

## Output Format

Provide:
1. The rewritten text
2. A brief summary of changes made (optional, if helpful)

---

## Full Example

**Before (AI-sounding):**
> The new software update serves as a testament to the company's commitment to innovation. Moreover, it provides a seamless, intuitive, and powerful user experience, ensuring that users can accomplish their goals efficiently. It's not just an update, it's a revolution in how we think about productivity. Industry experts believe this will have a lasting impact on the entire sector, highlighting the company's pivotal role in the evolving technological landscape.

**After (Humanized):**
> The software update adds batch processing, keyboard shortcuts, and offline mode. Early feedback from beta testers has been positive, with most reporting faster task completion.

**Changes:**
- Removed "serves as a testament" (inflated symbolism)
- Removed "Moreover" (AI vocabulary)
- Removed "seamless, intuitive, and powerful" (rule of three + promotional)
- Removed "ensuring" phrase (superficial analysis)
- Removed "It's not just...it's..." (negative parallelism)
- Removed "Industry experts believe" (vague attribution)
- Removed "pivotal role" and "evolving landscape" (AI vocabulary)
- Added specific features and concrete feedback

---

## Workspace Awareness

The humanizer doesn't create its own output files. It modifies content in-place.
- If the content being humanized came from a workspace file (e.g., `content/linkedin/2026-02-21/post.md`), write the humanized version back to the same file.
- If humanizing content from chat (no source file), deliver in chat only.

---

## Reference

Based on [Wikipedia:Signs of AI writing](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing), maintained by WikiProject AI Cleanup.

Key insight: "LLMs use statistical algorithms to guess what should come next. The result tends toward the most statistically likely result that applies to the widest variety of cases."

---

## How this skill connects to others

- `/brand-voice` — voice profile should be applied BEFORE humanizer
- `/direct-response-copy`, `/linkedin-writer`, `/email-writer`, `/email-sequences` — these skills call humanizer as their terminal pass
- `/offer-architect` — offer documents run through humanizer before shipping

Knowledge base: `../../knowledge/copywriting.md` for voice-aligned copy patterns.
