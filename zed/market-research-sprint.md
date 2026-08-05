# Market Research Sprint (Zed Rules)

Decide what deserves validation before building. Triangulate customer problems, demand momentum, commercial behavior, competitors, and distribution into a clear pre-build verdict. Preserve what is evidence, label what is inference, never present proxy signals as proof of demand.

Match the user's language in final outputs.

## How to invoke

In Zed, mention this file in the Agent Panel (`@market-research-sprint`) or add it as a Rules file, then ask e.g.:

```text
Run a full market research sprint for solo accountants who want more clients.
```

If Zed web search/fetch is unavailable or blocked, return the query/export pack instead of guessing, and use `Research more`.

## Workflow

Choose the smallest workflow that answers the user:

1. **Market map**: ideas, categories, niches, or a focused market tree.
2. **Source query pack**: Reddit/community/web search queries before data collection.
3. **Pain-point extraction**: user provides comments, reviews, transcripts, links, or search results.
4. **Pre-build validation**: "market explorer", "validate idea", "before building", trend research, or competitor traction. Run the full pipeline below.
5. **Gap and offer generation**: after a candidate passes the gates, or when explicitly asked (label as hypothesis if gates not passed).
6. **Landing-page brief**: after gates pass or explicit request. Label weakly evidenced positioning as hypothesis.
7. **Full sprint**: run the pre-build pipeline end-to-end. Do not auto-generate an offer or landing page.

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
- For sensitive domains (health, legal, finance, parenting, custody, mental health), avoid professional claims and include appropriate uncertainty.

## Hard Gates and Verdicts

`Validate now` only when all three gates pass:

1. **Problem**: at least three concrete experienced-problem examples across at least two independent source families.
2. **Action/spend**: same-segment and same-JTBD evidence of payment, costly workaround, purchase/switch intent, or relevant verified revenue.
3. **Reachability**: a specific active channel plus a repeatable collection or outreach path.

Google Trends is context, never a hard gate. Use exactly these verdicts:

- **Validate now**: all gates pass.
- **Research more**: evidence is missing, thin, or inaccessible.
- **Pivot**: the problem is real but the buyer, segment, wedge, or channel is wrong.
- **Kill**: targeted research is complete but repeated problem evidence or action/spend is absent.

After gating, score eligible candidates 1-5 on problem severity, buyer/action strength, demand momentum, competitive gap, reachability, and validation speed. Scores rank candidates; they never override a failed gate.

## Default Output (full sprint)

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

Omit ranking when no candidate passes the gates. Shorten output when the user asks for only one stage.

---

## Reference: Research Workflow

### Intake

Infer missing fields from the prompt when safe. Ask a concise follow-up only if the answer would materially change the research path.

Capture: market/niche, target audience/buyer, geography and language, research mode (ideation, data collection, pain extraction, pre-build validation, opportunity generation, landing page brief, full sprint), available evidence (pasted comments, links, notes, search results, reviews, transcripts, surveys, or none), output depth (quick scan, normal, deep).

Default to digital-first markets: SaaS, web and mobile apps, AI tools, digital products. Include services and manual workarounds as substitutes. For pre-build validation and full sprints, use `Problem -> Demand -> Spend -> Competition -> Distribution -> Verdict`.

### Market Map

```markdown
- Core market or domain
  - Category
    - Subcategory
      - Niche
        - Sub-niche
```

Use Health, Wealth, and Relationships only for broad/random ideation or when no domain is supplied. Keep categories distinct. Prefer clear segmentation dimensions:

- Demographic: age, role, life stage, income, family status.
- Behavioral: frequency, trigger event, current workaround, spending behavior.
- Psychographic: belief, fear, desired identity, motivation.
- Contextual: geography, regulation, device, workplace, channel, seasonality.

### Niche Overlap Detection

Run after creating a market map or on niche selection. Compare candidate niches across: audience, pain, job-to-be-done, current workaround, buyer, channel, customer language.

| Overlap Type     | Meaning                                                 |
| ---------------- | ------------------------------------------------------- |
| Audience overlap | Same customer, different pain.                          |
| Pain overlap     | Same pain, different customer.                          |
| JTBD overlap     | Same job-to-be-done, different category or niche label. |
| Solution overlap | Same workaround, competitor, or substitute behavior.    |
| Language overlap | Repeated customer phrases across niches.                |

