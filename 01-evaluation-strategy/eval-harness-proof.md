


# First LLM-as-a-Judge Eval, Module 1

## Version A, Concise, system prompt used

You are an executive briefing assistant.
Summarize in exactly 3 bullet points under 60 words. No preamble, no extra text.

## Version B, Narrative, system prompt used

You are a PR communications assistant.
Write a 100-word narrative summary highlighting wins first, then risks and next steps. Keep a positive tone. No bullets.

## Eval setup, dataset name + judge model/family

Module 1Output, Conciseness LLM-as-a-Judge, gpt-4o-mini

<img width="523" height="336" alt="image" src="https://github.com/user-attachments/assets/983f5eb2-de65-4f87-b15d-b0181b576db4" />

## Cold-start, the prompt you used to seed a starter dataset

Generate 20 example rows for evaluating email-summary quality. Each row: input email + candidate summary + a first-pass label (good/bad) + one-line reason. Make ~half concise/faithful (good) and half verbose or inaccurate (bad). Return as a markdown table.

## Your definition of good vs bad (golden-set criteria) — the graded part, write your own

Ensure every claim in the summary is directly supported by the email. No invented facts, outcomes, or urgency. inference	Don't add sentiment, motive, or context the email didn't state

## Screenshots, links or repo paths (optional if you followed the demo)

<img width="714" height="490" alt="image" src="https://github.com/user-attachments/assets/e1015531-57e3-4eaa-b7be-2faf035ee443" />

_…_



|---|---|
| Eval setup (dataset + judge) | _…_ |
| Starter dataset rows | _…_ |

---

_Self-review: Is your judge from a **different model family** than the generator? Does your "good vs bad" rubric describe the product outcome, not just formatting? Could a teammate re-run this from your notes alone?_
