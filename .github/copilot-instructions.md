# Hinshelwood.com - Repository Instructions

**Purpose**: Professional consulting website for Martin Hinshelwood specializing in DevOps, Agile, Lean, and AI enablement.

**Repository**: https://github.com/nkdAgility/Hinshelwood.com  
**Type**: Hugo static site (Extended version required)  
**Primary Language**: Markdown content, Go templates, YAML configuration  
**Deployment**: Azure Static Web Apps  
**Size**: Small (~11 pages, generates <1MB output)

Trust these instructions. Only search for additional information if you find gaps or errors.

## Build & Development Commands

**Hugo Version**: v0.152.2+extended (or as specified in GitHub Actions variable `HUGO_BUILD_VERSION`)

### Local Development
```pwsh
cd site
hugo server --config hugo.yaml,hugo.local.yaml
```
- Opens at `http://localhost:1313`
- Hot reloads on file changes
- Always run from `site/` directory
- Build time: ~110-134ms

### Production Build
```pwsh
cd site
hugo --config hugo.yaml,hugo.production.yaml --logLevel info
```
- Output: `public/` directory at repo root (not `site/public/`)
- Typical output: 23 pages, <1MB
- Environment configs overlay base `hugo.yaml`: production, preview, canary, local

### Preview Build
```pwsh
cd site
hugo --config hugo.yaml,hugo.preview.yaml
```

### Canary Build
```pwsh
cd site
hugo --config hugo.yaml,hugo.canary.yaml
```

**Important**: Always specify both base config and environment config when building. Hugo merges them in order.

## Project Structure

```
/
├── .github/
│   ├── copilot-instructions.md          # This file
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
cd site
hugo new insights/my-new-article.md
```

### Content Sections
- **about/**: Company/consultant information
- **case-studies/**: Real client engagements with outcomes
- **insights/**: Technical articles and opinions
- **outcomes/**: Success stories categorized by type
- **problems/**: Problem domains (devops, scaling, ai)

**See `.github/instructions/*.instructions.md` for section-specific writing standards.**

## Communication Style

Apply Allan Weiss principles to all content:
- Direct, active voice
- No marketing buzzwords or corporate speak
- Evidence-backed claims
- Front-load key information
- Short paragraphs (3-4 lines max)
- Challenge vague or unsupported assertions

Ask: "What does the reader gain?" If unclear, revise or delete.

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

1. **Wrong working directory**: Always `cd site` before running Hugo commands
2. **Missing config**: Specify both base and environment config: `--config hugo.yaml,hugo.local.yaml`
3. **Editing public/**: Don't. It's generated. Edit source in `site/content/` or `site/layouts/`
4. **Hardcoded URLs**: Use Hugo variables or environment-specific configs
5. **Markdown links**: Use `{{< ref >}}` shortcodes, not `[text](../path.md)`

## Validation Before Commit

1. Build successfully: `cd site; hugo --config hugo.yaml,hugo.local.yaml`
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
- `public/`: Hugo output (generated, not committed)
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
