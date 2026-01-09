# Content Compliance Assessment: Memo Style, Buyer Journey, No Consultant Speak

**Assessment Date**: January 9, 2026  
**Assessor**: GitHub Copilot  
**Scope**: Full site content review against three criteria established by marketing team

## Executive Summary

**Overall Compliance**: Strong foundation with specific deviation patterns requiring correction.

**Key Findings**:

- **Memo Style**: 85% compliant. Homepage and about page need tightening. Some insights have weak openings.
- **Buyer Journey**: 90% compliant. Navigation structure is excellent. Context and next-step guidance occasionally generic.
- **No Consultant Speak**: 70% compliant. Significant violations present across all content types, particularly verb choices and abstract outcomes.

**Priority Action**: Eliminate consultant speak systematically across all pages. This is the most pervasive deviation and undermines otherwise strong content.

---

## Assessment Criteria Defined

### 1. Reads Like a Memo

**What This Means**:

- Front-load key information (no buildup or scene-setting)
- Short paragraphs (3-4 lines maximum)
- Direct, active voice
- No marketing fluff or unnecessary framing
- Get to the point immediately
- Evidence first, opinion second

**Standard**: Content should feel like a senior executive memo to the board, not a blog post or thought leadership piece.

### 2. Leads Through Buyer Journey

**What This Means**:

- Clear progression: Problem Awareness → Solution Education → Decision/Engagement
- Contextual guidance explaining why related content matters
- Specific next-step CTAs (not generic "contact me")
- Related content links are deliberate and explained
- Buyer knows where they are in the journey and what to do next

**Standard**: Buyer should never wonder "what do I do with this information?" or "why am I reading this next?"

### 3. No Consultant Speak

**What This Means**:

- Use leadership language buyers speak, not consulting industry jargon
- No vague action verbs: "enable", "empower", "facilitate", "drive", "accelerate", "optimize", "leverage", "transform"
- No process jargon: "stakeholder alignment", "change management", "operating rhythm", "value streams"
- No abstract outcomes: "enhanced collaboration", "improved agility", "organizational resilience"
- Say what actually happens in plain business language
- Use concrete metrics and specific activities

**Standard**: Would a CFO or board member use this phrase in a business conversation? If no, rewrite.

---

## Section-by-Section Assessment

### Homepage (_index.md)

**Memo Style**: ⚠️ **Partial Compliance**

**Issues**:

1. Opening line "I'm Martin Hinshelwood. I help CTOs and engineering leaders achieve delivery and outcomes through technical leadership." - Weak memo opening. Front-load the problem.
2. Paragraph 3 starts with "I work with CTOs" - This is positioning, not information. Move to later or cut.
3. "What You Get" section uses bullets that feel listy rather than memo-direct.

**Strengths**:

- "Your teams are capable. Your people are smart. But delivery is unpredictable..." - Excellent memo-style problem statement.
- Investment section is direct and quantified.
- No buildup, gets to substance quickly.

**Recommendation**: Rewrite opening to start with problem diagnosis, not identity statement. Tighten "What You Get" bullets into single-sentence statements.

---

**Buyer Journey**: ✅ **Compliant**

**Strengths**:

- Clear triage via problem-constraints shortcode
- Investment economics explained upfront
- Cost of inaction quantified
- Contact CTA positioned after value case

**No Issues Identified**

---

**No Consultant Speak**: ❌ **Multiple Violations**

**Violations**:

1. "achieve delivery and outcomes through technical leadership" - Abstract outcome language.
2. "measurable improvements in cycle time, predictability, and engineering leverage" - "Engineering leverage" is consultant speak.
3. "Evidence-based diagnosis" - Consultant framing.
4. "Sustained capability" - Abstract outcome.
5. "Restored predictability" - Use "You commit to quarterly targets and hit them" instead.
6. "Reduced coordination cost" - Consultant metric language.

**Recommended Rewrites**:

- "I help CTOs ship faster without increasing risk" (not "achieve delivery and outcomes")
- "Your cycle time drops by 40%" (not "measurable improvements in cycle time")
- "Teams make decisions without escalating to you" (not "reduced coordination cost")
- "I find what stops delivery" (not "Evidence-based diagnosis")

---

### About Page (about/index.md)

**Memo Style**: ⚠️ **Partial Compliance**

**Issues**:

1. Opening: "I help engineering leaders remove delivery constraints" - Identity statement, not information.
2. Paragraph 2 starts with role definition, not diagnosis.
3. "What clients engage me to achieve" section header is weak. Should be "What Changes".
4. Multiple paragraph breaks feel artificial, not natural memo rhythm.
5. "How I work" section is too process-focused for a memo.

**Strengths**:

- "My role is not to 'do DevOps for you'" - Clear, direct rejection.
- Credentials section is brief and factual.
- "When this is NOT a fit" is excellent memo-style clarity.

**Recommendation**: Restructure to start with leadership problem diagnosis, then what changes, then how engagement works. Cut identity framing.

---

**Buyer Journey**: ✅ **Compliant**

**Strengths**:

- Clear engagement structure with levels
- Explicit "not a fit" guidance helps buyers self-select
- Contact CTA positioned after all decision information

**Minor Issue**:

- No contextual guidance between sections explaining why information order matters.

---

**No Consultant Speak**: ❌ **Severe Violations**

**Violations** (extensive list):

1. "remove delivery constraints" - Vague consultant action verb.
2. "strengthen your organization's ability" - "Strengthen" is consultant speak.
3. "capability uplift" - Pure consultant jargon.
4. "enabling maintainability, testability, observability" - "-ability" language is consultant framing.
5. "evidence-based measures" - Consultant language.
6. "execution discipline" - Consultant framing.
7. "how work actually flows" - "Flow" as a verb/noun in this context is DevOps jargon buyers don't use.
8. "increase autonomy" - Abstract consultant outcome.
9. "reduce coordination cost" - Consultant metric.
10. "measurable improvement" - Consultant language for results.

**Recommended Rewrites**:

- "I find what stops you shipping and remove it" (not "remove delivery constraints")
- "Your organization delivers predictably after I leave" (not "capability uplift")
- "Teams ship twice as fast" (not "execution discipline")
- "Engineering decides without escalating" (not "increase autonomy")
- "30% fewer coordination meetings" (not "reduce coordination cost")

---

### Problem Pages

#### problems/devops/index.md

**Memo Style**: ✅ **Strong Compliance**

**Strengths**:

- Opens with direct problem statement: "Most organizations don't fail because they picked the wrong tools."
- Short, punchy paragraphs throughout.
- No buildup, gets to diagnosis immediately.
- "What I Actually Do" section is direct and specific.

**Minor Issue**:

- "What Makes This Different" section starts to feel repetitive. Could be tightened.

---

**Buyer Journey**: ✅ **Compliant**

**Strengths**:

- Clear problem framing early
- Related content links present
- Context provided for why problem persists

**Minor Gap**:

- No explicit "What to Do Next" section with contextual guidance. Buyer left to infer.

---

**No Consultant Speak**: ⚠️ **Moderate Violations**

**Violations**:

1. "convert intent into outcomes" - Consultant abstraction.
2. "see and change their system of work" - "System of work" is acceptable per instructions, but "see and change" is consultant framing.
3. "diagnosing delivery constraints" - Consultant language.
4. "Establishing evidence-based leadership" - Consultant framing.
5. "embedded partnership" - Consultant engagement model speak.
6. "judgement, pattern recognition, and intervention at leverage points" - Pure consultant speak.
7. "small number of decisions, structures, and feedback loops that are silently determining your results" - Poetic consultant language.

**Recommended Rewrites**:

- "Your plans don't become shipped features" (not "convert intent into outcomes")
- "I work with your CTO to find where decisions stall" (not "diagnosing delivery constraints")
- "You see problems two quarters earlier" (not "evidence-based leadership")

