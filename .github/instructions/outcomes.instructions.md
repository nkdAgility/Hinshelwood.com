````instructions
---
applyTo:
  - site/content/outcomes/**
---

# Outcomes Instructions

## Purpose

Outcome pages for hinshelwood.com describe measurable results and business value for senior buyers evaluating systems of work decisions. Write for CTOs, engineering/product/platform leaders, growth and revenue leaders, boards, and executive sponsors.

Focus on capability development and tangible impact, not process descriptions. Emphasise strategic optionality, decision quality, learning speed, and business value. No promotional tone or demand-gen tactics.

## Content Requirements

Each outcome page must:
- **State the outcome clearly**: What specific results do clients achieve?
- **Quantify when possible**: Use metrics, percentages, time frames
- **Show the path**: How do clients get from current state to this outcome?
- **Connect to business value**: Why does this outcome matter to the business?
- **Emphasise**: Constraints removed, risk reduced, learning speed increased, decision quality improved
- **Assume**: Issues are systemic, not people failures

## Structure

1. **Outcome statement**: The main result (the page title)
2. **What this means**: Concrete examples of this outcome in practice
3. **Key indicators**: How you measure and track this outcome
4. **The journey**: Major phases clients go through to achieve this
5. **Business impact**: Connection to revenue, efficiency, quality, or morale

## Writing Standards

- **American English only**
- **No em dashes** (use full stops, commas, or shorter sentences)
- **No analogies** (say what you mean directly)
- Lead with results, not methodology.
- Use client language, not consultant speak. "Faster releases" not "accelerated delivery cadence."
- Provide real metrics from past engagements (anonymised if needed).
- Be honest about timelines. "This takes 3-6 months" is better than vague "we'll work together to..."
- Link to relevant case studies that demonstrate this outcome.
- Direct, pragmatic, executive-safe language.
- Start with buyer problem/risk, explain the constraint, state consequences of inaction.
- Stop short of prescribing solutions unless explicitly asked.

## No Consultant Speak (CRITICAL)

**Use leadership language, not consultant speak.** Allan Weiss promotes communicating in terms buyers understand, not industry jargon or consulting terminology.

**Outcome pages describe business results. They should read like performance reports, not capability frameworks.**

### Consultant Speak to Avoid

**Process/methodology jargon**:
- ❌ "stakeholder alignment"
- ❌ "change management"
- ❌ "organizational transformation"
- ❌ "engagement model"
- ❌ "delivery framework"
- ❌ "capability maturity"
- ❌ "operating rhythm"
- ❌ "value streams"
- ❌ "centre of excellence"

**Vague action verbs**:
- ❌ "enable", "empower", "facilitate"
- ❌ "drive", "accelerate", "optimize"
- ❌ "transform", "revolutionize"
- ❌ "leverage", "utilize"
- ❌ "orchestrate", "operationalize"

**Abstract outcomes**:
- ❌ "enhanced collaboration"
- ❌ "improved agility"
- ❌ "increased alignment"
- ❌ "cultural shift"
- ❌ "organizational resilience"

### Leadership Language to Use

**Say what actually happens**:
- ✅ "Teams decide faster" (not "enable decision velocity")
- ✅ "Leaders see problems earlier" (not "enhance visibility")
- ✅ "Engineering ships twice as often" (not "accelerate delivery cadence")
- ✅ "Costs dropped by 40%" (not "optimize spend efficiency")

**Use concrete business terms**:
- ✅ "Deploy 10 times per day"
- ✅ "Cut incident response from 4 hours to 20 minutes"
- ✅ "Reduced coordination meetings from 15 to 3 per week"
- ✅ "Freed up 30% of engineering time for new features"

**Describe outcomes as measurable changes**:
- ✅ "Deployment frequency increased from weekly to daily"
- ✅ "Bug escape rate dropped from 15% to 2%"
- ✅ "Feature delivery time reduced from 3 months to 3 weeks"
- ✅ "Platform onboarding time decreased from 2 weeks to 1 day"

### Test Your Language

Ask: **Would a CFO or board member understand this metric without explanation?**

- If yes, keep it
- If no, rewrite in plain business language

Remember: Outcome pages should read like quarterly business reviews, not consulting capability models.

## Front Matter Requirements

```yaml
---
title: "Clear Outcome Description"
date: YYYY-MM-DD
description: "One sentence describing the business impact"
diagnosis:
  capability: "The capability this outcome represents"
  impact: "Business value and strategic benefit"
  signal: "Evidence this outcome is relevant"
related:
  - "problems/scaling"
tags: ["relevant", "tags"]
categories: ["outcomes"]
---
```

### Related Items Linking (CRITICAL)

**Outcomes typically link TO problems** using the `related:` array (if they address specific constraints).

**Most linking TO outcomes happens FROM other content types.** Case studies and insights link to outcomes to show what changes when constraints are removed.

**DO NOT add reverse links.** The system handles bidirectional display automatically via `get-related-items.html` function.

**Path format**: Use `section/slug` without leading or trailing slashes:
- ✅ `"problems/scaling"`
- ❌ `"case-studies/..."` (case studies link TO outcomes, not reverse)
- ❌ `"insights/..."` (insights link TO outcomes, not reverse)

**What gets displayed**:
- Outcome page automatically displays: related case studies → related insights → related problems
- Display is populated by case studies and insights that list this outcome in their `related:` arrays

## Examples of Good vs. Bad Outcome Descriptions

**Bad**: "Improved agility and responsiveness"
**Good**: "Deploy to production 10x per day with 60% fewer defects"

**Bad**: "Enhanced team collaboration"
**Good**: "Cross-functional teams resolve incidents in under 2 hours"

**Bad**: "Modern engineering practices"
**Good**: "Automated testing catches 85% of bugs before production"

## Avoid

- Vague enablement promises
- Outcomes that can't be measured or verified
- Process outputs masquerading as outcomes ("implemented Scrum" is not an outcome)
- Ignoring the effort required
- Overselling what's achievable
- "Agile transformation" (prefer "systems of work redesign")
- "ways of working" (prefer "systems of work" or "operating model")
- "mindset" (prefer "ethos" when culture is relevant)
- "maturity models" (use specific capability assessments)
- Guaranteed results or fixed methodologies
- Hype or evangelism

If you can't point to multiple clients who've achieved this outcome working with you, don't claim it.

## Language Rules

Use consistent, precise terminology when describing organisational design and work structures:

**Default term**: Use "systems of work" when describing processes, practices, funding flows, decision patterns, and governance mechanics.

**Executive context**: When addressing executives, boards, investors, or C-suite audiences, prefer "operating model" or "operating model hygiene" over "systems of work".

**Banned terms**: Never introduce or reintroduce "ways of working", "ways of work", or "mindset shifts" as preferred terms. These are vague and lack precision.

**Software systems**: If discussing software systems, technology architecture, or platforms, use explicit terms like "software systems", "technical architecture", or "platforms" to avoid ambiguity with "systems of work".

### Example Rewrites

**Before**: "Teams adopt new ways of working and mindset shifts."
**After**: "Teams adopt new systems of work that enable continuous improvement."

**Before**: "The organisation's ways of work support rapid learning."
**After**: "The organisation's systems of work support rapid learning."

**Executive context before**: "Your systems of work enable faster delivery."
**Executive context after**: "Your operating model enables faster delivery."

### Decision Rule

- If describing how work is designed to flow (processes, practices, governance, funding): use "systems of work".
- If speaking to executives about organisational design and constraints: use "operating model".
- If discussing software, platforms, or technical architecture: use explicit technical terms, not "systems".

````
