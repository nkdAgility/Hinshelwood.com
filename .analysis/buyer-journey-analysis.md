# Buyer Journey Analysis and Implementation Plan

## Allan Weiss Principles Assessment

Date: 8 January 2026  
**Updated**: 8 January 2026 - Post-Implementation Review

---

## Executive Summary

Your site has strong Allan Weiss foundations: direct language, evidence-based claims, front-loaded key information, and minimal marketing fluff. **Buyer journeys have been made explicit** through structured navigation, diagnostic displays, and contextual guidance.

**Key Finding**: Core navigation infrastructure is complete. Content pages have journey guidance. Templates are basic but functional. Next phase focuses on template enhancement and insights/outcomes content completion.

---

## Implementation Status Review: What Buyers Actually See

**Assessment Method**: Reviewed rendered HTML in `/public/` folder to evaluate complete buyer experience (content + templates).

### ✅ COMPLETE BUYER JOURNEYS

**Problem Pages** (e.g., /problems/devops/):

- ✅ Full diagnostic content with constraint explanation
- ✅ Structured related case studies section with evidence display: "How This Shows Up in Practice"
- ✅ Related insights section: "Diagnostic Perspective" (currently empty but infrastructure present)
- ✅ Related outcomes section with capability statements: "What Changes When This Gets Fixed"
- ✅ "What to Do Next" section with three clear options
- ✅ Contextual diagnostic conversation CTA
- **Buyer sees complete journey**: Problem → Evidence → Capabilities → Next Steps

**Case Study Pages** (e.g., /case-studies/restoring-delivery-visibility...):

- ✅ Constraint → Outcome → Evidence structure visible
- ✅ "What to Do Next" section with three navigation options
- ✅ Links back to related problems and outcomes
- ✅ Contextual diagnostic conversation CTA specific to constraint
- **Buyer sees complete journey**: Evidence → Constraint → Capabilities → Next Steps

**Outcomes Pages** (e.g., /outcomes/engineering-excellence/):

- ✅ Capability statement and impact description
- ✅ Related case studies displayed as cards with images
- ✅ Related insights section (template present, awaiting content connections)
- ✅ Contextual diagnostic conversation CTA
- ✅ **"What to Do Next" sections added with three clear navigation options**
- **Buyer sees complete journey**: Capability → Evidence → Related Constraints → Next Steps

**Homepage** (/):

- ✅ Clear value proposition
- ✅ Problem triage section implemented
- ✅ Investment/cost framing
- ✅ Client logos
- ✅ Contact CTA
- **Buyer sees complete entry journey**: Value → Problems → Investment → Action

### ⚠️ PARTIAL: Insights Pages

**Current State** (e.g., /insights/why-ai-is-making-delivery-harder/):

- ✅ Strong diagnostic content
- ✅ Contextual diagnostic conversation CTA
- ❌ No "What to Do Next" section
- ❌ No related problems section visible
- ❌ No related case studies section visible
- ❌ No related outcomes section visible
- **Buyer sees**: Diagnostic content → CTA (journey stops, no onward navigation except CTA)

**Impact**: Insights are currently **terminal nodes**. Buyers reading insights cannot easily progress to:

- Problem pages (to understand constraint)
- Case studies (to see evidence)
- Outcomes (to see what changes)

### ❌ NOT STARTED

**Diagnostic Assessment Page**:

- No dedicated `/diagnostic-assessment/` page
- All CTAs link directly to calendar booking
- **Missing**: Self-qualification content, readiness signals, what to expect

---

## Priority Actions Based on Rendered Output

### IMMEDIATE (Fixes Critical Journey Break)

**1. Fix Insights Template to Add Journey Navigation**

**Why**: Insights are currently terminal nodes with no onward journey. The template (`insights/single.html`) only renders content + CTA, missing all related content sections that Problem and Outcomes pages have.

**Action**: Update `site/layouts/insights/single.html` to match the journey structure:

- Add related problems section (to understand constraint)
- Add related case studies section (to see evidence)
- Add related outcomes section (to see what changes)
- Add "What to Do Next" section in template or add to each insight's content

**Impact**: Converts insights from dead-ends into journey entry points. Buyers can progress from symptom → constraint → evidence → outcome.

**Estimated time**: 1 hour template work + content review

---

### HIGH PRIORITY (Completes Journey Infrastructure)

**2. Add "What to Do Next" Sections to Insights Content**

Once template displays related content, add explicit guidance in each insight explaining how to use the related sections.

**3. ~~Add "What to Do Next" to Outcomes Pages~~** ✅ **COMPLETED**

Both outcomes pages now have "What to Do Next" sections that:

- Guide buyers to review related case studies above
- Link to relevant problem pages to understand constraints
- Offer diagnostic conversation for specific situation assessment

**4. Create Diagnostic Assessment Landing Page**

Create `/diagnostic-assessment/` page that explains:

- What happens in the conversation
- Who it's for (self-qualification)
- What you'll leave with (clarity, not pitch)
- Links to booking

This gives buyers a "decision page" between reading and engaging.

---

### MEDIUM PRIORITY (Enriches Journey)

**5. Connect Insights to Problems via Front Matter**

Review insights and ensure `related:` front matter connects to relevant problems. Currently problem pages expect insights to link to them, but insights don't have onward navigation.

**6. Review Empty Related Sections**

Some problem pages have empty "related-insights" sections (shortcode renders but no content). Either:

- Add insight connections via front matter
- Remove empty sections from display

---

## What's Working Well (Don't Change)

1. **Problem pages are excellent** - Full journey visible, clear navigation, evidence displayed, outcomes shown, next steps explicit
2. **Case studies are excellent** - Complete constraint → outcome → evidence pattern, clear next steps, contextual CTAs
3. **Outcomes display well** - Case studies shown as visual cards, capability statements clear
4. **CTAs are contextual** - Not generic "contact me" but specific "Assess whether [constraint] is preventing [outcome]"
5. **Homepage triage works** - Problem selection visible and clear

---

## Current State Assessment

### Existing Navigation Infrastructure

**Implemented** ✅:

- Problem pages automatically display related case studies via `related-case-studies.html` shortcode
- Problem pages automatically display related insights via `related-insights.html` shortcode
- Problem pages automatically display related outcomes via `related-outcomes.html` shortcode
- Case studies, insights, and outcomes link back using `related:` front matter
- Template structure: Content → Case Studies → Insights → Outcomes → What to Do Next
- Reusable `get-related-items.html` function filters related content by section
- All case studies use consistent `diagnosis:` front matter (constraint, outcome, evidence)
- All insights use `diagnosis:` front matter (question, statement, reason, signal)
- All outcomes use `diagnosis:` front matter (capability, impact, signal)
- Problems use `triage:` front matter (title, signal)

**How It Works**:

- Content declares relationships in front matter: `related: ["problems/ai", "outcomes/technical-leadership"]`
- Shortcodes automatically find and display bidirectional links using get-related-items function
- No manual linking required in content
- Allan Weiss-style displays: evidence-based for case studies, diagnostic for insights, capability-oriented for outcomes

**Journey Enhancements Completed**:

1. ✅ All case studies have proper `related:` front matter and consistent `diagnosis:` fields
2. ✅ Contextual guidance added around automated sections on problem pages
3. ✅ Explicit "What to Do Next" sections added to all problem pages
4. ✅ Homepage triage section implemented with `problem-constraints` shortcode
5. ✅ Problems list page uses diagnostic display with triage signals
6. ✅ Outcomes list page uses capability display with diagnosis data
7. ✅ Both list pages have journey context (top intro + bottom navigation guidance)

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

1. **Analogies Present**
   - Insights occasionally use analogies when direct statement would be clearer
   - Example opportunity: Replace metaphors with concrete statements

