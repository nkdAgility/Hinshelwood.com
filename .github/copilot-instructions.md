# Hinshelwood.com - Repository Instructions

**Purpose**: Professional consulting website for Martin Hinshelwood specializing in DevOps, Agile, Lean, and AI enablement.

**Repository**: https://github.com/nkdAgility/Hinshelwood.com  
**Type**: Hugo static site (Extended version required)  
**Primary Language**: Markdown content, Go templates, YAML configuration  
**Deployment**: Azure Static Web Apps

Trust these instructions. Only search for additional information if you find gaps or errors.

## Build & Development Commands

**Hugo Version**: latest extended

**IMPORTANT**: Always run Hugo commands from the repository root, not from the `site/` directory.

### Local Development

```pwsh
hugo serve --source site --config hugo.yaml,hugo.local.yaml
```

- Run from repository root
- Opens at `http://localhost:1313`
- Hot reloads on file changes

### Production Build

```pwsh
hugo --source site --config hugo.yaml,hugo.production.yaml --logLevel info
```

- Run from repository root
- Output: `public/` directory at repo root (not `site/public/`)
- Typical output: 23 pages, <1MB
- Environment configs overlay base `hugo.yaml`: production, preview, canary, local

### Preview Build

```pwsh
hugo --source site --config hugo.yaml,hugo.preview.yaml
```

- Run from repository root

### Canary Build

```pwsh
hugo --source site --config hugo.yaml,hugo.canary.yaml
```

- Run from repository root

**Important**: Always specify both base config and environment config when building. Hugo merges them in order.

## Project Structure

```
/
├── .github/
│   ├── copilot-instructions.md          # This file
│   ├── .analysis/
│   │   └── buyer-journey-analysis.md    # Buyer journey mapping and implementation plan
│   ├── instructions/*.instructions.md    # Scoped rules for content sections
│   ├── workflows/
│   │   ├── main.yaml                     # Primary CI/CD pipeline (GitVersion, multi-environment deploy)
│   │   ├── azure-static-web-apps-*.yml  # Azure SWA deployment (currently disabled)
│   │   └── close-pr.yaml                # PR cleanup
│   └── GitVersion.yml                    # Semantic versioning config
├── site/                                 # Hugo source (work here)
│   ├── content/                          # Markdown content files
│   │   ├── _index.md
│   │   ├── about/
│   │   ├── case-studies/
│   │   ├── insights/
│   │   ├── outcomes/
│   │   └── problems/
│   ├── layouts/                          # Hugo templates
│   │   ├── baseof.html                   # Base template
│   │   ├── single.html                   # Single page layout
│   │   ├── list.html                     # List page layout
│   │   ├── sitemap.xml
│   │   └── robots.txt
│   ├── hugo.yaml                         # Base Hugo configuration
│   ├── hugo.production.yaml              # Production overrides
│   ├── hugo.preview.yaml                 # Preview overrides
│   ├── hugo.canary.yaml                  # Canary overrides
│   └── hugo.local.yaml                   # Local dev overrides
├── public/                               # Generated static output (do NOT edit)
├── staticwebapp.config.json              # Base Azure SWA routing
├── staticwebapp.config.production.json   # Production routing overrides
├── staticwebapp.config.preview.json      # Preview routing overrides
├── staticwebapp.config.canary.json       # Canary routing overrides
├── .spellcheck.yml                       # Spell check configuration (pyspelling)
├── .wordlist.txt                         # Custom dictionary
├── .prettierrc                           # Code formatting
└── readme.md                             # Project documentation
```

## CI/CD Pipeline

**Primary Pipeline**: `.github/workflows/main.yaml`

### Triggers

- Push to `main` branch
- Pull requests to `main`
- Manual workflow dispatch

### Pipeline Stages

1. **Setup**: GitVersion, ring determination (Production/Preview/Canary)
2. **BuildSite**: Hugo build with token replacement, artifact upload
3. **Publish**: Merge SWA configs, deploy to Azure Static Web Apps

### Ring Determination

- **Production**: When `GitVersion_PreReleaseLabel` is empty (release tags)
- **Preview**: When `GitVersion_PreReleaseLabel` is "Preview"
- **Canary**: Default for all other branches/PRs (includes PR number in environment name)

### Token Replacement

Template tokens use format `#{VariableName}#` in HTML/YAML files. Replaced before build with:

- GitVersion outputs (SemVer, Major, Minor, etc.)
- Hinshelwood-specific config (AzureSitesConfig, PR_Number)

