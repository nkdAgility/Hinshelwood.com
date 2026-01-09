````instructions
---
applyTo:
  - site/content/insights/**
---

# Insights Instructions

## Purpose

Insights for hinshelwood.com are buyer-diagnostic articles that help senior leaders understand systems of work, operating model constraints, and outcome risk. Write for CTOs, engineering/product/platform leaders, growth and revenue leaders, boards, and executive sponsors.

Produce buyer-diagnostic insight that shapes decisions upstream of buying, without promotional tone or demand-gen tactics. Insights must stand alone and be useful without a pitch.

Take clear positions backed by experience. Defend them. Challenge conventional wisdom. Avoid hype or evangelism.

## Content Requirements

Every insight article must:
- **Take a stance**: Have a clear point of view
- **Support with evidence**: Personal experience, data, examples from the field
- **Address counterarguments**: Don't ignore obvious objections
- **Provide actionable takeaways**: Readers should know what to do with this information
- **Emphasise**: Constraints, risk, learning speed, decision quality, evidence, flow, strategic optionality
- **Assume**: Issues are systemic, not people failures
- **Stop short of prescribing solutions** unless explicitly asked

## Structure

1. **Hook**: Open with a provocative statement, question, or real scenario (2-3 sentences)
2. **The problem**: What's wrong with current thinking or practice (1-2 paragraphs)
3. **Your position**: State your view clearly (1 paragraph)
4. **The case**: Build your argument with evidence and examples (3-5 paragraphs)
5. **Objections**: Address the strongest counterarguments (1-2 paragraphs)
6. **Action**: What should readers do with this (1 paragraph)

## Writing Standards

- **American English only**
- **No em dashes** (use full stops, commas, or shorter sentences)
- **No analogies** (say what you mean directly)
- Use "I" and "you." This is personal expertise, not a research paper.
- Cut unnecessary qualifiers. "Usually," "often," "tends to" weaken your point.
- Be specific. "Daily standups waste time" is better than "meetings can be inefficient."
- Use examples from real work. Anonymise if needed, but keep it concrete.
- Break up text. No paragraph longer than 5 lines.
- Direct, pragmatic, executive-safe language.
- Start with buyer problem/risk, name why it persists, identify the constraint, state consequences of inaction.

## No Consultant Speak (CRITICAL)

**Use leadership language, not consultant speak.** Allan Weiss promotes communicating in terms buyers understand, not industry jargon or consulting terminology.

**Insights build buyer understanding. They should read like strategic analysis from an experienced leader, not consulting pitches.**

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

**Describe problems and solutions plainly**:
- ✅ "Product and engineering can't agree on priorities" (not "misalignment between product and engineering")
- ✅ "Teams spend 3 days coordinating what should take 30 minutes" (not "sub-optimal coordination overhead")
- ✅ "Leaders discover problems after decisions are locked in" (not "feedback loops need optimization")

### Test Your Language

Ask: **Would a CTO say this to their CFO in a hallway conversation?**

- If yes, keep it
- If no, rewrite in plain business language

Remember: Insights should sound like experienced leadership analysis, not consulting slide decks.

## Front Matter Requirements

```yaml
---
title: "Clear, Specific Title"
date: YYYY-MM-DD
description: "Your main point in one sentence"
diagnosis:
  question: "The question this insight answers"
  statement: "Core diagnostic statement"
  reason: "Why this problem persists"
  signal: "Evidence this insight is relevant to the reader"
related:
  - "problems/ai"
  - "outcomes/technical-leadership"
  - "case-studies/when-product-leadership-breaks-across-borders"
tags: ["relevant", "tags"]
categories: ["insights"]
author: "Martin Hinshelwood"
---
```

### Related Items Linking (CRITICAL)

**Insights should link TO problems, outcomes, and case studies** using the `related:` array.

**DO NOT add insights to case study `related:` arrays.** The system handles bidirectional linking automatically via `get-related-items.html` function. If you add relationships in both directions, content will display duplicate links.

**Path format**: Use `section/slug` without leading or trailing slashes:
- ✅ `"problems/ai"`
- ✅ `"case-studies/restoring-delivery-visibility-and-governance-at-enterprise-scale"`
- ✅ `"outcomes/technical-leadership"`

**What gets displayed**:
- Insights page automatically displays: related problems → related case studies → related outcomes
- Any content that lists this insight in its `related:` array will also appear automatically

## Avoid

- Academic hedging ("it could be argued that...")
- Restating common wisdom without adding new perspective
- Lists without context (not just "10 tips" without explanation)
- Ending without a clear takeaway
- Corporate safe-speak that offends no one and helps no one
- "Agile transformation" (prefer "systems of work redesign")
- "ways of working" (prefer "systems of work" or "operating model")
- "mindset" (prefer "ethos" when culture is relevant)
- "maturity models" (use specific capability assessments)
- Guaranteed results or fixed methodologies
- Hype or evangelism

If you're not willing to defend the position in the comments, don't publish it.

## Language Rules

Use consistent, precise terminology when describing organisational design and work structures:

**Default term**: Use "systems of work" when describing processes, practices, funding flows, decision patterns, and governance mechanics.

**Executive context**: When addressing executives, boards, investors, or C-suite audiences, prefer "operating model" or "operating model hygiene" over "systems of work".

**Banned terms**: Never introduce or reintroduce "ways of working", "ways of work", or "mindset shifts" as preferred terms. These are vague and lack precision.

**Software systems**: If discussing software systems, technology architecture, or platforms, use explicit terms like "software systems", "technical architecture", or "platforms" to avoid ambiguity with "systems of work".

### Example Rewrites

**Before**: "We need to change our ways of working and adopt new mindset shifts."
**After**: "We need to redesign our systems of work to support faster decision-making."

**Before**: "The organisation's ways of work prevent teams from adapting quickly."
**After**: "The organisation's systems of work prevent teams from adapting quickly."

**Executive context before**: "Your systems of work create unnecessary coordination overhead."
**Executive context after**: "Your operating model creates unnecessary coordination overhead."

### Decision Rule

- If describing how work is designed to flow (processes, practices, governance, funding): use "systems of work".
- If speaking to executives about organisational design and constraints: use "operating model".
- If discussing software, platforms, or technical architecture: use explicit technical terms, not "systems".

````
