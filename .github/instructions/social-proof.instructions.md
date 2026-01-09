---
applyTo:
  - site/content/social-proof/**
  - site/data/socialproof.json
---

# Social Proof Instructions

## Purpose

Social proof for hinshelwood.com presents authentic client testimonials and feedback to help senior buyers evaluate Martin Hinshelwood's consulting services. Write for CTOs, engineering/product/platform leaders, growth and revenue leaders, boards, and executive sponsors.

Present real feedback that demonstrates credibility, expertise, and business value. No fabrication, no manipulation, no promotional enhancement.

## Content Requirements

Every social proof entry must include:

- **Authentic feedback**: Real quotes from real people
- **Attribution**: Name, role, company (when permissible)
- **Context**: Type of engagement (consulting, training, FTE)
- **Specificity**: Concrete outcomes or observations where possible
- **Date**: When the feedback was given or engagement occurred

## Data Structure

Social proof is stored in `site/data/socialproof.json`:

```json
{
  "quotes": [
    {
      "id": "UNIQUE_ID",
      "quote": "The actual feedback text",
      "author": "Person Name",
      "role": "Job Title",
      "company": "Company Name (optional)",
      "date": "YYYY-MM-DD",
      "engagementType": "consulting|training|fte",
      "tags": ["relevant", "tags"]
    }
  ]
}
```

## Writing Standards

- **American English only**
- **No em dashes** (use full stops, commas, or shorter sentences)
- **No analogies** (say what you mean directly)
- Present quotes exactly as given (no editing for style)
- Provide full context (who, when, what engagement)
- Include specific outcomes when mentioned
- Attribute properly with name and role
- Organise by engagement type
- Direct, pragmatic, executive-safe language
- Emphasise constraints removed, risk reduced, measurable outcomes
- Assume issues are systemic, not people failures

## No Consultant Speak (CRITICAL)

**Use leadership language, not consultant speak.** Allan Weiss promotes communicating in terms buyers understand, not industry jargon or consulting terminology.

**Social proof should sound like real client feedback, not curated testimonials from consulting marketing materials.**

### Consultant Speak to Avoid in Quote Selection

When selecting quotes to include, avoid those using:

**Process/methodology jargon**:
- ❌ "facilitated stakeholder alignment"
- ❌ "drove organizational transformation"
- ❌ "enabled delivery acceleration"
- ❌ "optimized our operating model"
- ❌ "leveraged best practices"

**Vague praise**:
- ❌ "enhanced our capabilities"
- ❌ "improved our agility"
- ❌ "strengthened our culture"
- ❌ "elevated our maturity"

### Leadership Language to Prefer

Prioritize quotes using concrete, plain language:

**Specific outcomes**:
- ✅ "We cut deployment time from 4 hours to 20 minutes"
- ✅ "Teams started shipping features in 2 weeks instead of 3 months"
- ✅ "Incident response dropped from 4 hours to 30 minutes"
- ✅ "We freed up 30% of engineering time for new work"

**Plain descriptions of value**:
- ✅ "Martin helped us see where decisions were stalling"
- ✅ "He showed us which platform constraints were slowing teams down"
- ✅ "We finally understood why quality issues appeared so late"
- ✅ "His diagnostic work revealed problems we'd been missing"

**Real working experiences**:
- ✅ "Martin challenged our assumptions about how work flowed"
- ✅ "He asked questions that made us rethink our approach"
- ✅ "His analysis identified constraints we couldn't see"
- ✅ "Working with Martin changed how we think about risk"

### When Editing Quotes

**Minor editing is acceptable** for:
- Spelling and grammar corrections
- Removing filler words ("um", "like", "you know")
- Clarifying ambiguous references

**Never edit to**:
- Change meaning or emphasis
- Add consultant speak that wasn't there
- Make generic praise more specific
- Exaggerate outcomes

### Presentation Language

When writing content around quotes:
- ✅ "What clients say"
- ❌ "Transformational impact testimonials"
- ✅ "Client feedback by outcome"
- ❌ "Strategic partnership success stories"

### Test Your Selection

Ask: **Does this quote sound like something a real person said in conversation, or like something from a consulting brochure?**

- If it sounds real, include it
- If it sounds polished or promotional, reconsider

Remember: Authenticity builds more credibility than polish. Real client language proves value better than consultant-perfect testimonials.

## Quality Standards

Accept quotes that:

- Come from verified real engagements
- Mention specific outcomes or changes
- Describe concrete experiences
- Reference business value or impact
- Include measurable results when possible

Reject quotes that:

- Are purely generic ("excellent work")
- Lack verifiable attribution
- Have been edited beyond basic cleanup
- Feel promotional rather than authentic
- Use hype or evangelism

## Integration

Social proof appears via shortcode in markdown:

```markdown
{{< social-proof id="UNIQUE_ID" >}}
```

Common placement:

- About pages to establish credibility
- Homepage to build trust
- Case study pages to support outcomes

## Red Flags to Eliminate

- Generic praise without specifics ("best consultant ever")
- Unverifiable quotes or anonymous sources
- Embellished or edited claims
- Quotes taken out of context
- Promotional language we've added
- Multiple similar quotes (select best representative)
- "Agile transformation" language
- "ways of working" (prefer "systems of work" or "operating model")
- "mindset" (prefer "ethos" when culture is relevant)
- Hype or evangelism

## Language Rules

Use consistent, precise terminology when describing organisational design and work structures:

**Default term**: Use "systems of work" when describing processes, practices, funding flows, decision patterns, and governance mechanics.

**Executive context**: When addressing executives, boards, investors, or C-suite audiences, prefer "operating model" or "operating model hygiene" over "systems of work".

**Banned terms**: Never introduce or reintroduce "ways of working", "ways of work", or "mindset shifts" as preferred terms. These are vague and lack precision.

**Software systems**: If discussing software systems, technology architecture, or platforms, use explicit terms like "software systems", "technical architecture", or "platforms" to avoid ambiguity with "systems of work".

### Example Rewrites

**Before**: "Martin transformed our ways of working and drove mindset shifts."
**After**: "Martin helped us redesign our systems of work, reducing deployment time by 60%."

**Before**: "He improved our ways of work."
**After**: "He improved our systems of work."

**Executive context before**: "Martin optimised our systems of work."
**Executive context after**: "Martin optimised our operating model."

### Decision Rule

- If describing how work is designed to flow (processes, practices, governance, funding): use "systems of work".
- If speaking to executives about organisational design and constraints: use "operating model".
- If discussing software, platforms, or technical architecture: use explicit technical terms, not "systems".

## Authenticity Standards

- Never fabricate or embellish testimonials
- Obtain permission before using (when required)
- Preserve original meaning and intent
- Correct only obvious typos or grammar errors
- Maintain speaker's voice and style
- Include unflattering feedback when relevant (builds credibility)

The goal is credibility through authenticity, not promotion through curation.