| Action        | Use When                                                                                 |
| ------------- | ---------------------------------------------------------------------------------------- |
| Merge         | Audience, pain, job, buyer, and workaround are materially the same.                      |
| Split         | The label is broad but contains different triggers, urgency, or buying moments.          |
| Keep separate | Similar surface language hides different buyer, channel, urgency, or willingness to pay. |
| Research more | Overlap is plausible but evidence is thin or mostly inferred.                            |

Do not merge niches on similar labels alone. Weak evidence: mark confidence low and write the overlap as a hypothesis.

### Pain-Point Extraction

Scan all source material before grouping. Extract pain points showing a real experienced problem, not generic interest.

Include: first-person struggles; failed attempts with existing solutions; workarounds, spreadsheets, manual processes, hacks; emotional consequences (fear, embarrassment, lost time/money, relationship strain, health impact); repeated questions revealing confusion or unmet demand; specific usage scenarios.

Exclude: advice without a described problem; generic rants with no concrete situation; purely positive stories unless contrasting a prior pain; news, politics, memes, unrelated debate; vague market assumptions.

For each pain point capture: clear heading; one-sentence summary; 2-5 exact quotes when available; frequency (low/medium/high or count); intensity (low/medium/high from emotional language and stakes); solvability (low/medium/high); current workaround; existing solutions mentioned and why users dislike them.

### Demand Momentum

Use Google Trends when accessible. Check last five years and last twelve months for the target geography. Record: broad topic vs exact term; long-term and recent direction; seasonality and news-spike dependence; regional concentration; rising/breakout related queries. Google Trends is sampled, normalized relative interest 0-100: not market size, revenue, or purchase intent. If unavailable, request a shared Trends link or CSV export and mark demand momentum unknown.

### Commercial and Competitor Evidence

Compare 3-5 products across three types:

- **Direct competitor**: same audience and job-to-be-done.
- **Substitute**: different product or manual workflow for the same job.
- **Successful analog**: proven product with a transferable mechanism, buyer motion, or business model.

Capture audience, job, positioning, current pricing, traction signal and date, repeated complaints, apparent gap, transferable mechanism. Prefer first-party pricing/product pages.

| Source               | What it can support                                                               | What it cannot prove alone                                       |
| -------------------- | --------------------------------------------------------------------------------- | ---------------------------------------------------------------- |
| TrustMRR             | Verified revenue, MRR, subscriptions, customer counts, growth for listed products | Whole-market size, profitability, representative category demand |
| Product Hunt         | Launch attention, positioning, maker activity, votes, comments                    | Revenue, retention, durable demand                               |
| App stores           | Public ratings, review volume/recency, category rank, displayed install ranges    | Profit, retention, exact active users                            |
| Pricing/review pages | Paid alternatives, segments, objections, switching complaints                     | Verified revenue, market-wide frequency                          |
| Founder claims       | A lead for further research                                                       | Verified commercial proof unless independently corroborated      |

Commercial evidence must relate to the same segment and job-to-be-done. A popular adjacent product is an analog, not proof of candidate demand.

### Distribution Evidence

Name at least one active channel where the target buyer can be reached and one repeatable access path (specific community plus recurring problem queries, review ecosystem, partner directory, professional association, app-store category, direct-outreach list). "Social media" or "SEO" without a concrete audience and collection method fails the reachability gate.

### Evidence Rules

- **Evidence**: direct quotes, observed repeated themes, source links, user-provided facts.
- **Inference**: likely motivations, underserved segment hypotheses, implied willingness to pay.
- **Recommendation**: what to test, build, cut, or position next.

Never invent quotes or metrics, or cite "many users" unless source volume supports it. Open a source before quoting it. Thin evidence: say so and frame findings as hypotheses.

### Ranking (only after gating)

| Factor                | Meaning                                                                 |
| --------------------- | ----------------------------------------------------------------------- |
| Problem severity      | Emotional, financial, risk, or time stakes are strong and repeated.     |
| Buyer/action strength | Buyer is clear; observable behavior supports action or spend.           |
| Demand momentum       | Trends/related-query evidence improve timing confidence (not a gate).   |
| Competitive gap       | Complaints or underserved behavior support a wedge beyond "better app". |
| Reachability          | Audience can be found manually in communities or direct channels.       |
| Validation speed      | Manual test can produce decision-quality evidence in 7-14 days.         |

### Pre-Build Experiment

