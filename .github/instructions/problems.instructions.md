````instructions
---
applyTo:
  - site/content/problems/**
---

# Problems Instructions

## Purpose

Problem pages for hinshelwood.com define specific challenges for senior buyers evaluating systems of work decisions. Write for CTOs, engineering/product/platform leaders, growth and revenue leaders, boards, and executive sponsors.

Focus on clear problem articulation, not selling solutions. Emphasise constraints, risk, and systemic issues. Produce buyer-diagnostic insight that shapes decisions upstream of buying, without promotional tone or demand-gen tactics.

## Content Requirements

Each problem page must:
- **Define the problem precisely**: What specifically goes wrong?
- **Explain why it matters**: What's the business impact?
- **Show what it looks like**: Concrete symptoms and scenarios
- **Indicate who faces this**: What types of organisations or teams?
- **Emphasise**: Constraints, risk, learning speed limitations, decision quality issues
- **Assume**: Issues are systemic, not people failures
- **Stop short of prescribing solutions** unless explicitly asked

Do NOT:
- Jump to solutions (that comes later)
- Use vague problem statements ("struggling with agility")
- Lead with fear, uncertainty, and doubt tactics
- Oversimplify complex problems

## Structure

1. **Problem statement**: One clear sentence (the page title)
2. **What this looks like**: 2-3 specific scenarios or symptoms
3. **Why it happens**: Root causes, not just surface issues (identify the constraint)
4. **The impact**: Business consequences (time, money, quality, morale)
5. **Who experiences this**: Company size, team structure, industry factors

## Writing Standards

- **American English only**
- **No em dashes** (use full stops, commas, or shorter sentences)
- **No analogies** (say what you mean directly)
- Be descriptive, not prescriptive. You're diagnosing, not solving.
- Use real examples. Change names, but keep scenarios authentic.
- Quantify impact when possible. "Teams spend 40% of sprint time fixing production issues."
- Avoid blame. Focus on systemic issues, not people failures.
- Link to related problems when relevant.
- Direct, pragmatic, executive-safe language.
- Start with buyer problem/risk, name why it persists, identify the constraint, state consequences of inaction.

## No Consultant Speak (CRITICAL)

**Use leadership language, not consultant speak.** Allan Weiss promotes communicating in terms buyers understand, not industry jargon or consulting terminology.

**Problem pages diagnose constraints. They should read like technical incident reports, not consulting assessments.**

### Consultant Speak to Avoid

**Process/methodology jargon**:
- ❌ "stakeholder alignment issues"
- ❌ "change management resistance"
- ❌ "organizational transformation barriers"
- ❌ "engagement model friction"
- ❌ "delivery framework gaps"
- ❌ "capability maturity deficits"
- ❌ "operating rhythm challenges"
- ❌ "value stream impediments"
- ❌ "centre of excellence dysfunction"

**Vague action verbs**:
- ❌ "enable", "empower", "facilitate"
- ❌ "drive", "accelerate", "optimize"
- ❌ "transform", "revolutionize"
- ❌ "leverage", "utilize"
- ❌ "orchestrate", "operationalize"

**Abstract problem statements**:
- ❌ "collaboration challenges"
- ❌ "agility limitations"
- ❌ "alignment issues"
- ❌ "cultural dysfunction"
- ❌ "resilience gaps"

### Leadership Language to Use

**Say what actually goes wrong**:
- ✅ "Teams wait 3 days for architecture decisions" (not "decision velocity constraints")
- ✅ "Leaders discover quality problems after release" (not "feedback loop delays")
- ✅ "Engineering spends 60% of time on coordination" (not "coordination overhead inefficiency")
- ✅ "Product and engineering disagree on priorities weekly" (not "alignment friction")

**Use concrete business impact**:
- ✅ "Deployments take 4 hours and fail 30% of the time"
- ✅ "Feature delivery slows from 2 weeks to 3 months as team grows"
- ✅ "Production incidents require 5 teams to coordinate response"
- ✅ "Platform changes break 8 dependent teams every release"

**Describe systemic constraints plainly**:
- ✅ "Architecture decisions require 4 approval layers" (not "governance overhead")
- ✅ "Teams can't deploy without ops team manual intervention" (not "deployment friction")
- ✅ "Code review backlog averages 2 weeks" (not "review cycle inefficiency")
- ✅ "Platform team can't keep up with requests from 15 product teams" (not "platform capacity constraints")

### Test Your Language

Ask: **Would an engineering leader describe this problem using these exact words to their CEO?**

- If yes, keep it
- If no, rewrite in plain business language

Remember: Problem pages should sound like engineering post-mortems, not consulting diagnosis frameworks.

## Front Matter Requirements

```yaml
---
title: "Specific Problem Statement"
date: YYYY-MM-DD
description: "One sentence describing the problem's impact"
tags: ["relevant", "tags"]
categories: ["problems"]
---
```

## Red Flags

- Problem descriptions that are actually solution pitches
- Exaggerating severity to create urgency
- Using generic problems that apply to everyone and no one
- Ignoring context (company size, maturity, industry)
- Technical jargon that obscures the real problem
- "Agile transformation" language
- "ways of working" (prefer "systems of work" or "operating model")
- "mindset" problems (prefer "ethos" when culture is relevant)
- Hype or evangelism

The best problem pages make readers say "Yes, that's exactly what we're dealing with", not "Maybe we have that problem?"

## Language Rules

Use consistent, precise terminology when describing organisational design and work structures:

**Default term**: Use "systems of work" when describing processes, practices, funding flows, decision patterns, and governance mechanics.

**Executive context**: When addressing executives, boards, investors, or C-suite audiences, prefer "operating model" or "operating model hygiene" over "systems of work".

**Banned terms**: Never introduce or reintroduce "ways of working", "ways of work", or "mindset shifts" as preferred terms. These are vague and lack precision.

**Software systems**: If discussing software systems, technology architecture, or platforms, use explicit terms like "software systems", "technical architecture", or "platforms" to avoid ambiguity with "systems of work".

### Example Rewrites

**Before**: "Their ways of working create coordination bottlenecks and require mindset shifts."
**After**: "Their systems of work create coordination bottlenecks."

**Before**: "The organisation's ways of work slow decision-making."
**After**: "The organisation's systems of work slow decision-making."

**Executive context before**: "Your systems of work limit responsiveness."
**Executive context after**: "Your operating model limits responsiveness."

### Decision Rule

- If describing how work is designed to flow (processes, practices, governance, funding): use "systems of work".
- If speaking to executives about organisational design and constraints: use "operating model".
- If discussing software, platforms, or technical architecture: use explicit technical terms, not "systems".

````