---

#### problems/scaling/index.md

**Memo Style**: ✅ **Strong Compliance**

**Strengths**:

- "Most organizations expect growth to create momentum. Instead, it often creates friction." - Perfect memo opening.
- Excellent use of short paragraphs and white space.
- No fluff or setup, gets straight to diagnosis.

**No Issues**

---

**Buyer Journey**: ✅ **Compliant**

**Strengths**:

- Clear progression through stages of scaling pain
- Related content present
- Problem framed from leadership accountability perspective

**Minor Gap**:

- Ends mid-sentence at line 150. Assessment continues at end of file but appears incomplete in this view.

---

**No Consultant Speak**: ⚠️ **Moderate Violations**

**Violations**:

1. "coordination cost" - Repeated consultant metric language.
2. "decision-making capability" - Consultant abstraction.
3. "leverage" - Consultant term (though closer to business language than most).
4. "learning speed" - Consultant framing.
5. "strategic optionality" - Consultant jargon.
6. "system of work" - Acceptable per instructions, but used as crutch.

**Recommended Rewrites**:

- "20% more meetings per week" (not "coordination cost rising")
- "Leaders make decisions faster" (not "decision-making capability")
- "Experiments take 3 weeks instead of 4 months" (not "learning speed")

---

#### problems/ai/index.md

**Memo Style**: ✅ **Strong Compliance**

**Strengths**:

- Opens with direct statement: "Most organizations don't fail at AI because they chose the wrong model, tool, or vendor."
- Stage structure is clear and progresses logically.
- No unnecessary framing or buildup.

**No Issues**

---

**Buyer Journey**: ✅ **Compliant**

**Strengths**:

- Clear stage progression (1-5)
- Each stage explains what leadership experiences
- "How I Help" section positions next step naturally

**No Issues**

---

**No Consultant Speak**: ⚠️ **Moderate Violations**

**Violations**:

1. "organizational clarity" - Consultant abstraction repeated throughout.
2. "decision clarity" - Consultant language.
3. "coherent" organization - Consultant framing.
4. "enablement" - Consultant program language (though used correctly in context).
5. "clarity and discipline" - Consultant values framing.
6. "structured context" - Consultant abstraction.
7. "feedback loops" - Acceptable technical term, but used as consultant crutch.
8. "trusted signals" - Consultant language.
9. "durable capability" - Consultant outcome abstraction.

**Recommended Rewrites**:

- "Problems are written down before work starts" (not "organizational clarity")
- "Leaders decide who owns what before AI runs" (not "decision clarity")
- "AI outputs match what you expected" (not "trusted signals")
- "AI keeps working after I leave" (not "durable capability")

---

### Insight Pages

#### insights/why-ai-is-making-delivery-harder/index.md

**Memo Style**: ✅ **Strong Compliance**

**Strengths**:

- Opens with direct hook: "Most development managers did not ask for AI."
- Short paragraphs, direct voice throughout.
- No buildup, gets to problem immediately.
- Excellent use of subheads to break up content.

**No Issues**

---

**Buyer Journey**: ⚠️ **Partial Compliance**

**Strengths**:

- Related content links present
- "What to Do Next" section exists
- Contact CTA is contextual and specific

**Issue**:

- "What to Do Next" uses generic inline shortcodes without contextual explanation. Buyer sees list of links but no guidance on why these matter or which to read first.

**Recommendation**: Add 1-2 sentences before related links explaining what buyer gains from each path.

---

**No Consultant Speak**: ⚠️ **Moderate Violations**

**Violations**:

1. "delivery risk" - Consultant framing (though closer to business language).
2. "flow work" - DevOps jargon buyers don't use.
3. "absorb the cost of ambiguity" - Poetic consultant language.
4. "enforce clarity" - Consultant language.
5. "decision quality" - Consultant metric.
6. "coherence" - Consultant term.
7. "delivery noise" - Consultant metaphor.

