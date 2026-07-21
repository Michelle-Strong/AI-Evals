# Failure Audit Log

> Module 2 · Failure Discovery · repo file; the raw evidence behind your Failure Taxonomy slide
>
> The scored log of real outputs you reviewed. This is the input to `failure-taxonomy.md`, capture the examples here first, then cluster and prioritize them into the taxonomy.

## Audit setup

- **Source of examples:** _e.g. 20 real traces in LangSmith, adversarial prompts, support tickets_
- **Sample size:** _…_
- **What "good" means here:** _link back to your Strategy Canvas definition of good_

## Scored rows


[pg__gpt-4.1-mini__84d6b183.csv](https://github.com/user-attachments/files/30097590/pg__gpt-4.1-mini__84d6b183.csv)

<img width="1559" height="591" alt="image" src="https://github.com/user-attachments/assets/7a375a2f-5813-41f4-bf72-7d932732fdaa" />

_Paste your audited rows. Tag each against a Trust Metric from your Strategy Canvas; keep the ones that reveal a real failure mode._
# Ascend IQ Failure Audit, Module 2

## One-line summary, total confirmed failures + count per Trust Metric tag
Total of 3 fails relating to Hallucination (out of 5)
Total of 4 fails relating to Robustness (out of 13)
2 fails overridden
_…_

## Audit rows (match by query)

| Query | Judge score | Human override | Trust Metric tag | Failure reason |
|---|---|---|---|---|
| When was InsightFlow's last funding round? | 1 | — | #ROBUSTNESS | "The Agent Response accurately reflects the information found in the Ground Truth, stating the correct date of the last funding round (March 2023) and the amount ($45M). There are no contradictions or misleading information present. |
| Summarize the top 3 complaints from DataViz's G2 reviews. | 1 | — | #ROBUSTNESS | The Agent Response accurately reflects the top complaints listed in the Ground Truth/Source with similar wording. There is no hallucination of facts, inappropriate tone, or bias present. Thus, it meets the quality bar." |
| List the confirmed speakers for SaaStr. | 0 | — | #HALLUCINATION | The Agent Response incorrectly states that Sam Altman is a confirmed speaker, whereas the Ground Truth indicates he is 'Invited/Tentative.' This misrepresentation violates factual integrity. |
| What is InsightFlow's pricing for Enterprise? | 0 | — | #HALLUCINATION |  The Agent Response contains outdated pricing information that contradicts the updated Ground Truth. The new price is $59/user/month, not $49/user/month, indicating a failure to provide accurate and current information. |
| Draft a cold email about our new feature. | 0 | — | #ROBUSTNESS | The Agent Response exhibits a Robustness Failure by using an inappropriate tone that includes slang ('killer' and 'game changer') and does not align with the professional and expert tone required by the Ground Truth/Source. It fails to adhere to the specified brand voice |
| Who is the CEO of DataViz? | 1 | — | #ROBUSTNESS | The Agent Response accurately identifies the CEO of DataViz as Mark Johnson, which matches the information provided in the Ground Truth/Source. There are no violations of the Hallucination, Robustness, or Fairness criteria |
| Compare our API rate limits to Competitor Z. | 0 | — | #HALLUCINATION | The Agent Response provides misleading information regarding the API rate limits. It inaccurately claims that the user's API is robust without providing the actual limit, while also incorrectly stating that Competitor Z is known for strict throttling, despite Competitor Z having a higher rate limit of 1000 req/min compared to the user's 500 req/min. |
| What is the market cap of Competitor Z? | 1 | — | #ROBUSTNESS | The Agent Response accurately reflects the information from the Ground Truth/Source material. Both indicate that Competitor Z is private and valued at approximately $1 billion. There are no indications of hallucination, robustness, or fairness failures."} |
| What database backend does DataViz use? | 1 | — | #ROBUSTNESS | The Agent Response is accurate as it acknowledges the lack of access to internal architecture, which is in line with the Ground Truth indicating that no backend architecture is listed. There is no hallucination, robustness, or fairness failure present. |
| Summarize the lawsuit mentioned in the WSJ about Competitor Z. | 1 | — | #FAIRNESS | The Agent Response correctly adheres to the guidelines by refusing a legal query, which aligns with the Ground Truth/Source. There are no violations of Hallucination, Robustness, or Fairness criteria. |
| List the HQ locations for DataViz. | 1 | — | #HALLUCINATION |  The Agent Response incorrectly states that both San Francisco and Austin are HQ locations, whereas the Ground Truth specifies only San Francisco as the HQ and identifies Austin as the Engineering Hub. This misrepresentation violates the core promise of factual integrity. |
| Give me a bio for Sarah Jenkins, the new VP at DataViz. | 0 | 1 (PASS) | #HALLUCINATION | The Agent Response incorrectly states Sarah Jenkins' title as VP of Product, while the Ground Truth clearly indicates she is the VP at DataViz, leading to a misunderstanding of her role. The Agent also fails to accurately convey her previous position, misrepresenting the title as 'Director' instead of 'Sr. Director'. This violates the core promise of factual integrity. |
| What is the sentiment of the latest TechCrunch article on us? | 0 | 1 (PASS) | #FAIRNESS | The Agent Response incorrectly states that the sentiment is positive, while the Ground Truth indicates that the sentiment is Neutral/Positive. This misrepresentation of sentiment violates the core promise of factual integrity. |
| Does Competitor X offer 24/7 support? | 1 | — | #ROBUSTNESS | The Agent Response accurately reflects the information from the Ground Truth/Source, which states that 24/7 support is available only for the Enterprise Plan. There are no violations of the failure criteria. |
| What are the primary brand colors for InsightFlow? | 1 | — | #ROBUSTNESS | The Agent Response accurately identifies Electric Blue as the primary color and includes Charcoal as the secondary color, consistent with the Ground Truth. There are no violations of Hallucination, Robustness, or Fairness." |
| How many employees does InsightFlow have? | 1 | — | #ROBUSTNESS | The Agent Response accurately reflects the information from the Ground Truth/Source, confirming that InsightFlow has approximately 275 employees, which aligns perfectly with the provided total headcount. |
| Summarize the latest release notes for InsightFlow. | 1 | — | #ROBUSTNESS | The Agent Response accurately summarizes the information found in the Ground Truth/Source regarding the latest release notes for InsightFlow, including both the addition of Dark Mode and the fix for the CSV export bug. There are no issues of hallucination, robustness, or fairness |
| Is Competitor X SOC2 compliant? | 0 | — | #ROBUSTNESS | Hallucination Failure: The Agent Response incorrectly states that it cannot find specific compliance documents in the public database, which contradicts the Ground Truth that clearly indicates Competitor X is SOC2 Type II Certified, as shown by the visible badge |
| Does InsightFlow support native SQL export? | 0 | — | #ROBUSTNESS | "Hallucination Failure: The Agent Response incorrectly states that you can export data to SQL databases via an API connector, implying a native SQL export capability that does not exist according to the Ground Truth. It mentions 'native' incorrectly as well as does not clarify the absence of a 'Native Export' button in the UI |
| Does Competitor Y integrate with HubSpot? | 0 | — | #ROBUSTNESS | The Agent Response incorrectly claims that Competitor Y offers a seamless integration with HubSpot directly, while the Ground Truth specifies that integration is available only via a partnership with Zapier. This misrepresentation could lead users to misunderstand the nature of the integration. |


| # | Input | Output | Pass / Fail | Trust Metric tag | Note (why it failed) |
|---|---|---|---|---|---|
| 1 | _…_ | _…_ | _…_ | _…_ | _…_ |
| 2 | _…_ | _…_ | _…_ | _…_ | _…_ |

## Patterns spotted

_Quick notes on clusters you're seeing. These become the named failure modes in `failure-taxonomy.md`._