#### ✅ Recently Completed

1. **American English Consistency** ✅
   - Standardized on American English spelling throughout
   - Systematic spell-check completed

2. **Navigation Directness** ✅
   - Explicit "What to Do Next" sections added
   - Clear buyer journey signposting implemented
   - CTAs now contextual and diagnostic

---

## Buyer Journey Mapping

### Current Content by Journey Stage

#### Stage 1: Problem Awareness (Top of Funnel)

**Buyer State**: "Something is wrong, but I can't name it precisely"
Status**: ✅ **IMPLEMENTED** - Problem pages now include "What to Do Next" sections with clear signposting
**Current Content\*\*:

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

**Status**: ✅ **OUTCOMES ENHANCED** - Outcomes pages now display capability statements with evidence signals. Case studies show constraint → outcome → evidence pattern.

#### Stage 3: Decision / Engagement (Bottom of Funnel)

**Buyer State**: "I'm ready to act, but need to understand investment and fit"

**Current Content**:

- ✅ Homepage investment section (cost framing, time ranges)
- ✅ About page fit criteria
- ✅ Contact CTAs throughout

**Strength**: Investment section frames opportunity cost well

**Status**: ⚠️ **PARTIAL** - Diagnostic conversation CTAs added to problem pages. Dedicated diagnostic assessment page not yet created.

---

## Current Journey Flow Problems

### 1. **Passive Linking** ✅ RESOLVED

- ✅ Shortcodes automatically display related content with contextual headings
- ✅ "What to Do Next" sections provide explicit guidance
- ✅ Problem pages include triage → case studies → insights → outcomes flow

### 2. **Insight → Problem → About Progression Not Clear** ✅ RESOLVED

- ✅ Problem pages have contextual guidance before each automated section
- ✅ Case studies display with "How This Shows Up in Practice" heading
- ✅ Insights display with "Diagnostic Perspective" heading
- ✅ Outcomes display with "What Changes When This Gets Fixed" heading
- ✅ "What to Do Next" explicitly states: sharpen diagnosis, see proof, assess situation

### 3. **Case Studies Are Terminal Nodes** ✅ RESOLVED

- ✅ Case studies link back to problems via `related:` front matter
- ✅ Individual case study pages now have "What to Do Next" sections
- ✅ Contextual CTAs guide buyers to understand constraints, explore outcomes, and schedule diagnostic conversations

### 4. **Missing Progressive Qualification** ⚠️ PARTIAL

- ✅ Diagnostic conversation CTAs added to problem pages
- ✅ List pages provide journey context and next steps
- ⚠️ No dedicated diagnostic assessment landing page
- ⚠️ No self-qualification checklist or readiness content

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

#### 2.1 Add "Why This Matters" Section (NOT STARTED)

Add before contact CTA in each case study to explain the general constraint pattern.

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

#### 2.2 Make Case Study CTAs Contextual (NOT STARTED)

Replace generic "contact me" with constraint-specific CTAs like "Schedule diagnostic conversation about [specific constraint]".

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
✅ COMPLETED

### 2. Problem Page Journey Context

Add contextual guidance around existing automated case study/insight sections (30 minutes)
**Note**: Template already auto-links case studies and insights, just needs buyer guidance text

### 3. Case Study Enhancements

Add "Why This Matters" section to top 2 case studies (1 hour)

### 4. Create Diagnostic Assessment Page

New simple page with clear offer (45 minutes)

### 5. Update CTAs

Make CTAs contextual: "Assess [specific problem]" not "Contact me" (30 minutes)

### Additional Infrastructure Implemented ✅

**Shortcodes Created**:

- `related-case-studies.html` - Allan Weiss evidence display (constraint → outcome → evidence)
- `related-insights.html` - Diagnostic display (statement → reason → signal)
- `related-outcomes.html` - Capability display (capability → impact → signal)
- `problem-constraints.html` - Dynamic homepage triage
- `client-logos.html` - Flexible client showcase