For `Validate now`, recommend the smallest manual or concierge test runnable in 7-14 days: buyer, channel, offer/action requested, sample target, success metric, kill criterion. For other verdicts, make the next test close the highest-impact evidence gap rather than build software.

---

## Reference: Query Patterns

Adapt language, geography, and community names to the market. Prefer several targeted queries over one huge query.

### Reddit Queries

```text
"{market or pain}" site:reddit.com/r/ "{first-person phrase}"
```

First-person phrases: "I tried", "I hate", "I wish", "I can't", "I struggle with", "my biggest problem", "my biggest fear", "what worked for me", "what I wish I knew", "does anyone else", "any alternatives to", "worth it", "too expensive", "waste of money", "finally found", "I regret".

```text
"{market}" site:reddit.com "I struggle with"
"{market}" site:reddit.com "what I wish I knew"
"{market}" site:reddit.com "any alternatives to"
"{competitor or solution}" site:reddit.com "too expensive"
"{competitor or solution}" site:reddit.com "I hate"
"{job to be done}" site:reddit.com "does anyone else"
site:reddit.com/r/{subreddit} "{pain phrase}" "{market term}"
```

### Community and Forum Queries

```text
"{market}" "forum" "I struggle"
"{market}" "community" "I wish"
"{market}" "support group" "I tried"
"{market}" "Facebook group" "recommend"
"{market}" "Discord" "problem"
```

### Review and Competitor Queries

```text
"{competitor}" reviews "too expensive"
"{competitor}" "alternatives"
"{competitor}" "complaints"
"{competitor}" "not worth it"
"{category}" "best" "for {specific segment}"
"{category}" "for {specific segment}" "reviews"
site:g2.com/products "{category or competitor}" reviews
site:capterra.com "{category or competitor}" reviews
site:apps.apple.com "{category or competitor}"
site:play.google.com/store/apps "{category or competitor}"
site:github.com/{owner}/{repo}/issues "{pain or missing feature}"
```

On review/app-store/issue pages: capture recurring complaints, requested alternatives, workaround behavior, review recency, and the segment/job described. Do not infer frequency from one highlighted review.

### Google Trends Protocol

Build a small comparison set (candidate problem, JTBD, category, leading alternatives). For the target geography: compare broad topic and exact terms; inspect five years for baseline/seasonality; inspect twelve months for direction/spikes; record regional concentration and rising/breakout related queries; save the Trends link or CSV and access date. Do not label the 0-100 index as search volume, TAM, or purchase intent. Too small to register = `insufficient Trends data`, not `no demand`.

### Commercial and Launch Queries

```text
site:trustmrr.com/startup "{competitor or category}"
site:trustmrr.com "{job to be done}" revenue
site:producthunt.com/products "{competitor or category}"
site:producthunt.com/posts "{job to be done}"
"{competitor}" pricing
"{competitor}" customers OR users OR case study
"{competitor}" changelog OR release notes
"{competitor}" alternative "{specific segment}"
```

TrustMRR = verified commercial evidence only for the listed product and date. Product Hunt votes/comments = launch attention only. Founder claims = self-reported unless corroborated.

### Comparable Product Collection

Collect 3-5 products, label each `direct`, `substitute`, or `successful analog`:

```markdown
| Product | Type | Audience/JTBD | Pricing | Traction source/date | Complaints/gap | Transferable mechanism |
| ------- | ---- | ------------- | ------- | -------------------- | -------------- | ---------------------- |
```

Extract the mechanism, buyer motion, or distribution pattern; do not copy a feature merely because a successful analog has it.

### Jobs-to-Be-Done Queries

```text
"how do I {job}" "{audience}"
"best way to {job}" "{constraint}"
"tool for {job}" "{audience}"
"template for {job}" "{market}"
"service that helps with {job}"
```

### Query Pack Output Format

```markdown
**Search Strategy**

- Goal:
- Best sources:
- Exclusions:
- Missing evidence this pack should close:

**Queries**
| Signal | Source | Query or collection action | What it can prove |
|---|---|---|---|

**Collection Instructions**

1. Open 5-10 high-signal pages across at least two source families.
2. Save first-person evidence, context, links, and access dates.
3. Keep problem, demand, commercial, and launch signals separate.
4. For each signal, record what it proves and what it does not prove.
5. Paste raw evidence or exported Trends CSV back for analysis.
```

If browsing is blocked, return this query/export pack and mark affected gates unknown. Do not fabricate results or convert missing evidence into `Kill`.

