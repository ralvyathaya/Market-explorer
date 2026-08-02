# Research Workflow

## Intake

Infer missing fields from the prompt when safe. Ask a concise follow-up only if the answer would materially change the research path.

Capture:

- Market or niche.
- Target audience or buyer.
- Geography and language.
- Research mode: ideation, data collection, pain extraction, pre-build validation, opportunity generation, landing page brief, or full sprint.
- Available evidence: pasted comments, links, prior notes, search results, reviews, transcripts, surveys, or none.
- Output depth: quick scan, normal, or deep.

Default to digital-first markets: SaaS, web and mobile apps, AI tools, and digital products. Include services and manual workarounds as substitutes. For pre-build validation and full sprints, use `Problem -> Demand -> Spend -> Competition -> Distribution -> Verdict`.

## Market Map

Use a hierarchy that fits the user's market:

```markdown
- Core market or domain
  - Category
    - Subcategory
      - Niche
        - Sub-niche
```

Use Health, Wealth, and Relationships only when the user asks for broad/random ideation or when no domain is supplied. Do not force every market into those three buckets if the user gave a specific market.

Keep categories distinct. Prefer clear segmentation dimensions:

- Demographic: age, role, life stage, income, family status.
- Behavioral: frequency, trigger event, current workaround, spending behavior.
- Psychographic: belief, fear, desired identity, motivation.
- Contextual: geography, regulation, device, workplace, channel, seasonality.

## Niche Overlap Detection

Run this after creating a market map or whenever the user asks for niche selection. The goal is to prevent duplicate niches from looking like separate opportunities, while avoiding premature merges that hide useful segment differences.

Compare candidate niches across:

- Audience: who has the problem.
- Pain: what hurts, costs time, creates risk, or triggers action.
- Job-to-be-done: what the customer is trying to accomplish.
- Current workaround: what they use today, including manual hacks.
- Buyer: who can approve, pay, or act.
- Channel: where the audience can be reached.
- Customer language: repeated phrases, metaphors, objections, or desired outcomes.

Use these overlap types:

| Overlap Type | Meaning |
|---|---|
| Audience overlap | Same customer, different pain. |
| Pain overlap | Same pain, different customer. |
| JTBD overlap | Same job-to-be-done, different category or niche label. |
| Solution overlap | Same workaround, competitor, or substitute behavior. |
| Language overlap | Repeated customer phrases across niches. |

Use these actions:

| Action | Use When |
|---|---|
| Merge | Audience, pain, job, buyer, and workaround are materially the same. |
| Split | The label is broad but contains different triggers, urgency, or buying moments. |
| Keep separate | Similar surface language hides different buyer, channel, urgency, or willingness to pay. |
| Research more | Overlap is plausible but evidence is thin or mostly inferred. |

Do not merge niches based only on similar labels. If the evidence is weak, mark confidence as low and write the overlap as a hypothesis.

## Pain-Point Extraction

Scan all source material before grouping. Extract pain points that show a real experienced problem, not generic interest.

Include:

- First-person struggles and frustrations.
- Failed attempts with existing solutions.
- Workarounds, spreadsheets, manual processes, or hacks.
- Emotional consequences, fear, embarrassment, lost time, lost money, relationship strain, health impact.
- Repeated questions that reveal confusion or unmet demand.
- Specific usage scenarios where the pain appears.

Exclude:

- Advice without a described problem.
- Generic rants with no concrete situation.
- Purely positive stories unless they contrast with a prior pain.
- News, politics, memes, or unrelated debate.
- Vague market assumptions not grounded in the source data.

For each pain point, capture:

- Clear pain heading.
- One-sentence summary.
- 2-5 exact quotes when available.
- Frequency estimate: low, medium, high, or a count if data is structured.
- Intensity estimate: low, medium, high, based on emotional language and stakes.
- Solvability estimate: low, medium, high, based on whether a product/service could realistically help.
- Current workaround or existing alternative.
- Existing solutions mentioned and why users dislike them.

For a `Problem` gate pass, require at least three concrete experienced-problem examples across at least two independent source families, such as communities, product reviews, app-store reviews, support forums, or GitHub issues. Search volume and launch votes are not problem evidence.

## Demand Momentum

Use Google Trends when accessible. Check both the last five years and last twelve months for the target geography. Record:

- Whether the input is a broad topic or an exact search term.
- Long-term direction and recent direction.
- Seasonality and whether apparent growth depends on one news-driven spike.
- Regional concentration.
- Rising and breakout related queries that reveal adjacent jobs or language.

Google Trends is sampled, normalized relative interest scaled from 0-100. It does not provide absolute market size, revenue, or purchase intent. Treat low-volume zeroes and isolated spikes cautiously. If Trends is unavailable, request a shared Trends link or CSV export and mark demand momentum unknown.