### Deployment

- Uses `Azure/static-web-apps-deploy@v1` action
- Requires secret: `AZURE_STATIC_WEB_APPS_API_TOKEN_CALM_ISLAND_0DC928510`
- Deploys to environment-specific slot based on ring
- Output URL available as `steps.azureDeploy.outputs.static_web_app_url`

### Size Validation

Pipeline checks if `public/` exceeds 500MB (Azure SWA limit). Current size: ~0.08MB (safe).

## Custom Agents

For specialized content creation, use these custom agents:

- **Marketing Content**: `.github/agents/marketing-content.md` - Homepage, about pages, landing pages, service descriptions
- **Insights**: `.github/agents/insights.md` - Technical articles, thought leadership, opinionated analysis
- **Case Studies**: `.github/agents/case-studies.md` - Client engagement documentation with measurable outcomes
- **Social Proof**: `.github/agents/social-proof.md` - Client testimonials and feedback curation
- **Clients**: `.github/agents/clients.md` - Client roster and logo management

Each agent provides:

- Specific persona and role
- Content structure templates
- Quality checklists
- Integration patterns with other content

## Content Guidelines

### File Requirements

- **Format**: Markdown with YAML front matter
- **Naming**: lowercase-with-hyphens.md
- **Location**: `site/content/<section>/`

### Front Matter Template

```yaml
---
title: "Page Title"
date: YYYY-MM-DD
description: "One sentence description"
tags: ["tag1", "tag2"]
categories: ["section-name"]
---
```

### Internal Links

Use Hugo shortcodes (NOT relative markdown links):

```
{{< ref "path/to/file.md" >}}
{{< relref "file.md" >}}
```

### Creating New Content

```pwsh
hugo new insights/my-new-article.md --source site
```

- Run from repository root

### Content Sections

