---
name: market-research-sprint
description: Pre-build market validation workflow for discovering niches, triangulating customer pain with demand and commercial signals, analyzing competitors, and deciding whether to validate, research more, pivot, or kill an idea. Use for market exploration, idea validation, Google Trends research, Reddit/review analysis, Product Hunt or TrustMRR comparisons, opportunity ranking, offer shaping, and evidence-backed landing-page briefs.
---

# Market Research Sprint

## Overview

Use this skill to decide what deserves validation before someone builds. For digital-first markets, connect problem evidence, demand momentum, commercial behavior, competitors, and distribution into a clear pre-build verdict. Preserve what is evidence, label what is inference, and never present proxy signals as proof of demand.

Match the user's language in final outputs. Keep this skill's internal reasoning and structure in English unless the user asks otherwise.

## Workflow

Choose the smallest workflow that answers the user:

1. **Market map**: use when the user wants ideas, categories, niches, or a focused market tree.
2. **Source query pack**: use when the user needs Reddit/community/web search queries before data collection.
3. **Pain-point extraction**: use when the user provides comments, reviews, transcripts, links, or search results.
4. **Pre-build validation**: use for “market explorer,” “validate idea,” “before building,” trend research, or competitor traction. Run the full pipeline below.
5. **Gap and offer generation**: use after a candidate passes the gates, or when the user explicitly asks for hypotheses.
6. **Landing-page brief**: use after the gates pass or when explicitly requested. Label weakly evidenced positioning as a hypothesis.
7. **Full sprint**: run the pre-build pipeline end-to-end. Do not automatically generate an offer or landing page.

## Pre-Build Pipeline

Run in this order:

1. Define the market, buyer, job-to-be-done, geography, and candidate segments.
2. Find repeated problem evidence across independent source families.
3. Examine Google Trends for momentum, seasonality, geography, and related queries.
4. Find action or spend through workarounds, paid products, pricing, and relevant verified-revenue comparables.
5. Compare 3-5 direct competitors, substitutes, and successful analogs.
6. Identify one repeatable way to reach the buyer.
7. Apply the hard gates, rank only eligible candidates, and return a verdict.
8. Propose a manual 7-14 day experiment with a success metric and kill criterion.

Read only the reference file needed for the current task:

- `references/research-workflow.md`: intake, evidence collection, signal interpretation, hard gates, verdicts, and ranking.
- `references/query-patterns.md`: problem, trend, commercial, competitor, and distribution research patterns.
- `references/offer-and-landing.md`: post-gate opportunity generation, offer shaping, and landing-page formats.

## Ground Rules

- Do not quote users unless the text was provided by the user or retrieved from a visible source.
- Separate **Evidence**, **Inference**, **Unknowns**, and **Recommendation**.
- For every material signal, record the source, access date, what it proves, what it does not prove, and confidence.
- Default to public web pages. Do not require Google Trends alpha access, a TrustMRR API key, or a Product Hunt token; user-provided links or exports are optional accelerators.
- If using live web, cite opened sources. If browsing is unavailable or blocked, provide a query/export pack, identify the missing evidence, and use `Research more` rather than guessing.
- For Reddit/community analysis, prioritize first-person pain, attempted solutions, workarounds, tradeoffs, emotional stakes, repeated complaints, and requests for alternatives.
- Ignore shallow complaints, hypotheticals, advice-only threads, and comments without a concrete experienced problem.
- Treat Google Trends as normalized relative interest, not market size, absolute search volume, or revenue. A low Trends value alone cannot kill an idea with strong paid behavior.
- Treat Product Hunt votes and comments as launch attention, not revenue or retention.
- Treat TrustMRR as a strong verified commercial signal for listed companies, not a representative sample of the whole market.
- Do not default to broad TAM claims. Apply the hard gates before ranking opportunities.
- For sensitive domains such as health, legal, finance, parenting, custody, or mental health, avoid professional claims and include appropriate uncertainty.

## Hard Gates and Verdicts

An idea may receive `Validate now` only when all three gates pass:

1. **Problem**: at least three concrete experienced-problem examples across at least two independent source families.
2. **Action/spend**: behavior tied to the same segment and job-to-be-done, such as paying, using a costly workaround, expressing purchase/switch intent, or a relevant verified-revenue comparable.
3. **Reachability**: a specific active channel plus a repeatable collection or outreach path.

Google Trends is context, never a hard gate. Use exactly these verdicts:

- **Validate now**: all gates pass.
- **Research more**: evidence is missing, thin, or inaccessible.
- **Pivot**: the problem is real but the buyer, segment, wedge, or channel is wrong.
- **Kill**: targeted research is complete but repeated problem evidence or action/spend is absent.

After gating, score eligible candidates from 1-5 on problem severity, buyer/action strength, demand momentum, competitive gap, reachability, and validation speed. Scores rank candidates; they never override a failed gate.

## Default Output

For full sprint requests, produce:

```markdown
**Verdict**
Validate now / Research more / Pivot / Kill

1-3 direct sentences explaining the gate result and biggest remaining assumption.

**Research Snapshot**
- Market:
- Target customer:
- Geography/language:
- Evidence quality:
- Main unknown:

**Gate Card**
| Gate | Pass/Fail | Evidence | Missing proof |
|---|---|---|---|

**Problem Evidence**
| Problem | Segment/JTBD | Source family | Source/date | Evidence | Workaround/action |
|---|---|---|---|---|---|

**Google Trends Snapshot**
- Topic or exact term:
- Geography:
- Five-year direction:
- Twelve-month direction:
- Seasonality/spike risk:
- Rising related queries:
- Limitation:

**Competitors and Successful Analogs**
| Product | Type | Audience/JTBD | Pricing | Traction source/date | Complaints/gap | Transferable mechanism |
|---|---|---|---|---|---|---|

**Distribution**
- Reachable channel:
- Evidence of activity:
- Repeatable access path:

**Evidence Ledger**
| Claim | Label | Source/date | What it proves | What it does not prove | Confidence |
|---|---|---|---|---|---|

**Inference and Unknowns**
- Inference:
- Unknowns:

**Eligible Opportunity Ranking**
| Candidate | Problem | Action | Momentum | Gap | Reachability | Validation speed |
|---|---:|---:|---:|---:|---:|---:|

**Pre-Build Experiment**
1. Manual 7-14 day test:
2. Success metric:
3. Kill criterion:
4. Next step: test / collect evidence / pivot / stop
```

Omit ranking when no candidate passes the gates. Offer and landing sections appear only after a passing verdict or an explicit request. Shorten the output when the user asks for only one stage.

## Quality Bar

Before finalizing, check:

- The answer is specific to the chosen market, not a generic template.
- Every quote is traceable to provided or retrieved text.
- Every material metric is traceable to an opened source and access date.
- Assumptions are named plainly.
- The verdict follows the hard gates; proxy signals never override them.
- Google Trends, Product Hunt, and TrustMRR are interpreted according to their stated limits.
- The comparison includes direct products, substitutes, and successful analogs where available.
- The niche overlap check compares audience, pain, job-to-be-done, current workaround, buyer, channel, and customer language.
- Similar labels alone are not enough to merge niches; uncertain overlaps are labeled as hypotheses.
- The recommended candidate can be tested manually in 7-14 days before software buildout.
- A failed or unproven gate never produces an unqualified offer or landing-page recommendation.