## Commercial and Competitor Evidence

Compare 3-5 relevant products across three types:

- **Direct competitor**: same audience and job-to-be-done.
- **Substitute**: different product or manual workflow used for the same job.
- **Successful analog**: a proven product with a transferable mechanism, buyer motion, or business model.

Capture audience, job, positioning, current pricing, traction signal and date, repeated complaints, apparent gap, and the mechanism worth testing. Prefer current first-party pricing and product pages over summaries.

Use source-specific interpretations:

| Source | What it can support | What it cannot prove alone |
|---|---|---|
| TrustMRR | Verified revenue, MRR, subscriptions, customer counts, or growth for listed products | Whole-market size, profitability, or representative category demand |
| Product Hunt | Launch attention, positioning, maker activity, votes, and comments | Revenue, retention, or durable demand |
| App stores | Public ratings, review volume/recency, category rank, and displayed install ranges | Profit, retention, or exact active users |
| Pricing/review pages | Paid alternatives, segments, objections, and switching complaints | Verified revenue or market-wide frequency |
| Founder claims | A lead for further research | Verified commercial proof unless independently corroborated |

Commercial evidence must relate to the same segment and job-to-be-done. A popular adjacent product is an analog, not proof that the candidate itself has demand.

## Distribution Evidence

Name at least one active channel where the target buyer can be reached and one repeatable access path, such as a specific community plus recurring problem queries, a review ecosystem, partner directory, professional association, app-store category, or direct-outreach list. “Social media” or “SEO” without a concrete audience and collection method fails the reachability gate.

## Evidence Rules

For each material claim, record the source, access date, what it proves, what it does not prove, and confidence. Use this labeling:

- **Evidence**: direct quotes, observed repeated themes, source links, user-provided facts.
- **Inference**: likely motivations, underserved segment hypotheses, implied willingness to pay.
- **Recommendation**: what to test, build, cut, or position next.

Never invent quotes, metrics, or cite "many users" unless source volume supports it. Open a source before quoting it. If there are only a few comments, say the evidence is thin and frame findings as hypotheses.

## Hard Gates and Verdicts

Evaluate these before ranking:

| Gate | Pass condition |
|---|---|
| Problem | At least three concrete experienced-problem examples across at least two independent source families |
| Action/spend | Same-segment and same-JTBD evidence of payment, costly workaround, purchase/switch intent, or relevant verified revenue |
| Reachability | One specific active channel with a repeatable research or outreach path |

Google Trends is not a gate. Assign exactly one verdict:

- **Validate now**: all three gates pass.
- **Research more**: evidence is missing, thin, inaccessible, or the targeted search is incomplete.
- **Pivot**: the problem passes but the buyer, segment, wedge, or channel is wrong.
- **Kill**: targeted research is complete but repeated problem evidence or action/spend is absent.

Do not use `Kill` merely because a source is blocked or Google Trends is low. Do not use `Validate now` because one proxy, launch, or comparable is strong.

## Ranking

Only after gating, score eligible candidates from 1-5:

| Factor | Meaning |
|---|---|
| Problem severity | Emotional, financial, risk, or time stakes are strong and repeated. |
| Buyer/action strength | The buyer is clear and observable behavior supports action or spend. |
| Demand momentum | Trends and related-query evidence improve timing confidence without acting as a gate. |
| Competitive gap | Complaints or underserved behavior support a wedge beyond "better app". |
| Reachability | The audience can be found manually in communities or direct channels. |
| Validation speed | A manual test can produce decision-quality evidence in 7-14 days. |

Scores rank candidates that passed; they never compensate for a failed gate. Omit the ranking table when none pass.

## Default Scorecard Fields

Use these fields in full sprint outputs:

| Field | Guidance |
|---|---|
| Pain | Name the problem in customer-centered language. |
| Evidence | Use a short quote, source note, or observed repeated theme. |
| Frequency | Use 1-5, or low/medium/high if source volume is thin. |
| Intensity | Use 1-5 based on urgency, emotion, cost, or risk. |
| Current workaround | Name what people do today, even if it is manual or bad. |
| Solvability | Use 1-5 based on whether a focused product/service could help. |

## Evidence vs Inference Output

Keep the distinction visible:

- **Evidence**: what was directly seen in source data.
- **Inference**: what likely follows, but is not proven.
- **Unknowns**: facts that must be researched or tested before committing.

If evidence quality is weak, keep recommendations smaller and push the next step toward data collection instead of product design.

## Pre-Build Experiment

For `Validate now`, recommend the smallest manual or concierge test that can run in 7-14 days. State the buyer, channel, offer or action requested, sample target, success metric, and kill criterion. For other verdicts, make the next test close the highest-impact evidence gap rather than build software.