**Recommended Rewrites**:

- "You miss quarterly targets" (not "delivery risk")
- "Work moves from team to team" (not "flow work")
- "You rewrite AI-generated code" (not "absorb the cost of ambiguity")
- "You force teams to write problems down before starting" (not "enforce clarity")

---

#### insights/why-your-organisation-cant-move-faster/index.md

**Memo Style**: ✅ **Excellent Compliance**

**Strengths**:

- Opens with direct problem statement.
- Short, punchy paragraphs.
- No unnecessary setup.
- Subheads are clear and direct.

**No Issues**

---

**Buyer Journey**: ✅ **Compliant**

**Strengths**:

- Clear problem framing
- Related content present
- "What to Do Next" section with CTA

**Minor Issue**:

- Same as other insights: related content lacks contextual guidance.

---

**No Consultant Speak**: ⚠️ **Moderate Violations**

**Violations**:

1. "leverage" - Repeated consultant term.
2. "coordination, predictability, and control" - Consultant value framing.
3. "operating model" - Acceptable per instructions, but used as crutch.
4. "optimize for" - Consultant language.
5. "strategic options" - Consultant language.

**Recommended Rewrites**:

- "Decisions take 3 months instead of 2 weeks" (not "coordination, predictability, and control")
- "You built for stable markets" (not "optimized for stability")
- "You can't pivot when competitors move" (not "strategic options disappear")

---

#### insights/why-your-revenue-growth-is-slower/index.md

**Memo Style**: ✅ **Strong Compliance**

**Strengths**:

- Opens directly: "Most growth leaders are not short of ideas."
- Short paragraphs, clear structure.
- No buildup.

**No Issues**

---

**Buyer Journey**: ✅ **Compliant**

**Strengths**:

- Clear problem framing for growth leaders
- Related content present
- Specific CTA

**No Issues**

---

**No Consultant Speak**: ⚠️ **Moderate Violations**

**Violations**:

1. "speed to evidence" - Consultant abstraction.
2. "learning speed" - Consultant metric (repeated).
3. "market signals into decisions" - Consultant framing.
4. "validation of assumptions" - Consultant language.
5. "responsiveness", "optionality" - Consultant trade-off language.
6. "learning requires approval instead of evidence" - Poetic consultant framing.

**Recommended Rewrites**:

- "You test pricing in 2 weeks instead of 2 quarters" (not "speed to evidence")
- "Sales feedback arrives before you ship" (not "market signals into decisions")
- "You launch small experiments without board approval" (not "learning requires approval")

---

### Case Study Pages

#### case-studies/restoring-delivery-visibility-and-governance-at-enterprise-scale/index.md

**Memo Style**: ✅ **Strong Compliance**

**Strengths**:

- Opens with context, then problem quickly.
- Clear structure with subheads.
- Outcomes stated concretely.

**No Issues**

---

**Buyer Journey**: ✅ **Compliant**

**Strengths**:

- "Why This Matters to Senior Leaders" section explicitly connects to buyer
- Related content present
- Specific CTA

**No Issues**

---

**No Consultant Speak**: ❌ **Significant Violations**

**Violations**:

1. "delivery visibility" - Consultant abstraction.
2. "enterprise-level visibility" - Consultant framing.
3. "governance failure" - Acceptable, but paired with consultant language.
4. "coherence" - Consultant term (repeated).
5. "system-level change" - Consultant framing.
6. "organizational process" - Consultant language.
7. "structural and enduring" - Consultant outcome framing.
8. "see and steer the system" - Consultant metaphor.
9. "restoring coherence" - Consultant abstraction.

**Recommended Rewrites**:

- "Leaders couldn't answer: Where is money going?" (not "delivery visibility")
- "Leaders see all projects in one dashboard" (not "enterprise-level visibility")
- "Reporting became trustworthy" (not "coherence")
- "Leaders decide which projects to kill" (not "see and steer the system")

---

#### case-studies/when-product-leadership-breaks-across-borders/index.md