---

## Reference: Offer and Landing

### Evidence Gate

Generate offers or landing-page briefs after `Validate now`, or on explicit request. If a gate has not passed, label the result as a hypothesis and name the missing proof. A full sprint does not automatically include an offer or landing page.

### Opportunity Lenses

- **Segment wedge**: solve the pain for a specific underserved group first.
- **Simplification**: remove complexity; focus on the core job.
- **Premium/service layer**: expert help, done-with-you, accountability, trust.
- **Business model shift**: subscription, one-time kit, concierge, marketplace, community, audit, course, template, hybrid.
- **Distribution wedge**: community, SEO, partnerships, creators, professional referrals, integrations, local channels.
- **New paradigm**: new tech, behavior shift, regulation, data availability, cultural change.

For each concept include: name, buyer, target segment, pain addressed, core promise, mechanism, MVP test (smallest manual proof), business model, differentiator, risks.

### Opportunity Ranking (top 3)

| Factor             | Meaning                                             |
| ------------------ | --------------------------------------------------- |
| Pain severity      | Urgent, costly, or emotionally loaded.              |
| Reachability       | Audience gathers in findable places.                |
| Payment likelihood | Users already spend money or time solving this.     |
| Differentiation    | Clear wedge beyond generic quality.                 |
| Build feasibility  | A small version can be tested quickly.              |
| Category potential | Could become the obvious choice for a narrow niche. |

Be brutally honest. If every idea is weak, say so and propose a sharper pivot.

### Offer Brief

```markdown
**Offer**

- Name:
- Buyer:
- Audience/segment:
- Problem:
- Promise:
- Mechanism:
- Format:
- Differentiator:
- Price hypothesis:
- Primary acquisition channel:

**Why This Segment**

- Evidence:
- Inference:
- Unknowns:

**MVP Test**

- Build:
- Do manually:
- Success metric:
- Kill criterion:
```

Compressed table:

```markdown
| Offer | Buyer | Promise | Differentiator | MVP test | Risk |
| ----- | ----- | ------- | -------------- | -------- | ---- |
```

MVP test must be manual/concierge-first when possible, 7-14 days. No software buildout until gates pass.

### Landing Page Brief (Before-After-Bridge)

1. Above the fold: product, audience, urgent problem, differentiated promise, primary CTA.
2. Current pain: make the audience feel understood using verified customer language.
3. Desired outcome: new reality and emotional payoff.
4. Bridge/product: mechanism and credibility.
5. How it works: 3 steps max.
6. Proof: testimonials, quotes, case snippets, waitlist signal, or transparent "early access" framing.
7. Pricing or next step: trial, consultation, waitlist, audit, preorder, or interview.
8. FAQ: objections from the research.
9. Final CTA.

Do not invent testimonials, credentials, endorsements, medical/legal claims, or fake integrations. Use placeholders when proof is missing. Always include **Proof needed**: the smallest credible proof to gather next (5 customer interviews, waitlist, before/after case note, paid pilot).

### Builder Prompt Format (one copy-paste block)

```markdown
Create a conversion-focused landing page for [offer name].

Audience:
[specific audience]

Positioning:
[one-sentence positioning]

Use this structure:

1. Above the fold...
2. Current pain...
3. Desired outcome...
4. Product bridge...
5. How it works...
6. Proof...
7. FAQ...
8. Final CTA...

Copy requirements:

- Use these verified phrases where appropriate: [...]
- Do not invent testimonials or claims.
- Keep tone: [tone].

Design requirements:

- Mobile-first.
- Clear typography.
- High contrast.
- CTA visible above the fold and near final section.
- Visual style fitted to the market, not generic SaaS decoration.

Form/integration requirements:
[email capture, calendar booking, checkout, waitlist, or none]
```

---

## Quality Bar

- The answer is specific to the chosen market, not a generic template.
- Every quote is traceable to provided or retrieved text.
- Every material metric is traceable to an opened source and access date.
- Assumptions are named plainly.
- The verdict follows the hard gates; proxy signals never override them.
- Google Trends, Product Hunt, and TrustMRR are interpreted per their stated limits.
- The comparison includes direct products, substitutes, and successful analogs where available.
- Similar labels alone do not merge niches; uncertain overlaps are labeled hypotheses.
- The recommended candidate can be tested manually in 7-14 days before software buildout.
- A failed or unproven gate never produces an unqualified offer or landing-page recommendation.
