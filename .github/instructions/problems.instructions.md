---
applyTo:
  - site/content/problems/**
---

Problem pages define specific challenges that clients face. The focus is on clear problem articulation, not selling solutions.

## Content Requirements

Each problem page must:
- **Define the problem precisely**: What specifically goes wrong?
- **Explain why it matters**: What's the business impact?
- **Show what it looks like**: Concrete symptoms and scenarios
- **Indicate who faces this**: What types of organizations or teams?

Do NOT:
- Jump to solutions (that comes later)
- Use vague problem statements ("struggling with agility")
- Lead with fear, uncertainty, and doubt tactics
- Oversimplify complex problems

## Structure

1. **Problem statement**: One clear sentence (the page title)
2. **What this looks like**: 2-3 specific scenarios or symptoms
3. **Why it happens**: Root causes, not just surface issues
4. **The impact**: Business consequences (time, money, quality, morale)
5. **Who experiences this**: Company size, team structure, industry factors

## Writing Standards

- Be descriptive, not prescriptive. You're diagnosing, not solving.
- Use real examples. Change names, but keep scenarios authentic.
- Quantify impact when possible. "Teams spend 40% of sprint time fixing production issues."
- Avoid blame. Focus on systemic issues, not people failures.
- Link to related problems when relevant.

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

The best problem pages make readers say "Yes, that's exactly what we're dealing with" - not "Maybe we have that problem?"
