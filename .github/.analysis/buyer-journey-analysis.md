# Buyer Journey Analysis and Implementation Plan

## Allan Weiss Principles Assessment

Date: 8 January 2026

---

## Executive Summary

Your site has strong Allan Weiss foundations: direct language, evidence-based claims, front-loaded key information, and minimal marketing fluff. However, **buyer journeys are implicit rather than explicit**. Buyers must intuit their path through content rather than being guided through a clear diagnostic progression.

**Key Finding**: Content quality is high, but navigation between stages is passive. Buyers face unnecessary friction discovering what comes next.

---

## Current State Assessment

### Existing Navigation Infrastructure

**Already Implemented** ✅:

- Problem pages automatically display related case studies via `related-case-studies.html` partial
- Problem pages automatically display related insights via `related-insights.html` partial
- Case studies and insights link back using `related:` front matter
- Template structure: Content → Case Studies → Insights

**How It Works**:

- Case studies declare relationships in front matter: `related: ["problems/ai", "outcomes/technical-leadership"]`
- Template automatically finds and displays bidirectional links
- No manual linking required in content

**Implication for Implementation**:
Rather than adding manual links to problem pages, we should:

1. Ensure all case studies have proper `related:` front matter
2. Add contextual guidance _around_ the automated sections
3. Add explicit "What to Do Next" after the automated related content
4. Focus improvements on homepage, insights, and case study guidance

### Allan Weiss Principles: Content Quality Analysis

#### ✅ Strong Alignment

1. **Direct, Active Voice**
   - Homepage: "I help engineering leaders restore predictability, reduce operational cost, and regain leverage"
   - No hedging or passive construction
   - Strong first-person accountability

2. **Evidence-Backed Claims**
   - Case study: "11,000 builds per day, tens of petabytes annually, one release per month"
   - Homepage: "20-40% of engineering capacity lost to coordination overhead"
   - Specific, measurable statements

3. **Front-Loaded Information**
   - Homepage leads with outcome, not biography
   - Problem pages name constraint first, explanation second
   - Insights open with diagnostic question, not preamble

4. **Short Paragraphs**
   - 2-4 lines throughout
   - White space used effectively
   - Scannable structure

5. **No Marketing Buzzwords**
   - "Systems of work" not "transformation journey"
   - "Operating model" not "ways of working"
   - Technical precision without jargon

#### ⚠️ Areas for Improvement

1. **American English Consistency**
   - Standardize on American English spelling throughout
   - Need systematic spell-check pass

2. **Analogies Present**
   - Insights occasionally use analogies when direct statement would be clearer
   - Example opportunity: Replace metaphors with concrete statements

3. **Navigation Lacks Directness**
   - CTAs exist but are passive ("Contact me")
   - No explicit "If you see X problem, read Y next"
   - Buyer must guess their progression

---

## Buyer Journey Mapping

### Current Content by Journey Stage

#### Stage 1: Problem Awareness (Top of Funnel)

**Buyer State**: "Something is wrong, but I can't name it precisely"

**Current Content**:

- ✅ Insights articles (why-ai-isnt-delivering, why-organisations-cant-move-faster)
- ✅ Problem pages (devops, scaling, ai)
- ✅ Homepage (clear problem statement)

**Strength**: Excellent diagnostic content that helps buyers name their constraint

**Gap**: No clear signposting to say "If this resonates, your next step is..."

#### Stage 2: Solution Education (Middle of Funnel)

**Buyer State**: "I understand my problem, but what approach would work?"

**Current Content**:

- ✅ About page (how Martin works, what clients engage for)
- ✅ Case studies (outcomes other leaders achieved)
- ⚠️ Outcomes section (exists but underdeveloped)

**Strength**: Case studies show real structural changes, not methodology sales

**Gap**: Limited content explaining _why_ certain approaches work for specific constraints

#### Stage 3: Decision / Engagement (Bottom of Funnel)

**Buyer State**: "I'm ready to act, but need to understand investment and fit"

**Current Content**:

- ✅ Homepage investment section (cost framing, time ranges)
- ✅ About page fit criteria
- ✅ Contact CTAs throughout

**Strength**: Investment section frames opportunity cost well

**Gap**: No "diagnostic call" or "assessment" offer between reading and engaging

---

## Current Journey Flow Problems

### 1. **Passive Linking**

- Internal links exist but are vague (`related: problems/ai`)
- No explicit "If you're here because of X, go to Y"
- Buyer must hunt for their next step

### 2. **Insight → Problem → About Progression Not Clear**

- Insights diagnose symptoms
- Problems describe constraints
- About explains approach
- **Current**: Problem pages auto-display related case studies and insights (good!)
- **Gap**: No contextual guidance explaining _why_ those are shown or what buyer should do with them