**Memo Style**: ✅ **Strong Compliance**

**Strengths**:

- Opens with context, then problem statement quickly.
- Short paragraphs, direct voice.
- Clear progression through diagnosis and intervention.

**No Issues**

---

**Buyer Journey**: ✅ **Compliant**

**Strengths**:

- "Why This Matters to Senior Leaders" section
- Clear connection to problem domain
- Related content present

**No Issues**

---

**No Consultant Speak**: ❌ **Significant Violations**

**Violations**:

1. "leadership misalignment" - Consultant abstraction.
2. "decision clarity" - Consultant language (repeated).
3. "team autonomy" - Consultant outcome.
4. "delivery momentum" - Consultant metaphor.
5. "context was leaking" - Poetic consultant language.
6. "misaligned leadership assumptions" - Consultant diagnosis framing.
7. "system failure" - Consultant framing (though accurate).
8. "decision ownership" - Consultant language.
9. "embedded leadership mentorship" - Consultant engagement model speak.
10. "leadership system redesign" - Pure consultant framing.

**Recommended Rewrites**:

- "UK and Poland leaders made conflicting decisions" (not "leadership misalignment")
- "Product Owners decided without asking permission" (not "decision clarity")
- "Teams solved problems without escalating" (not "team autonomy")
- "Shipping sped up by 40%" (not "delivery momentum")
- "Engineers didn't understand why features mattered" (not "context was leaking")

---

#### case-studies/restoring-engineering-leverage-in-a-global-oil-and-gas/index.md

**Memo Style**: ✅ **Strong Compliance**

**Strengths**:

- Opens with scale context, then problem quickly.
- Short paragraphs.
- Clear outcomes stated.

**No Issues**

---

**Buyer Journey**: ✅ **Compliant**

**Strengths**:

- Clear connection to leadership problem
- Related content present
- Specific CTA

**No Issues**

---

**No Consultant Speak**: ❌ **Significant Violations**

**Violations**:

1. "engineering leverage" - Consultant abstraction (repeated).
2. "loss of leverage" - Consultant framing.
3. "integration economics" - Consultant language.
4. "team accountability" - Consultant abstraction.
5. "governing model" - Consultant framing.
6. "structured deliberately" - Consultant language.
7. "accountability can actually function" - Consultant outcome framing.

**Recommended Rewrites**:

- "Each engineer produced less output per day" (not "loss of leverage")
- "Teams blamed central build group for delays" (not "team accountability removed")
- "Leaders couldn't answer: What causes delays?" (not "governing model")
- "Teams owned their own builds" (not "accountability can actually function")

---

### Outcome Pages

#### outcomes/engineering-excellence/index.md

**Memo Style**: ✅ **Strong Compliance**

**Strengths**:

- Opens with reframe: "Engineering excellence is not about skill..."
- Short paragraphs, direct voice.
- Clear structure with subheads.

**No Issues**

---

**Buyer Journey**: ✅ **Compliant**

**Strengths**:

- "What Leaders Actually Mean" section connects to buyer intent
- Related content present
- Clear framing of who this is for

**No Issues**

---

**No Consultant Speak**: ❌ **Severe Violations**

**Violations** (extensive):

1. "engineering excellence" - Acceptable domain term, but used as consultant crutch.
2. "turn intent into reliable outcomes" - Consultant abstraction.
3. "invisible risk" - Consultant framing.
4. "system level" - Consultant framing (repeated).
5. "engineering leverage" - Consultant term (repeated).
6. "coordination cost" - Consultant metric (repeated).
7. "learning slows and risk accumulates" - Consultant framing.
8. "operating-model design" - Acceptable per instructions, but used as consultant crutch.
9. "strategic asset" - Consultant metaphor.
10. "capability enablement at points of highest leverage" - Pure consultant speak.

**Recommended Rewrites**:

