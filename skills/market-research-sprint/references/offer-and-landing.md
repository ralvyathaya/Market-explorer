# Offer and Landing Workflow

## Evidence Gate

Generate offers or landing-page briefs after the candidate receives `Validate now`, or when the user explicitly requests them. If a gate has not passed, label the result as a hypothesis and name the missing proof. A full sprint does not automatically include an offer or landing page.

## Opportunity Generation

Start from known pain points, action/spend evidence, a reachable channel, and the competitive gap. If the user explicitly requests concepts before those exist, generate hypotheses but mark them as unvalidated.

Apply these lenses:

- **Segment wedge**: solve the pain for a specific underserved group before going broad.
- **Simplification**: remove complexity from existing solutions and focus on the core job.
- **Premium/service layer**: add expert help, done-with-you support, accountability, or trust.
- **Business model shift**: subscription, one-time kit, concierge service, marketplace, community, audit, course, template, or hybrid.
- **Distribution wedge**: community, SEO, partnerships, creators, professional referrals, integrations, local channels.
- **New paradigm**: new tech, behavior shift, regulation, data availability, or cultural change that makes a different approach viable.

For each concept, include:

- Name.
- Buyer.
- Target segment.
- Pain addressed.
- Core promise.
- Mechanism: why this works differently.
- MVP test: smallest manual proof before building.
- Business model.
- Differentiator.
- Risks.

## Opportunity Ranking

Rank the top 3 using:

| Factor | Meaning |
|---|---|
| Pain severity | The problem is urgent, costly, or emotionally loaded. |
| Reachability | The audience gathers in findable places. |
| Payment likelihood | Users already spend money or time solving this. |
| Differentiation | The concept has a clear wedge beyond generic quality. |
| Build feasibility | A small version can be tested quickly. |
| Category potential | It could become the obvious choice for a narrow niche. |

Be brutally honest. If every idea is weak, say so and propose a sharper pivot.

## Offer Brief

Use this structure:

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

When offer generation is allowed, compress the top offers into this table:

```markdown
| Offer | Buyer | Promise | Differentiator | MVP test | Risk |
|---|---|---|---|---|---|
```

The MVP test must be manual or concierge-first when possible and run in 7-14 days. Avoid recommending software buildout until the problem, action/spend, and reachability gates pass.

## Landing Page Brief

Create a builder-agnostic landing page brief only after a passing verdict or an explicit request. Only create a Lovable.dev, Framer, Webflow, or other tool-specific prompt when the user asks for that tool.

Use a Before-After-Bridge structure:

1. Above the fold: product, audience, urgent problem, differentiated promise, primary CTA.
2. Current pain: make the audience feel understood using verified customer language.
3. Desired outcome: show the new reality and emotional payoff.
4. Bridge/product: explain the mechanism and why it is credible.
5. How it works: 3 steps maximum unless the product truly needs more.
6. Proof: testimonials, quotes, case snippets, waitlist signal, or transparent "early access" framing.
7. Pricing or next step: trial, consultation, waitlist, audit, preorder, or interview.
8. FAQ: objections from the research.
9. Final CTA.

Do not invent testimonials, founder credentials, expert endorsements, medical/legal claims, or fake integrations. Use placeholders when proof is missing.

Always include **Proof needed** in landing page briefs. If proof is missing, recommend the smallest credible proof to gather next, such as 5 customer interviews, a waitlist, a before/after case note, or a paid pilot.

## Builder Prompt Format

When asked for a builder prompt, return one copy-paste block:

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
