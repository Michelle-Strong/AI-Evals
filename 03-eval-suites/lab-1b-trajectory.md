# Trajectory Eval — Scorecard

> Module 3 · Eval Suites · repo file; the path-quality evidence behind your Eval Results slide
>
> For agentic features, a correct-looking answer can still come from a broken path. Score the path the agent took, not just the final answer. (Judge agreement / κ lives in `lab-judge-calibration.md`.)

## Trajectory scorecard
# M3 · Lab 2 · Eval Spec, Ascend IQ P0

## Part 1 · The 5-Part Eval Spec

| Question | Answer |
|---|---|
| **01 · Target Risk** | Hallucinated pricing (out of date) |
| **Risk Type** | Trajectory |
| **Trust Metric** | Hallucination |
| **02 · Evaluator** | Hybrid |
| **Detection logic** | Hybrid - Code based check - compare any $ amount in the response against live pricing API + LLM judge on what passes. |
| **03 · Threshold** | 100% accuracy |
| **Strategy** | Safety First (max TPR) |
| **04 · Business Stakes** | Quoting incorrect pricing in a B2B sales context causes trust issues, opens up revenue-recognition liability and could potentially trigger penalties for breach of contract |
| **05 · Owner** | Group PM, and sponsor |

## Trajectory fields

| Field | Answer |
|---|---|
| **Dimensions scored** | 1 · Tool selection; 6 · Task completion |
| **Matching mode** | Strict |


## Part 2 · Three Audience Messages

### A. For Engineering (Jira ticket)
Description: Hybrid eval (live pricing API cross-check + LLM judge) detected instances where Ascend IQ returned dollar figures that did not match current live pricing data. This is a launch-blocking defect for the Top 50 Enterprise release under the Trust & Safety eval gate (Dims 1, 6 — Trajectory, Strict Match, 100% threshold).

Acceptance Criteria:

 Root cause identified and documented: is this a retrieval-freshness issue (stale index/cache), a grounding issue (model not citing/using the live source), or a generation issue (model fabricating a figure not present in any retrieved source)?
 Every response containing a $ amount is programmatically checked against the live pricing API before being returned to the user (hard gate, not a best-effort call).
 If a live price cannot be verified in real time, the agent must decline to state a number and instead direct the user to the verified source page — never emit an unverified figure.
 Data freshness SLA defined and enforced (e.g., pricing index refresh interval) with a visible "as of [date/time]" stamp on any pricing claim shown to the user.
 Regression suite: full hybrid eval (code-based $ comparison + LLM judge) re-run against the complete trajectory test set, 100% pass required, zero exceptions.
 Load/edge-case testing: multi-entity comparisons (e.g., "Stripe vs. Adyen vs. Braintree"), tiered/negotiated pricing mentions, and currency variants specifically included in the test set, since these are the most likely fabrication triggers.
 Logging: every pricing claim logged with source, timestamp, and confidence, so any future incident is traceable and auditable — this is required for the revenue-recognition/liability exposure noted by the eval owner.
 Sign-off required from: Group PM, Eval Owner, and Engineering Lead before this ticket can close.

### B. For UX / Design
Goal: Design for verified confidence, not just speed.

The product's core promise — "instant answers without manual digging" — is only a valid promise if the user can trust the answer without re-verifying it manually, which defeats the point. The UX goal is to make trustworthiness visible, not just assumed:

Every numeric/pricing claim in an Ascend IQ response carries an inline source citation and an "as of" freshness timestamp — no bare numbers.
Design a distinct, low-friction UI state for "I can't verify this in real time" that routes the user to the primary source, so a graceful decline feels like a feature (transparency) rather than a failure.
Add a lightweight in-product feedback affordance (thumbs down / "flag this figure") on every data-bearing response, specifically to catch pricing drift or edge cases the eval suite didn't anticipate, before Enterprise rollout and after.
Usability test the "decline gracefully" flow with a handful of current power users before GA: does it still feel faster than manual digging even when it can't give a number outright?
Success metric for Design: time-to-trust (does the user act on the answer without double-checking it elsewhere), not just time-to-answer.

### C. For Leadership (bi-weekly update)
Status: HOLD — remediation in progress, reopening gated on eval pass, not calendar date.
This period:

Root cause investigation underway on pricing hallucination (retrieval freshness vs. grounding vs. fabrication)
Hard verification gate being built: no $ figure ships without a live-source match
Full hybrid eval re-run scheduled once fix lands; 100% pass is the sole reopening condition — no partial/soft launch to any Enterprise account in the interim
Sales/CS aligned on messaging to accounts with near-term renewals to avoid overpromising while this is in flight

Next update will include: eval pass/fail result on the full trajectory set, and — if passed — a revised go-live date for the Top 50 cohort.



---

_Save this to `03-eval-suites/lab-2-eval-spec.md` in your repo (the repo is your submission). It underpins the Eval Results slide of your final pitch deck._