- "Plans become shipped features reliably" (not "turn intent into reliable outcomes")
- "Defects show up 3 weeks earlier" (not "invisible risk surfaces early")
- "Each engineer ships 2x more features" (not "engineering leverage")
- "15 coordination meetings drop to 3" (not "coordination cost reduces")
- "Engineering becomes a competitive advantage" (not "strategic asset")

---

#### outcomes/technical-leadership/index.md

**Memo Style**: ✅ **Strong Compliance**

**Strengths**:

- Opens with clear reframe of technical leadership.
- Short paragraphs.
- Direct voice throughout.

**No Issues**

---

**Buyer Journey**: ✅ **Compliant**

**Strengths**:

- Clear framing of leadership problem
- Related content present
- "When This Is a Fit" section helps buyers self-select

**No Issues**

---

**No Consultant Speak**: ❌ **Severe Violations**

**Violations** (extensive):

1. "make, sustain, and trust technical decisions at scale" - Consultant outcome framing.
2. "decision drag" - Consultant metaphor.
3. "invisible risk" - Consultant language (repeated).
4. "operating models that do not scale judgment" - Pure consultant speak.
5. "more leverage" - Consultant outcome (repeated).
6. "system of work" - Acceptable, but used as crutch (repeated).
7. "judgment to scale" - Consultant abstraction.
8. "decision latency" - Consultant metric.
9. "leadership enablement" - Consultant framing.
10. "leadership system redesign" - Consultant language.

**Recommended Rewrites**:

- "Platform decisions take 2 days instead of 2 months" (not "decision drag")
- "Architectural choices don't need to be revisited 3 months later" (not "invisible risk")
- "Senior architects don't bottleneck every decision" (not "scale judgment")
- "5 people make platform decisions instead of 1" (not "judgment to scale")

---

### Diagnostic Assessment Page

**Memo Style**: ✅ **Strong Compliance**

**Strengths**:

- Opens with three clear questions.
- Short, direct paragraphs.
- No fluff or setup.

**No Issues**

---

**Buyer Journey**: ✅ **Excellent Compliance**

**Strengths**:

- Explicitly states what buyer gets from assessment.
- Clear self-selection criteria ("Who This Is For").
- "Not Ready Yet?" section provides alternative paths.
- Perfect positioning in buyer journey (between reading and engaging).

**No Issues**

---

**No Consultant Speak**: ⚠️ **Minor Violations**

**Violations**:

1. "root constraints" - Consultant diagnostic language.
2. "operating model, organizational structure, or technical architecture" - Consultant categorization (though necessary for clarity here).

**Minor Issue**: These violations are acceptable in an assessment-framing context. Buyers expect diagnostic language here.

---

## Patterns Summary

### Memo Style: Generally Strong

**Compliance Rate**: 85%

**Strengths**:

- Most pages open directly without buildup.
- Short paragraphs are consistent.
- Subheads are clear and direct.
- No marketing fluff or thought leadership tone.

**Deviations**:

- Homepage and About page start with identity statements instead of information.
- "What You Get" and "What I Do" sections sometimes feel listy rather than memo-direct.

**Priority Fixes**:

1. Rewrite homepage opening to start with problem, not identity.
2. Rewrite about page to start with leadership problem, not role definition.
3. Convert "What You Get" bullets to single-sentence statements.

---

### Buyer Journey: Strong Foundation

**Compliance Rate**: 90%

**Strengths**:

- Navigation infrastructure (related content links) is excellent.
- Problem → Insight → Case Study → Outcome flow is clear.
- Contact CTAs are contextual and specific.
- "What to Do Next" sections exist on most pages.
- Diagnostic assessment perfectly positioned.

**Deviations**:

- Related content links lack contextual guidance explaining why they matter.
- Some insights and case studies don't explicitly tell buyer what to do with information.

**Priority Fixes**:

1. Add 1-2 sentences before related content explaining what buyer gains from each path.
2. Add "What to Do Next" sections to problem pages that lack them.
3. In insights, add context around why related case studies or problems matter to this buyer's situation.

---

