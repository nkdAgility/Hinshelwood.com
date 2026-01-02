---
applyTo:
  - site/content/clients/**
  - site/data/clients.json
---

# Clients Instructions

## Purpose

Client documentation for hinshelwood.com demonstrates breadth of experience and establishes credibility with senior buyers. Write for CTOs, engineering/product/platform leaders, growth and revenue leaders, boards, and executive sponsors.

Present accurate client roster that shows range of industries, company sizes, and engagement types. Respect confidentiality while demonstrating experience.

## Content Requirements

Every client entry must include:
- **Company name**: Official name (or descriptor if confidential)
- **Industry**: Sector or classification
- **Engagement type**: Consulting, training, FTE, advisory
- **Verification**: Confirmed engagement occurred
- **Permission**: Appropriate clearance to display

Optional details (when permissible):
- Company logo
- Engagement dates
- Company size
- Specific outcomes (link to case study)

## Data Structure

Clients are stored in `site/data/clients.json`:

```json
{
  "clients": [
    {
      "id": "UNIQUE_ID",
      "name": "Company Name",
      "industry": "Sector",
      "logo": "/images/clients/company-logo.png",
      "engagementType": "consulting|training|fte|advisory",
      "dateStart": "YYYY-MM",
      "dateEnd": "YYYY-MM",
      "size": "enterprise|midmarket|startup",
      "public": true
    }
  ]
}
```

## Writing Standards

- **British English only**
- **No em dashes** (use full stops, commas, or shorter sentences)
- **No analogies** (say what you mean directly)
- Use official company names
- Respect confidentiality agreements
- Provide accurate industry classifications
- Include only verified engagements
- Direct, pragmatic, executive-safe language
- No promotional language about clients
- No overstating relationships

## Confidentiality Handling

When client cannot be named:
- Use industry descriptor: "Global Financial Services Company"
- Include company scale: "FTSE 100", "Fortune 500", "Series B Startup"
- Omit logo but include in client count
- Reference in case studies without naming
- Set `public: false` in data structure

## Engagement Type Definitions

**Consulting**: Strategic advisory, diagnostic work, systems of work redesign  
**Training**: Courses, workshops, certification programs  
**FTE**: Full-time equivalent embedded work with teams  
**Advisory**: Board advisory, executive coaching, ongoing counsel  

## Quality Standards

Accept client entries that:
- Have confirmed, verified engagements
- Include proper attribution and permission
- Respect confidentiality requirements
- Provide accurate company information
- Use properly licensed logos

Reject client entries that:
- Cannot be verified
- Lack necessary permissions
- Violate confidentiality agreements
- Include inaccurate information
- Overstate relationship or impact

## Red Flags to Eliminate

- Unverified or questionable engagements
- Names used without permission
- Overstated relationships ("key strategic partner")
- Inaccurate company details
- Unlicensed logos or branding
- Promotional language about the client
- Vague "worked with" without substance
- "Agile transformation" descriptions
- "ways of working" (prefer "systems of work" or "operating model")
- Hype or evangelism

## Language Rules

Use consistent, precise terminology when describing engagement types:

**Default term**: Use "systems of work" when describing processes, practices, funding flows, decision patterns, and governance mechanics.

**Executive context**: When addressing executives, boards, investors, or C-suite audiences, prefer "operating model" or "operating model hygiene" over "systems of work".

**Banned terms**: Never introduce or reintroduce "ways of working", "ways of work", or "mindset shifts" as preferred terms. These are vague and lack precision.

**Software systems**: If discussing software systems, technology architecture, or platforms, use explicit terms like "software systems", "technical architecture", or "platforms" to avoid ambiguity with "systems of work".

### Example Engagement Descriptions

**Before**: "Helped them transform their ways of working."
**After**: "Redesigned their systems of work to enable faster decision-making."

**Before**: "Improved their ways of work."
**After**: "Improved their systems of work."

**Executive context before**: "Optimised their systems of work."
**Executive context after**: "Optimised their operating model."

### Decision Rule

- If describing how work is designed to flow (processes, practices, governance, funding): use "systems of work".
- If speaking to executives about organisational design and constraints: use "operating model".
- If discussing software, platforms, or technical architecture: use explicit technical terms, not "systems".

## Logo Requirements

- High resolution (minimum 300px wide)
- Transparent background (PNG preferred)
- Official brand assets only
- Proper licensing or permission
- Consistent sizing and formatting
- Store in `site/static/images/clients/`

## Display Integration

Clients appear on:
- Homepage (featured clients)
- About page (full client list)
- Dedicated clients page with filtering

Common layouts:
- Logo grid (alphabetical or by industry)
- List with descriptions
- Filterable by industry, size, or engagement type

## Accuracy Standards

- Verify all engagements before listing
- Update when engagements end
- Remove if requested by client
- Check confidentiality status annually
- Maintain accurate contact information
- Keep logos current with rebrands

The goal is credible demonstration of experience, not an impressive-looking client list. Quality and accuracy over quantity.