**Partials Created**:

- `functions/get-related-items.html` - Reusable content filtering function

**Front Matter Standardization**:

- All case studies: `diagnosis: {constraint, outcome, evidence}`
- All insights: `diagnosis: {question, statement, reason, signal}`
- All outcomes: `diagnosis: {capability, impact, signal}`
- All problems: `triage: {title, signal}`

**List Page Enhancements**:

- Problems list: Diagnostic checklist format with journey context
- Outcomes list: Capability-oriented format with journey context
- Both include top/bottom navigation guidance

**Total Implementation Time: ~4 hours**
**Infrastructure Gain: Reusable, maintainable, Allan Weiss compliant**

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

### Completed ✅

1. ✅ Quick Win #1: Homepage problem triage
2. ✅ Quick Win #2: Problem page journey context
3. ✅ Infrastructure: Shortcodes, functions, front matter standardization
4. ✅ List pages: Diagnostic displays with journey context
5. ✅ Outcomes integration: Related outcomes on problem pages

### Remaining Work

#### Phase 2: Case Study Enhancements (Completed ✅)

- ✅ Add "What to Do Next" sections to case study pages
- ✅ Link case studies to related problems explicitly
- ✅ Add contextual CTAs with constraint-specific diagnostic conversation offers

**Status**: All four case studies now include "What to Do Next" sections that guide buyers to understand broader constraints, explore related outcomes, and assess their specific situation.

#### Phase 3: Diagnostic Assessment (Not Started)

- Create dedicated diagnostic assessment landing page
- Add self-qualification checklist
- Create readiness content

#### Phase 4: Insights Enhancement (Not Started)

- Add "What to Do Next" to insight pages
- Link insights to related problems explicitly
- Add diagnostic framework explanation

### Measurement and Iteration

1. **Measure** journey progression after 2 weeks
2. **Track** problem page → case study → contact flow
3. **Iterate** based on actual buyer behavior
4. **Validate** that outcomes display correctly on all problem pages

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

## Next Steps (Updated Based on Rendered Site Review)

### Immediate Action: Fix Insights Journey

**Problem**: Insights are terminal nodes. Buyers land on diagnostic content but have nowhere to go except a CTA.

**Solution**: Update `/site/layouts/insights/single.html` to add:

1. Related problems section (like outcomes template has)
2. Related case studies section (like outcomes template has)
3. Related outcomes section (like outcomes template has)
4. Consider adding "What to Do Next" in template

**Reference template**: `/site/layouts/outcomes/single.html` (already has partials structure)

---

### High Priority: Complete Journey Guidance

1. **Add "What to Do Next" to all insights** (content layer, 8 files)
2. ~~**Add "What to Do Next" to outcomes**~~ ✅ **COMPLETED** (content layer, 2 files)
3. **Create diagnostic assessment page** (new page)
4. **Review and connect insights to problems** (front matter updates)

---

### Validation Checklist

Before considering buyer journey complete, verify in `/public/`:

- [ ] Insights pages display related problems, case studies, and outcomes
- [ ] All insights have explicit "What to Do Next" guidance
- [ ] All outcomes have explicit "What to Do Next" guidance
- [ ] Diagnostic assessment page exists and is linked from key points
- [ ] No empty "related" sections render (or they gracefully hide)
- [ ] Each content type can progress to at least two other types

---

### Success Criteria

**A complete buyer journey means**:

- Buyer can enter anywhere (insight, problem, case study, homepage) and navigate to decision point
- No content type is a dead end
- Next steps are always clear and contextual
- Evidence and capability are always one click away from any starting point

**Current state**: 80% there. Problem pages and case studies are excellent. Insights are the critical gap.

---

**Critical Success Factors**:

- Maintain Allan Weiss directness in all new navigation
- Keep buyer in diagnostic mode, not sales mode
- Make next steps obvious, not clever
- Preserve evidence-based authority throughout