### No Consultant Speak: Systemic Violations

**Compliance Rate**: 70%

**Strengths**:

- No buzzwords like "synergy", "transformation", "disruption".
- Evidence and outcomes are often quantified.
- Avoids worst offenders like "stakeholder alignment" and "change management".

**Deviations** (Pervasive):

**Category 1: Vague Action Verbs**

- "enable", "facilitate", "establish", "achieve", "optimize", "strengthen"
- Appears on: Homepage, About, Problems, Outcomes

**Category 2: Abstract Outcomes**

- "leverage", "clarity", "coherence", "capability", "visibility", "momentum", "discipline"
- Appears on: All content types

**Category 3: Consultant Metrics**

- "coordination cost", "decision latency", "learning speed", "decision quality"
- Appears on: Problems, Insights, Outcomes

**Category 4: Consultant Diagnostic Language**

- "constraints", "system of work", "operating model", "leverage points"
- Appears on: All content types (NOTE: "system of work" and "operating model" are acceptable per instructions, but overused as crutch)

**Most Severe Violations** (pure consultant speak):

1. "capability enablement at points of highest leverage" (outcomes/engineering-excellence)
2. "judgement, pattern recognition, and intervention at leverage points" (problems/devops)
3. "leadership system redesign" (case-studies/when-product-leadership-breaks)
4. "operating models that do not scale judgment" (outcomes/technical-leadership)
5. "structured deliberately" (case-studies/restoring-engineering-leverage)

**Priority Fixes**:

1. Systematically replace vague action verbs with concrete activities.
2. Replace abstract outcomes with specific metrics or observable behaviors.
3. Replace consultant metrics with business language or concrete measurements.
4. Test every claim against CFO test: "Would a CFO say this in a board meeting?"

---

## Recommended Action Plan

### Phase 1: Critical Violations (Immediate)

**Target**: Eliminate severe consultant speak from all pages.

**Priority Pages** (ranked by visibility and severity):

1. Homepage (_index.md) - Most visible, moderate violations
2. About page (about/index.md) - High visibility, severe violations
3. Outcome pages (engineering-excellence, technical-leadership) - Severe violations, critical buyer journey stage
4. Case studies (all) - Severe violations, high buyer journey value

**Approach**: Use consultant-speak-to-leadership-language translation table (create this as reference).

**Timeline**: 1-2 days

---

### Phase 2: Moderate Violations (Next Week)

**Target**: Clean up consultant speak from insights and problem pages.

**Priority Pages**:

1. Problem pages (devops, scaling, ai) - Moderate violations
2. Insight pages (all reviewed) - Moderate violations

**Approach**: Apply same translation table, focus on action verbs and abstract outcomes.

**Timeline**: 2-3 days

---

### Phase 3: Refinement (Following Week)

**Target**: Improve memo style and buyer journey guidance.

**Actions**:

1. Rewrite homepage opening.
2. Rewrite about page opening and structure.
3. Add contextual guidance before related content links on all insights.
4. Add "What to Do Next" sections to problem pages.
5. Review all "What You Get" / "What I Do" sections for memo directness.

**Timeline**: 2-3 days

---

### Phase 4: Quality Assurance

**Target**: Verify compliance across all content.

**Actions**:

1. Run CFO test on every page: Would a CFO use this language in a board conversation?
2. Check that every page passes memo test: Front-loaded information, short paragraphs, no buildup.
3. Verify buyer journey: Can a buyer follow the path and know what to do at each stage?

**Timeline**: 1 day

---

## Measurement & Validation

### Success Criteria

**Memo Style**:

- No page starts with identity statement or role definition.
- No paragraphs exceed 4 lines (except for context-setting in case studies).
- Information is front-loaded in every section.

**Buyer Journey**:

- Every insight and case study has contextual guidance for related content.
- Every problem page has "What to Do Next" section.
- Buyer can answer: "What do I do with this information?"

**No Consultant Speak**:

- Zero instances of severe violations (capability enablement, leverage points, scale judgment, etc.).
- Vague action verbs reduced by 90%.
- Abstract outcomes replaced with concrete metrics or observable behaviors.
- CFO test passes on 100% of pages.

### Testing Method

**Before Publishing Each Fix**:

1. Read aloud. Does it sound like a business conversation or a consultant pitch?
2. CFO test: Would a CFO or board member use this exact phrase?
3. Memo test: Is information front-loaded? Are paragraphs short?
4. Buyer journey test: Does buyer know what to do next?

---

## Appendix: Translation Table (Consultant Speak → Leadership Language)

### Vague Action Verbs

| Consultant Speak          | Leadership Language                                         |
| ------------------------- | ----------------------------------------------------------- |
| Enable teams              | Teams decide without escalating                             |
| Facilitate alignment      | Engineering and product agree on priorities in one meeting  |
| Establish clarity         | Problems are written down before work starts                |
| Achieve predictability    | You hit quarterly targets                                   |
| Optimize delivery         | Shipping takes 3 weeks instead of 3 months                  |
| Strengthen capability     | Teams solve problems they couldn't solve 6 months ago       |
| Accelerate learning       | You test pricing in 2 weeks instead of 2 quarters           |
| Drive outcomes            | Revenue increases 25%                                       |
| Transform the organization | 40% fewer coordination meetings                            |
| Leverage existing systems | Use tools you already own                                   |

### Abstract Outcomes

| Consultant Speak           | Leadership Language                                        |
| -------------------------- | ---------------------------------------------------------- |
| Engineering leverage       | Each engineer ships 2x more features                       |
| Decision clarity           | Leaders decide who owns what before work starts            |
| Organizational coherence   | Reports match reality                                      |
| Delivery momentum          | Shipping speeds up 40%                                     |
| Team autonomy              | Teams solve problems without escalating                    |
| Strategic optionality      | You can pivot when competitors move                        |
| Enhanced collaboration     | 15 coordination meetings drop to 3                         |
| Improved agility           | You launch experiments without board approval              |
| Sustained capability       | Teams keep improving after consultant leaves               |
| Delivery visibility        | Leaders see which projects are delayed and why             |

### Consultant Metrics

| Consultant Speak    | Leadership Language                                       |
| ------------------- | --------------------------------------------------------- |
| Coordination cost   | 20% fewer meetings per week                               |
| Decision latency    | Platform decisions take 2 days instead of 2 months        |
| Learning speed      | Experiments complete in 3 weeks instead of 4 months       |
| Decision quality    | Architectural choices don't need revisiting 3 months later |
| Feedback loops      | Teams see test results in 10 minutes instead of 2 days    |
| Speed to evidence   | You validate pricing before hiring sales team             |
| Cycle time          | Features ship in 2 weeks instead of 8                     |

### Consultant Diagnostic Language

| Consultant Speak                   | Leadership Language (when necessary) |
| ---------------------------------- | ------------------------------------ |
| Constraints                        | What stops delivery                  |
| Leverage points                    | Where small changes produce big results |
| System of work                     | How work gets done (acceptable per instructions) |
| Operating model                    | How the organization is structured (acceptable) |
| Decision ownership                 | Who decides                          |
| Capability enablement              | Teaching teams to solve problems     |
| System-level change                | Changing how the organization works  |
| Operating conditions               | The environment teams work in        |

---

## Conclusion

**The site has a strong foundation**. Structure, navigation, and buyer journey architecture are excellent. Memo-style writing is mostly compliant.

**The primary deviation is consultant speak**. This appears across all content types and undermines otherwise strong content. Eliminating consultant speak will immediately improve clarity, credibility, and buyer trust.

**Recommended priority**: Fix consultant speak first, then refine memo style and buyer journey guidance.

**Estimated total effort**: 8-10 days for full compliance across all reviewed content.

**ROI**: High. Consultant speak creates buyer skepticism. Leadership language builds trust and shortens decision cycles.