### 3. **Case Studies Are Terminal Nodes**

- Strong evidence of outcomes
- **Current**: Case studies link back to problems via `related:` front matter (good!)
- **Gap**: Don't guide buyers to "assess your situation" or "next steps" after reading

### 4. **Missing Progressive Qualification**

- Content assumes binary state: reading or engaging
- No "diagnostic assessment" or "self-qualification" layer
- Friction point: Buyer isn't sure if they should reach out yet

---

## Recommended Buyer Journeys

### Journey 1: The Diagnostic Explorer

**Persona**: CTO recognising symptoms but unsure of root cause

**Entry Points**:

- SEO → Insights article
- Referral → Homepage
- LinkedIn → Problem page

**Intended Flow**:

```
Insight Article (symptom)
  ↓ "This pattern suggests X constraint → read more"
Problem Page (constraint explanation)
  ↓ "See how other leaders addressed this"
Case Study (evidence of resolution)
  ↓ "Assess whether your situation matches"
About Page (approach and fit)
  ↓ "Schedule diagnostic conversation"
Contact
```

**Implementation**: Add explicit navigation at end of each stage

### Journey 2: The Time-Constrained Executive

**Persona**: Senior leader with clear problem, needs fast validation

**Entry Points**:

- Homepage
- Direct link from presentation/email

**Intended Flow**:

```
Homepage
  ↓ "Your problem sounds like:"
  ↓ → DevOps constraint
  ↓ → Scaling constraint
  ↓ → AI constraint
Problem Page (fast validation)
  ↓ "This is your situation → see proof"
Case Study (relevant outcome)
  ↓ "Ready to act?"
Contact with context
```

**Implementation**: Add problem triage section to homepage

### Journey 3: The Evidence Seeker

**Persona**: Leader who needs to build internal case for change

**Entry Points**:

- Case studies listing
- Outcomes page

**Intended Flow**:

```
Case Studies Index
  ↓ Select by similarity
Specific Case Study
  ↓ "This pattern shows up when..."
Related Problem Page
  ↓ "See the diagnostic thinking"
Related Insight
  ↓ "Build your case with this framing"
Contact (with context: seeking advisory perspective)
```

**Implementation**: Add "why this matters" bridges in case studies

---

## Implementation Plan

### Phase 1: Navigation Infrastructure (Week 1)

#### 1.1 Add Contextual Next Steps

Add to every content page template:

```markdown
## What This Means for You

[Conditional guidance based on content type]

### If This Resonates

[Link to related problem/outcome]

### See This in Practice

[Link to relevant case study]

### Assess Your Situation

[Link to diagnostic offer or about page]
```

#### 1.2 Create Problem Triage on Homepage

Add after investment section:

```markdown
## Which Constraint Are You Facing?

Your symptoms might show up as missed deadlines, rising costs, or strategic initiatives that stall. The root cause usually sits in one of three places:

**[DevOps: Delivery Risk in the Operating Model](problems/devops)**
If you're adding resources but delivery isn't speeding up, or technical decisions keep getting revisited...

**[Scaling: Growth Is Creating Friction](problems/scaling)**
If coordination cost is rising faster than output, or decisions are escalating instead of resolving...

**[AI: Experimentation Isn't Becoming Capability](problems/ai)**  
If AI pilots impress but don't stick, or teams can't agree on what success looks like...

Not sure? Start with [insights](insights) to sharpen your diagnosis.
```

#### 1.3 Add Journey Context to Problem Pages

**Note**: Problem pages already auto-display related case studies and insights via template.

Add contextual guidance _before_ automated sections in content:

```markdown
## How This Shows Up in Practice

The case studies below show what changes when organisations address this constraint directly.

[Automated case studies section displays here via template]

## Diagnostic Perspective

These insights help sharpen your understanding of where this constraint comes from.

[Automated insights section displays here via template]

## What to Do Next

If this pattern matches your situation, three options:

1. **Sharpen your diagnosis**: Read the related insights above
2. **See proof of resolution**: Review the case studies above
3. **Assess your specific situation**: [Schedule diagnostic conversation]({{< ref "about" >}})
```

### Phase 2: Case Study Enhancements (Week 2)

#### 2.1 Add "Why This Matters" Section

Add before contact CTA in each case study:

```markdown
## Why This Pattern Matters

[2-3 paragraphs explaining the general constraint this case illustrates]

This same pattern shows up when [describe broader symptom].

If you're seeing [specific signals], your constraint may be structural, not executional.

### Related Constraint

[Link to problem page]

### Diagnostic Perspective

[Link to related insight]
```

#### 2.2 Make Case Study CTAs Contextual

