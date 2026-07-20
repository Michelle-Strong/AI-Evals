# Evaluation Strategy Canvas

# AI Evaluation Strategy Canvas

> Repo file `ai-evals/01-evaluation-strategy/strategy-canvas.md` (the repo is your submission).
> Becomes the Strategy Canvas slide of the final pitch deck you assemble in Module 6.

## 1. Product Strategy, The Context

**Target user:** VP-level Strategists and Product Leaders at the top 50 Enterprise who pay a premium for verified market intelligence — they are high-paying, low-patience, high-scrutiny customers.

**Key use case:** Rapidly extracting specific, verified insights (e.g., comparing competitor pricing models or summarizing G2 reviews) without manual data digging, using trust-worthy plain-language so they can move on their roadmap decisions at pace.


**Value proposition:** Personalized, instant answers based on verified data, dramatically reducing the time spent finding and synthesizing information for high-stakes decisions and strategic roadmaps.

## 2. Measurements, The Execution

**User promise.** For VP-level Enterprise Strategists, Ascend IQ promises to deliver verified, citation-backed competitive intelligence in under 5 seconds so that they hit their Q4 roadmap milestones without manual data digging.

**Top 3 trust metrics:**
- **Latency**, Response speed (P95 / P99). Slow kills engagement.
- **Hallucination Rate**, % of outputs that are confidently false or fabricated.
- **Fairness**, Quality consistency across user groups, geos, languages.

**Why these three:** • Hallucination, VP-level clients pay $50k+ for verified data; one fabricated stat ends the contract.
• Latency, <5s response is the only thing that beats manual digging.
• Fairness, consistent factual quality across English, German & French underpins our European Enterprise expansion.

## 3. Strategic Trade-Offs, The Cost

### Trade-off 1 · Hallucination Rate ↔ Latency
We prioritize Hallucination Rate over Latency because Ascend IQ serves VPs making $1M+ strategic decisions; a single fabricated competitor stat ends a $50k contract, whereas a 5-second wait during a roadmap review meeting breaks the 'faster than my analyst' mental model that justifies the premium price, the risk is reverting to manual digging for that session.

### Trade-off 2 · Fairness ↔ Hallucination Rate
We prioritize Fairness over peak Hallucination Rate because our European Enterprise expansion depends on consistent factual quality across English, German, and French, a bounded, monitored increase (no more than 5% relative) in non-English hallucination rate is acceptable while we close the gap, because English-market contracts are not put at risk by this trade-off.

---



## 2. Why evals: the cost of being wrong

_What happens when this feature fails silently? (e.g. wrong answer ships, trust erodes, compliance risk.)_

## 3. Quality dimensions

_Which dimensions actually matter here, and how do you weight them?_

| Dimension | Why it matters | How you'd measure it |
|---|---|---|
| _Correctness / faithfulness_ | _…_ | _…_ |
| _Safety / policy_ | _…_ | _…_ |
| _Tone / format_ | _…_ | _…_ |

## 4. Evaluator strategy

_For each dimension: human review, code/heuristic check, or LLM-as-judge? Why?_

| Dimension | Evaluator type | Rationale |
|---|---|---|
| _…_ | _human / code / LLM-judge_ | _…_ |

## 5. "Good enough to ship": the bar

_What threshold per dimension makes this shippable? What's the non-negotiable floor?_

## 6. Risks & unknowns

_What might this canvas be wrong about? What will you learn in Module 2's failure discovery?_

## Link to full artifact

_[link / screenshot]_
