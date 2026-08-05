# market-research-sprint

`market-research-sprint` is a Codex skill for deciding what deserves validation before you build. It triangulates customer problems, demand momentum, commercial behavior, competitors, and distribution into a clear verdict.

It is useful for founders, indie hackers, marketers, creators, and builders who want to understand a market before building.

## What It Does

- Maps broad markets into categories, niches, and sub-niches.
- Creates Reddit, forum, review, app-store, Google Trends, competitor, and commercial-signal research plans.
- Detects overlapping niches and recommends merge, split, keep separate, or research more.
- Analyzes Reddit posts, reviews, GitHub issues, transcripts, surveys, or notes.
- Extracts customer pain points and exact customer language.
- Interprets Google Trends as relative momentum and seasonality, not market size.
- Separates Product Hunt launch attention from TrustMRR verified commercial signals.
- Compares direct competitors, substitutes, and successful analogs.
- Applies hard problem, action/spend, and reachability gates before ranking opportunities.
- Returns `Validate now`, `Research more`, `Pivot`, or `Kill`, plus a manual 7-14 day test.
- Creates offer or landing-page assets only after validation gates pass or when explicitly requested.

## Requirements

- Codex with local skills support.
- Node.js 18 or newer.
- `npx`, which normally comes with Node.js.

Check your setup:

```powershell
node --version
npx --version
```

## Install

Run:

```powershell
npx --yes github:ralvyathaya/codex-market-explorer
```

Then restart Codex.

Use it by mentioning the skill in a prompt:

```text
Use $market-research-sprint to research AI tools for small business owners.
```

By default, the installer copies the skill to:

```text
~/.codex/skills/market-research-sprint
```

If `CODEX_HOME` is set, it uses:

```text
$CODEX_HOME/skills/market-research-sprint
```

## Install Options

```powershell
npx --yes github:ralvyathaya/codex-market-explorer where

npx --yes github:ralvyathaya/codex-market-explorer install --dry-run

npx --yes github:ralvyathaya/codex-market-explorer install --force

npx --yes github:ralvyathaya/codex-market-explorer install --dest "$env:USERPROFILE\.codex\skills"
```

These commands show the install path, preview the install, replace an existing copy, or install to a custom skills folder.

`--dest` can point to either a skills directory or the final `market-research-sprint` skill directory.

## How To Use

Start prompts with:

```text
Use $market-research-sprint to ...
```

The skill can use public web research when available, or analyze pasted data only. No API key is required. It will not invent customer quotes or metrics; every quoted claim must come from pasted text or an opened source.

For best results, include:

- Market or niche.
- Target customer.
- Country/language, if relevant.
- Raw customer text, links, or notes.
- Desired output, such as market map, query pack, pain-point report, offer ideas, or landing page brief.

## Usage Examples

### Explore A Broad Market

```text
Use $market-research-sprint to explore the market for remote workers.
Map categories, niches, sub-niches, and the most promising customer segments.
```

### Focus On One Niche

```text
Use $market-research-sprint to research meal planning for people with ADHD.
Focus only on this niche and find sub-segments, likely pain points, and current workarounds.
```

### Create Search Queries

```text
Use $market-research-sprint to create a search query pack for people struggling with custody transitions after divorce.
I want Reddit, forum, review, and competitor query ideas.
```

### Detect Niche Overlap

```text
Use $market-research-sprint to compare these niches for overlap.
Detect shared audience, pain, JTBD, workaround, buyer, channel, and customer language.
Recommend merge, split, keep separate, or research more.

[paste niche list here]
```

### Analyze Pasted Reddit Comments

```text
Use $market-research-sprint to analyze this Reddit data.
Extract pain points, exact customer quotes, frequency, intensity, current solutions, and potential market gaps.

[paste comments here]
```

### Validate Before Building

```text
Use $market-research-sprint as a market explorer for an AI bookkeeping assistant for solo accountants in the US.
Find problem evidence beyond Reddit, check Google Trends, compare paid competitors and successful analogs using Product Hunt, TrustMRR, app stores, reviews, and public pricing, then return Validate now, Research more, Pivot, or Kill.
Do not create a product or landing page yet.
```

### Find Market Gaps And Offer Ideas

```text
Use $market-research-sprint to turn these pain points into business opportunities.
Rank the top 3 offers by pain intensity, reachability, willingness to pay, differentiation, and speed to validate.

[paste pain-point notes here]
```

### Create A Landing Page Brief

```text
Use $market-research-sprint to create a landing page brief from this research.
Use customer language, Before-After-Bridge structure, objections, FAQ, and CTA ideas.

[paste research here]
```

### Create A Lovable.dev Prompt

```text
Use $market-research-sprint to create a Lovable.dev prompt from this customer research.
Include page structure, copy, design direction, form requirements, and CTA placement.

[paste research here]
```

### Run A Full Sprint

```text
Use $market-research-sprint to run a full market research sprint for solo accountants who want more clients.
Triangulate problem, demand, spend, competition, and distribution. Apply the hard gates, rank only eligible opportunities, and propose a manual 7-14 day experiment.
```

A full sprint does not automatically create an offer or landing page. Ask for those explicitly after the evidence is strong enough.

## Better Inputs

Good input:

```text
Market: divorced parents managing custody transitions
Audience: parents with children aged 5-12
Country: US
Goal: decide whether to validate, research more, pivot, or kill
Data: pasted Reddit comments and forum posts
```

Weak input:

```text
Research parenting apps.
```

Weak input still works, but the output will be broader and more speculative.

You can ask for: `market map`, `search query pack`, `pain-point extraction`, `Google Trends snapshot`, `competitor and successful analog analysis`, `pre-build validation`, `market gap analysis`, `manual validation plan`, `offer ideas`, `landing page brief`, or `Lovable.dev prompt`.

## Use In Zed

Zed does not read Codex skills, so use the self-contained rules file at `zed/market-research-sprint.md` (SKILL.md and all three references inlined). Either:

- Copy it to your Zed user rules: `~/.config/zed/rules/market-research-sprint.md` (toggle it on in the Agent Panel), or
- Copy it into your project as `.rules` / a `.zed/rules/` file, or just mention `@zed/market-research-sprint.md` in the Agent Panel when you want to use it.

Then prompt normally:

```text
Run a full market research sprint for solo accountants who want more clients.
```

Without Zed web search/fetch tools, the agent will return a query/export pack instead of live research.

## Troubleshooting

If `npx` is not recognized, install Node.js 18 or newer, then open a new terminal and run `node --version` and `npx --version`.

If the skill does not appear in Codex, restart Codex first. Then check the install path:

```powershell
npx --yes github:ralvyathaya/codex-market-explorer where
```

If needed, reinstall:

```powershell
npx --yes github:ralvyathaya/codex-market-explorer install --force
```

To avoid live web research, tell Codex:

```text
Use $market-research-sprint, but only analyze the pasted data. Do not browse.
```

## Development

Run checks:

```powershell
node .\bin\market-research-sprint.js --self-test
node .\scripts\validate-skill.js
```

Optional package checks:

```powershell
npm test
npm pack --dry-run
```

## License

MIT. The standalone skill folder also includes `LICENSE.txt` so the skill remains licensed when copied outside this repo.