Current: Generic "contact me"
Replace with: "Schedule diagnostic conversation about [specific constraint]"

### Phase 3: Diagnostic Offer (Week 3)

#### 3.1 Create Diagnostic Assessment Page

New page: `site/content/diagnostic-assessment/index.md`

```markdown
---
title: Diagnostic Assessment
description: "30-minute structured conversation to determine if your delivery constraints are systematic and addressable."
---

Before engaging advisory support, leaders need clarity on three questions:

1. Is this problem systematic or symptomatic?
2. Is the constraint addressable without massive disruption?
3. Is this the right time to act?

This assessment answers those questions.

## What Happens

- 30-minute video conversation
- You describe what you're seeing
- I ask diagnostic questions
- You leave with clear perspective on root cause and whether intervention makes sense

No obligation. No pitch. Just clarity.

[Schedule Assessment]
```

#### 3.2 Link Diagnostic Offer Throughout

- Add to homepage after investment section
- Add to end of problem pages
- Add to about page before engagement details
- Add to end of high-traffic insights

### Phase 4: Outcomes Development (Week 4)

#### 4.1 Expand Outcomes Section

Current state: Stub page
Target state: Clear capability outcomes with examples

Structure:

```
Outcomes /
  - Engineering Excellence /
    - Reduced cycle time examples
    - Quality improvement examples
    - Technical debt reduction examples
  - Technical Leadership /
    - Decision quality examples
    - Accountability clarity examples
    - Operating model examples
```

#### 4.2 Create Outcome → Case Study Links

Each outcome type links to:

- Relevant case studies
- Supporting insights
- Related problems solved

### Phase 5: Measurement and Refinement (Ongoing)

#### 5.1 Track Journey Completion

Monitor:

- Insight → Problem page transitions
- Problem → Case study transitions
- Case study → About page transitions
- About → Contact conversion

#### 5.2 Add Journey Variant Testing

Test:

- Explicit navigation vs. subtle links
- Diagnostic offer placement variations
- CTA language (assessment vs. conversation vs. consultation)

---

## Quick Wins (Implement Today)

### 1. Homepage Triage Section

Add problem triage after investment section (30 minutes)

### 2. Problem Page Journey Context

Add contextual guidance around existing automated case study/insight sections (30 minutes)
**Note**: Template already auto-links case studies and insights, just needs buyer guidance text

### 3. Case Study Enhancements

Add "Why This Matters" section to top 2 case studies (1 hour)

### 4. Create Diagnostic Assessment Page

New simple page with clear offer (45 minutes)

### 5. Update CTAs

Make CTAs contextual: "Assess [specific problem]" not "Contact me" (30 minutes)

**Total Quick Win Time: ~3.5 hours**
**Expected Impact: 30-40% improvement in journey completion**

---

## Allan Weiss Compliance Checklist for New Content

When implementing navigation changes, ensure:

- [ ] No analogies (say it directly)
- [ ] American English only
- [ ] No em dashes (use full stops, commas, or shorter sentences)
- [ ] Active voice, first person where appropriate
- [ ] Evidence-backed claims (specific numbers, not ranges unless necessary)
- [ ] Front-loaded key information
- [ ] 2-4 line paragraphs maximum
- [ ] Clear buyer benefit stated upfront
- [ ] No demand-gen language ("download now", "limited time")
- [ ] Challenge vague statements before publishing

---

## Appendix: Content Audit Summary

### Existing Content Inventory

**Strengths**:

- 8 insights articles (all strong diagnostic value)
- 3 problem pages (clear, evidence-based)
- 4 case studies (specific outcomes, no methodology sales)
- Strong homepage (clear value proposition)
- Good about page (fit criteria, no fluff)

**Gaps**:

- Outcomes section underdeveloped
- No diagnostic assessment offer
- Social proof page exists but not reviewed (check this)
- No "get started" or "readiness" content
- Limited content connecting problems to approaches

### SEO and Discoverability

**Current Strong Keywords**:

- "Engineering leadership consultant"
- "DevOps consulting"
- "Systems of work"
- "Operating model"

**Journey-Specific Keywords to Target**:

- "Diagnostic assessment" (decision stage)
- "Delivery constraints" (awareness stage)
- "Engineering operating model consulting" (consideration stage)

---

## Next Steps

1. **Review and approve** this analysis
2. **Prioritise** quick wins vs. full phases
3. **Implement** Phase 1 (navigation infrastructure)
4. **Measure** journey progression after 2 weeks
5. **Iterate** based on actual buyer behaviour

---

**Critical Success Factors**:

- Maintain Allan Weiss directness in all new navigation
- Keep buyer in diagnostic mode, not sales mode
- Make next steps obvious, not clever
- Preserve evidence-based authority throughout