- **about/**: Company/consultant information (use marketing-content agent)
- **case-studies/**: Real client engagements with outcomes (use case-studies agent)
- **clients/**: Client roster and logos demonstrating experience breadth (use clients agent)
- **insights/**: Technical articles and opinions (use insights agent)
- **outcomes/**: Success stories categorized by type
- **problems/**: Problem domains (devops, scaling, ai)
- **social-proof/**: Client testimonials and feedback (use social-proof agent)

**See `.github/instructions/*.instructions.md` for section-specific writing standards.**

## Buyer Journey Architecture

**Reference**: `.github/.analysis/buyer-journey-analysis.md`

The site implements explicit buyer journeys aligned with Allan Weiss principles. Content guides buyers through three stages:

1. **Problem Awareness** (Insights, Problem pages)
2. **Solution Education** (Case studies, About page, Outcomes)
3. **Decision/Engagement** (Diagnostic assessment, Contact)

### Navigation Infrastructure

**Automated Linking** (implemented via bidirectional front matter relationships):

All buyer journey navigation is automated using the `related:` front matter array and the `site/layouts/_partials/functions/get-related-items.html` function. The system finds related content bidirectionally, so you only need to declare the relationship once.

**How it Works**:

1. Content pages use `related:` front matter array to declare relationships
2. Hugo templates use partial components to display related content:
   - `related-problems.html` - Shows related problem pages
   - `related-case-studies.html` - Shows related case studies
   - `related-insights.html` - Shows related insights (limited to first 5)
   - `related-outcomes.html` - Shows related outcome pages
3. The `get-related-items.html` function searches bidirectionally:
   - **Forward**: If page A lists page B in its `related:` array, page A displays page B
   - **Reverse**: If page B lists page A in its `related:` array, page A automatically displays page B
4. No need to add relationships in both directions

**Current Template Structure**:

- **Problem pages**: Display related case studies → related insights → related outcomes
- **Insights pages**: Display related problems → related case studies → related outcomes
- **Case study pages**: Display related outcomes → related problems
- **Outcome pages**: Display related case studies → related insights

**CRITICAL: One-Direction Linking Only**

**DO NOT add related items in both directions.** The system handles bidirectional linking automatically.

**Examples**:

✅ **Correct** - Add relationship in one place only:

```yaml
# In insights/why-ai-is-making-delivery-harder/index.md
related:
  - "problems/ai"
  - "outcomes/technical-leadership"
  - "case-studies/when-product-leadership-breaks-across-borders"
```

Result: The insight displays the case study, AND the case study automatically displays the insight.

❌ **Wrong** - Do not add the reverse relationship:

```yaml
# DO NOT do this in case-studies/when-product-leadership-breaks-across-borders/index.md
related:
  - "insights/2026-01-07-why-ai-is-making-delivery-harder" # WRONG - creates duplicate linking
```

**Where to Add Related Items**:

- **Insights → Problems, Outcomes, Case Studies**: Add to insight front matter
- **Case Studies → Problems, Outcomes**: Add to case study front matter (do NOT add insights)
- **Problems → Outcomes**: Add to problem front matter (case studies and insights link TO problems, not from)
- **Outcomes**: Generally link FROM other content types (insights, case studies link to outcomes)

**Path Format**:

Use section/slug format without leading slash or trailing slash:

- ✅ `"problems/ai"`
- ✅ `"case-studies/when-product-leadership-breaks-across-borders"`
- ✅ `"outcomes/technical-leadership"`
- ✅ `"insights/2026-01-07-why-ai-is-making-delivery-harder"`
- ❌ `"/problems/ai/"` (will work but inconsistent)

**Manual Guidance** (content layer):

- Contextual text around automated sections explaining why they matter
- "What to Do Next" sections after automated content
- Homepage triage routing buyers to appropriate problem page
- Diagnostic assessment offer between reading and engaging

### Creating Journey-Aligned Content

When creating new content:

1. **Add `related:` front matter** to link to relevant problems/outcomes/case studies (only in ONE direction)
2. **Add contextual guidance** explaining what buyer should do with information
3. **Include next-step CTAs** that are specific, not generic ("Assess your scaling constraint" not "Contact me")
4. **Test journey flow** by following links as if you were a buyer in that stage

Example front matter for insight:

```yaml
related:
  - "problems/ai"
  - "outcomes/technical-leadership"
  - "case-studies/when-product-leadership-breaks-across-borders"
  - "case-studies/restoring-delivery-visibility-and-governance-at-enterprise-scale"
```

Example front matter for case study:

```yaml
related:
  - "problems/devops"
  - "outcomes/engineering-excellence"
```

See buyer-journey-analysis.md for full journey maps, identified gaps, and implementation phases.

## Communication Style

Apply Allan Weiss principles to all content:

- Direct, active voice
- No marketing buzzwords or corporate speak
- Evidence-backed claims
- Front-load key information
- Short paragraphs (3-4 lines max)
- Challenge vague or unsupported assertions
- **American English only**
- **No em dashes** (use full stops, commas, or shorter sentences)
- **No analogies** (say what you mean directly)

Ask: "What does the reader gain?" If unclear, revise or delete.

## Project Positioning

**Site**: hinshelwood.com (NOT NKDAgility.com)  
**Purpose**: Buyer-focused diagnostic insight for senior leaders making systems-of-work decisions  
**Audience**: CTOs, engineering/product/platform leaders, growth and revenue leaders, boards, executive sponsors

**Martin's Role**: Diagnostician and expert consultant who helps leaders understand and manage their systems of work. NOT doing delivery for clients, NOT owning outcomes, NOT selling a fixed methodology.

**Content Intent**: Produce buyer-diagnostic insight that shapes decisions upstream of buying, without promotional tone or demand-gen tactics. Insights must stand alone and be useful without a pitch.

## Lens and Framing

**Prefer**: Operating model and systems of work framing  
**Emphasise**: Constraints, risk, learning speed, decision quality, evidence, flow, strategic optionality  
**Assume**: Issues are systemic, not people failures  
**Approach**: Start with buyer problem/risk, name why it persists, identify the constraint, state consequences of inaction, stop short of prescribing solutions unless explicitly asked

## Language Rules (Non-Negotiable)

**Avoid**:

- "Agile transformation" (prefer "systems of work redesign")
- "ways of working" (prefer "systems of work" or "operating model")
- "mindset" (prefer "ethos" when culture is relevant)
- "maturity models" (use specific capability assessments)
- Guaranteed results or fixed methodologies
- Hype or evangelism

**Use**:

- "systems of work" (default for processes, practices, funding, decisions, governance)
- "operating model" (when speaking to executives about organisational design)
- Direct, pragmatic, executive-safe language

## Configuration Files

### Hugo Configs (`site/hugo.*.yaml`)

- `hugo.yaml`: Base config (menus, params, site title)
- Environment configs: Override `baseURL`, `publishDir`, environment variables
- Merged at build time with `--config hugo.yaml,hugo.<env>.yaml`

### Static Web App Configs (`staticwebapp.config.*.json`)

- Control routing, redirects, security headers
- Pipeline merges base + environment config with `jq` before deployment
- Merged output placed in `public/` for deployment

### Spell Check (`.spellcheck.yml`)

- Uses `pyspelling` with aspell
- Custom wordlist: `.wordlist.txt`
- Runs on markdown files
- Ignores code blocks, pre, blockquote

## Common Pitfalls

1. **Wrong working directory**: Always run Hugo commands from repository root, use `--source site` flag
2. **Missing config**: Specify both base and environment config: `--config hugo.yaml,hugo.local.yaml`
3. **Editing public/**: Don't. It's generated. Edit source in `site/content/` or `site/layouts/`
4. **Hardcoded URLs**: Use Hugo variables or environment-specific configs
5. **Markdown links**: Use `{{< ref >}}` shortcodes, not `[text](../path.md)`

## Validation Before Commit

1. Build successfully: `hugo --source site --config hugo.yaml,hugo.local.yaml`
2. Check output size: Should be <10MB
3. Verify front matter is valid YAML
4. Test internal links work
5. Review spelling with project wordlist
6. Confirm content follows section-specific standards (see `.github/instructions/`)

## Files in Repo Root

- `.git/`, `.github/`: Version control and CI/CD
- `.gitattributes`, `.gitignore`: Git configuration
- `.prettierrc`: Code formatting rules
- `.spellcheck.yml`, `.wordlist.txt`: Spell checking
- `readme.md`: Project overview and setup
- `site/`: Hugo source directory
- `public/`: Hugo output (generated, not committed, do not edit)
- `staticwebapp.config*.json`: Azure Static Web Apps routing

## Key Dependencies

- Hugo Extended (for SCSS processing if needed)
- Git (for submodules and GitVersion)
- PowerShell (for CI/CD scripts)
- jq (for JSON merging in pipeline)
- Azure Static Web Apps (deployment target)

## Live Deployments

- **Production**: https://calm-island-0dc928510.4.azurestaticapps.net/
- **Preview**: https://calm-island-0dc928510-preview.centralus.4.azurestaticapps.net/
- **Canary**: Dynamic per PR

Deploy occurs automatically on push to main or PR merge based on GitVersion labels.

## Documentation Maintenance

**CRITICAL**: Keep documentation, instructions, and agent configurations synchronized.

### When to Update Documentation

Update these files whenever you:

1. **Change Build Process**
   - Update `.github/copilot-instructions.md` with new commands
   - Update `readme.md` if user-facing

2. **Add New Content Patterns**
   - Update relevant agent in `.github/agents/`
   - Update corresponding instructions in `.github/instructions/`
   - Document in `.github/copilot-instructions.md` if significant

3. **Modify CI/CD Pipeline**
   - Update `.github/copilot-instructions.md` with new stages or behavior
   - Document token changes or new environment variables

4. **Create New Content Types**
   - Create new `.github/instructions/*.instructions.md`
   - Create corresponding `.github/agents/*.md` if needed
   - Reference in `.github/copilot-instructions.md`

5. **Discover Build Issues or Workarounds**
   - Document in "Common Pitfalls" section
   - Add to relevant agent workflow if content-specific

### Documentation Files to Maintain

| File                                          | Purpose                         | Update When                                       |
| --------------------------------------------- | ------------------------------- | ------------------------------------------------- |
| `.github/copilot-instructions.md`             | Repository-wide guidance        | Build changes, new patterns, architecture changes |
| `.github/.analysis/buyer-journey-analysis.md` | Buyer journey strategy and gaps | Journey flow changes, new navigation patterns     |
| `.github/instructions/*.instructions.md`      | Content-specific rules          | Writing standards evolve, new content patterns    |
| `.github/agents/*.md`                         | Specialized content agents      | Workflow improvements, quality standards change   |
| `readme.md`                                   | User-facing documentation       | Setup changes, deployment changes                 |
| `.wordlist.txt`                               | Spell check dictionary          | New technical terms added                         |

### Quality Check Before Committing

When updating documentation:

- [ ] All referenced files exist and paths are correct
- [ ] Commands have been tested and work
- [ ] Cross-references between docs are accurate
- [ ] Examples are current and valid
- [ ] Build/deploy processes match actual pipeline
- [ ] Agent workflows reference correct instruction files

### Documentation Debt

If you discover outdated information:

1. Fix it immediately if straightforward
2. Document as a TODO in the relevant file if complex
3. Never leave known-incorrect information uncommented

Trust documentation first. Verify if uncertain. Update when wrong.
