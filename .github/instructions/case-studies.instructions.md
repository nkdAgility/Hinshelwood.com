````instructions
---
applyTo:
  - site/content/case-studies/**
---

# Case Studies Instructions

## Purpose

Case studies for hinshelwood.com document real client work with measurable outcomes for senior buyers evaluating systems of work decisions. Write for CTOs, engineering/product/platform leaders, growth and revenue leaders, boards, and executive sponsors.

Focus on what changed and measurable progress. Do not focus on tools or methods. Present Martin as diagnostician and expert consultant who helps leaders understand and manage their systems of work, not as someone doing delivery for the client or owning outcomes.

No theoretical examples. No sanitized success stories that hide the messy reality. No promotional tone or demand-gen tactics. Case studies must stand alone and be useful without a pitch.

## Content Requirements

Every case study must include:
- **Client context**: Who they are, what they do (no need to name them if confidential)
- **The problem**: What wasn't working. Be specific. Quantify when possible.
- **What we did**: Concrete actions taken. Not "we aligned stakeholders" but "we ran 3 workshops with engineering and product teams to..."
- **The outcome**: Measurable results. Revenue impact, time saved, defects reduced, deployment frequency increased.
- **What didn't work**: Be honest about missteps and pivots. This builds credibility.

## Writing Standards

- **American English only**
- **No em dashes** (use full stops, commas, or shorter sentences)
- **No analogies** (say what you mean directly)
- Start with the outcome. Lead with the impact, not the backstory.
- Use real numbers. "Reduced deployment time by 60%" beats "significantly improved."
- Show your work. Explain the reasoning behind decisions.
- Avoid generic consulting speak. "We partnered to drive enablement" says nothing.
- Make it scannable. Use subheadings for each major section.
- Emphasise constraints, risk, learning speed, decision quality, evidence, flow, strategic optionality.
- Assume issues are systemic, not people failures.
- Start with buyer problem/risk, name why it persists, identify the constraint, state consequences of inaction.
- Stop short of prescribing solutions unless explicitly asked.

## No Consultant Speak (CRITICAL)

**Use leadership language, not consultant speak.** Allan Weiss promotes communicating in terms buyers understand, not industry jargon or consulting terminology.

**Case studies document real work. They should read like honest project reports from experienced leaders, not sanitized consulting success stories.**

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

**Say what actually happened**:
- ✅ "Teams started deciding faster" (not "enabled decision velocity")
- ✅ "Leaders began seeing problems earlier" (not "enhanced visibility")
- ✅ "Engineering shipped twice as often" (not "accelerated delivery cadence")
- ✅ "Costs dropped by 40%" (not "optimized spend efficiency")

**Use concrete business terms**:
- ✅ "Deployment frequency increased from weekly to 10 times per day"
- ✅ "Incident response time dropped from 4 hours to 20 minutes"
- ✅ "Coordination meetings reduced from 15 to 3 per week"
- ✅ "Engineering time for new features increased from 50% to 80%"

**Describe activities plainly**:
- ✅ "Martin worked with the CTO to map where decisions stalled" (not "facilitated executive alignment workshops")
- ✅ "Ran 3 workshops with engineering and product teams to identify conflicting priorities" (not "orchestrated cross-functional collaboration sessions")
- ✅ "Helped engineering leaders identify where platforms slowed teams down" (not "optimized platform operating model")
- ✅ "Reviewed code review process with 5 senior engineers" (not "assessed development workflow maturity")

### Test Your Language

Ask: **Would you explain this to a board member using these exact words?**

- If yes, keep it
- If no, rewrite in plain business language

Remember: Case studies prove Martin's value through honest documentation of real results using language buyers speak, not consulting frameworks.

## Front Matter Requirements

```yaml
---
title: "Client Name or Problem Focus"
date: YYYY-MM-DD
description: "One sentence outcome"
diagnosis:
  constraint: "The constraint this engagement addressed"
  outcome: "What changed"
  evidence: "Measurable results"
related:
  - "problems/devops"
  - "outcomes/engineering-excellence"
tags: ["relevant", "tags"]
categories: ["case-studies"]
---
```

### Related Items Linking (CRITICAL)

**Case studies should link TO problems and outcomes** using the `related:` array.

**DO NOT add case studies to insight `related:` arrays.** Insights link TO case studies, not the other way around. The system handles bidirectional display automatically via `get-related-items.html` function.

**DO NOT add insights to case study `related:` arrays.** Let insights declare the relationship.

**Path format**: Use `section/slug` without leading or trailing slashes:
- ✅ `"problems/devops"`
- ✅ `"outcomes/engineering-excellence"`
- ❌ `"insights/why-ai-is-making-delivery-harder"` (insights link TO case studies, not reverse)

**What gets displayed**:
- Case study page automatically displays: related outcomes → related problems
- Any insights that list this case study in their `related:` array will automatically display this case study

## Red Flags to Eliminate

- Claims without evidence
- Vague descriptions of work done
- Missing outcomes or results
- Overstating your role or impact (Martin helps leaders understand and manage systems of work, not deliver for them)
- Hiding the complexity or challenges
- Promotional tone or demand-gen tactics
- Prescribing solutions when the case was diagnostic
- Hype or evangelism
- "Agile transformation" (prefer "systems of work redesign")
- "mindset" (prefer "ethos" when culture is relevant)
- "maturity models" (use specific capability assessments)
- Guaranteed results or fixed methodologies

If you can't quantify the result, explain why and what qualitative indicators you tracked instead.

## Language Rules

Use consistent, precise terminology when describing organisational design and work structures:

**Default term**: Use "systems of work" when describing processes, practices, funding flows, decision patterns, and governance mechanics.

**Executive context**: When addressing executives, boards, investors, or C-suite audiences, prefer "operating model" or "operating model hygiene" over "systems of work".

**Banned terms**: Never introduce or reintroduce "ways of working", "ways of work", or "mindset shifts" as preferred terms. These are vague and lack precision.

**Software systems**: If discussing software systems, technology architecture, or platforms, use explicit terms like "software systems", "technical architecture", or "platforms" to avoid ambiguity with "systems of work".

### Example Rewrites

**Before**: "We changed their ways of working and drove mindset shifts."
**After**: "We redesigned their systems of work to enable faster decision-making."

**Before**: "The organisation's ways of work prevented teams from adapting."
**After**: "The organisation's systems of work prevented teams from adapting."

**Executive context before**: "Your systems of work create coordination overhead."
**Executive context after**: "Your operating model creates coordination overhead."

### Decision Rule

- If describing how work is designed to flow (processes, practices, governance, funding): use "systems of work".
- If speaking to executives about organisational design and constraints: use "operating model".
- If discussing software, platforms, or technical architecture: use explicit technical terms, not "systems".

````
