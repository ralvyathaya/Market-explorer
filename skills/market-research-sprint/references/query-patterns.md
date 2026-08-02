# Query Patterns

Use these patterns to gather evidence across problem, demand, spend, competition, and distribution. Adapt language, geography, and community names to the market. Prefer several targeted queries over one huge query.

## Reddit Queries

Core pattern:

```text
"{market or pain}" site:reddit.com/r/ "{first-person phrase}"
```

Useful first-person phrases:

```text
"I tried"
"I hate"
"I wish"
"I can't"
"I struggle with"
"my biggest problem"
"my biggest fear"
"what worked for me"
"what I wish I knew"
"does anyone else"
"any alternatives to"
"worth it"
"too expensive"
"waste of money"
"finally found"
"I regret"
```

Pain-oriented patterns:

```text
"{market}" site:reddit.com "I struggle with"
"{market}" site:reddit.com "what I wish I knew"
"{market}" site:reddit.com "any alternatives to"
"{competitor or solution}" site:reddit.com "too expensive"
"{competitor or solution}" site:reddit.com "I hate"
"{job to be done}" site:reddit.com "does anyone else"
```

Subreddit pattern:

```text
site:reddit.com/r/{subreddit} "{pain phrase}" "{market term}"
```

## Community and Forum Queries

```text
"{market}" "forum" "I struggle"
"{market}" "community" "I wish"
"{market}" "support group" "I tried"
"{market}" "Facebook group" "recommend"
"{market}" "Discord" "problem"
```

## Review and Competitor Queries

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

On review, app-store, and issue pages, capture recurring complaints, requested alternatives, workaround behavior, review recency, and the segment or job being described. Do not infer frequency from one highlighted review.

## Google Trends Protocol

Build a small comparison set with the candidate problem, job-to-be-done, category, and leading alternatives. For the target geography:

1. Compare a broad topic and exact search terms where both exist.
2. Inspect five years for baseline direction and seasonality.
3. Inspect twelve months for current direction and spikes.
4. Record regional concentration and rising/breakout related queries.
5. Save the Trends link or CSV and access date.

Do not label the 0-100 index as search volume, TAM, or purchase intent. If the term is too small to register, record `insufficient Trends data`, not `no demand`.

## Commercial and Launch Queries

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

Use TrustMRR data as verified commercial evidence only for the listed product and date. Use Product Hunt votes/comments as launch attention only. Founder claims remain self-reported unless independently corroborated.

## Comparable Product Collection

Collect 3-5 products total and label each `direct`, `substitute`, or `successful analog`.

```markdown
| Product | Type | Audience/JTBD | Pricing | Traction source/date | Complaints/gap | Transferable mechanism |
|---|---|---|---|---|---|---|
```

Do not copy a feature merely because a successful analog has it. Extract the mechanism, buyer motion, or distribution pattern that might transfer to the candidate market.

## Jobs-to-Be-Done Queries

Use when the product category is unclear:

```text
"how do I {job}" "{audience}"
"best way to {job}" "{constraint}"
"tool for {job}" "{audience}"
"template for {job}" "{market}"
"service that helps with {job}"
```

## Output Format

When asked for a query pack, return:

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

If browsing is blocked, return this query/export pack and mark the affected gates as unknown. Do not fabricate results or convert missing evidence into `Kill`.
