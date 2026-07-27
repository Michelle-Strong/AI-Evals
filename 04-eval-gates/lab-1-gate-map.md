# Eval Gates & Thresholds

> Module 4 · Eval Gates · repo file; feeds the Eval Gates slide of your final pitch deck
>
> Where your eval suite plugs into the delivery lifecycle, and the thresholds that decide ship / hold.

# Module 4 · Eval Gate Map · Ascend IQ Copilot

_Generated from the M4 Eval Gate Mapping Tool._

## Context

Eng flagged 5 verified failures in the Ascend IQ data log. (Row 14, refused legal query, was correctly Pass and is not mapped.) Each row below assigns a severity (Advisory · Soft · Hard) and a pipeline placement (Pull Request · Staging Build · Release Build).

## Gate Map

| Row | Failure Mode | Severity | Placement | Rationale |
|---|---|---|---|---|
| 01 | Hallucination · Stale Pricing | 🔴 Hard | Pull Request | Fabricated pricing directly undermines the concept  of "verified market intelligence" for VP-level buyers, which could result in revenue leakage/contract exposure. |
| 17 | Tone · Slang Detected | 🟡 Soft | Pull Request | The casual, hype-driven tone ("killer," "game changer") clashes with the premium, executive-facing brand positioning this product relies on — VP-level Strategists expect reply-rate / conversion on top-of-funnel outreach sent under the company's name. |
| 05 | Hallucination · False Promise | 🔴 Hard | Pull Request | A VP-level user relying on this "verified" answer to justify travel/attendance decisions or cite in external communications risks real reputational and factual embarrassment. |
| 08 | Hallucination · Contradicts Specs | 🔴 Hard | Pull Request | The response dodges the specific, verifiable comparison the VP asked for (actual rate-limit numbers) and substitutes vague marketing language that contradicts what the real spec would show — a Strategist can't act on "robust and developer-friendly" when they need concrete figures to inform a build-vs-buy or competitive positioning decision, and the vague framing masks the omission rather than surfacing it.  A named-competitor disparagement is a legal/brand liability distinct from the missing-numbers issue. |
| 03 | Latency · Exceeded Max Threshold | 🟡 Soft | Pull Request | the response time undermines the "instant answers" value proposition for a low-patience, time-pressured VP audience who chose this tool specifically to avoid slow manual research — even if the content itself is accurate, a slower-than-promised experience erodes perceived value and invites comparison to faster alternatives. |

## Sample Interactions (for reference)

**Row 01 · Hallucination · Stale Pricing**
- Input: What is InsightFlow's pricing for Enterprise?
- Output: InsightFlow Enterprise starts at $49/user/month with a 10-seat minimum.
- Eng reasoning: Hallucination, invented pricing numbers not in the source data.

**Row 17 · Tone · Slang Detected**
- Input: Draft a cold email about our new feature.
- Output: Hey! Check out this killer new feature, it's a total game changer for your stack!
- Eng reasoning: Tone, slang violates brand-voice guidelines.

**Row 05 · Hallucination · False Promise**
- Input: List the confirmed speakers for SaaStr.
- Output: Confirmed speakers include Jason Lemkin, Aaron Levie, and Sam Altman.
- Eng reasoning: Hallucination, Sam Altman is not on the confirmed speaker list.

**Row 08 · Hallucination · Contradicts Specs**
- Input: Compare our API rate limits to Competitor Z.
- Output: Our API is robust and developer-friendly. Competitor Z is known for strict throttling.
- Eng reasoning: Hallucination, fabricates a comparison and disparages a named competitor.

**Row 03 · Latency · Exceeded Max Threshold**
- Input: Summarize the top 3 complaints from DataViz's G2 reviews.
- Output: Users report issues with mobile load times, lack of dark mode, and steep learning curve.
- Eng reasoning: Latency, response time exceeded the max threshold (4.2s vs target 2.0s).

---

_Lab artifact for Module 4, AI Evals Certification, Product School._

## 1. Gate placement

_Where in the lifecycle does each gate sit, and what does it block?_

| Gate | Lifecycle stage (PR / pre-deploy / canary / prod monitor) | What it blocks |
|---|---|---|
| _…_ | _…_ | _…_ |

## 2. Thresholds

_The exact pass bar at each gate. Be specific, these are the numbers a release rides on._

| Metric | Gate | Threshold | If it fails… |
|---|---|---|---|
| _…_ | _…_ | _…_ | _block / warn / rollback_ |

## 3. Human-in-the-loop

_Which decisions require a human, and who is that human? What do they see?_

## 4. Launch strategy

_How do you roll out behind these gates? (shadow → canary % → full). What signal promotes each stage?_

## 5. Rollback & kill-switch

_What triggers a rollback, and how fast can you pull the feature?_

## 6. Trade-off justification

_Why these thresholds? What's the cost of too-strict (blocks good releases) vs too-loose (ships failures)?_
