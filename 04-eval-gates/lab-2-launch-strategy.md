# Launch Strategy

> Module 4 · Eval Gates · repo file; the rollout plan behind your Eval Gates slide
>
> How the gate policy in `lab-1-gate-map.md` translates into a safe release: staged rollout, monitoring, and the conditions under which you'd roll back.

# Module 4 · Launch Strategy · Section 4.0 Release Criteria

_Generated from the M4 Launch Strategy Builder. Drop this into your PRD as Section 4.0._

## 4.0 Release Criteria

The following thresholds must be met by Model Candidate v1.x before approval for production deploy. Eval Specs from Module 3 define the measurement methodology.

| Severity | Metric | Threshold | Dataset | Method |
|---|---|---|---|---|
| 🔴 Hard (Blocker) | Hallucination - stale pricing | =0% | `Ascend_IQ_Logs` | https://github.com/Michelle-Strong/AI-Evals/blob/main/03-eval-suites/lab-2-eval-spec.md |
| 🟡 Soft (Review) | Latency (P95) | < 2.0s | `Ascend_IQ_Logs` | _[Example Spec]_ |
| 🔵 Advisory (Monitor) | Tone Consistency | >4.0/5 | `Ascend_IQ_Logs` | _[Example Spec]_ |

## 4.1 CI Gate Policy

These thresholds run in a GitHub Actions gate on every pull request, replaying deterministic fixtures from the regression golden set (≥ 30 cases). PM owns the policy; Engineering owns the YAML.

> Block the merge if the Hallucination (stale pricing) metric shows any occurrence >0% in the golden set (absolute check, not baseline-relative) or if any golden-set case regresses to a defined P0/P1 severity (per the Section 4.3 Severity Definitions table); warn — but do not block — on a Tone Consistency drop of ≥1.0 point vs. baseline or a P95 Latency result exceeding the 2.0s Soft Gate budget.

## 4.2 Mitigation Plan · Soft Gate

**Selected Lever:** Beta Labeling

> If our Soft Gate fails (Latency exceeds 5.0s for complex reasoning queries.), we recommend **Beta Labeling** because It limits the impact to Beta Users while we collect production drift data, before we commit to a hard latency budget for all users.

---

_Lab artifact for Module 4, AI Evals Certification, Product School. Becomes the Eval Gates slide of the Final Project deck._

## Rollout stages

| Stage | Audience / % traffic | Gate that must pass to advance | Monitoring signal |
|---|---|---|---|
| _e.g. internal_ | _…_ | _…_ | _…_ |
| _e.g. canary_ | _…_ | _…_ | _…_ |
| _e.g. GA_ | _…_ | _…_ | _…_ |

## Rollback triggers

_What live signal (per-dimension regression, incident, threshold breach) forces a hold or rollback, and who makes the call?_

## Risk tolerance

_Which dimensions block a launch outright vs. warn-and-proceed, and why that's acceptable for this feature._
