# Hinshelwood.com

The official website for Martin Hinshelwood - Independent consultant specialising in DevOps, Agile, Lean, and AI enablement.

## 🌐 Live Deployments

- **Production**: https://calm-island-0dc928510.4.azurestaticapps.net/
- **Preview**: https://calm-island-0dc928510-preview.centralus.4.azurestaticapps.net/

## 📋 About

This site helps organisations understand and improve their systems of work so teams can deliver valuable software more effectively and with greater confidence. The site features:

- Case studies
- Technical insights and articles
- Outcomes and success stories
- Solutions to common problems in DevOps, AI, and Scaling

## 🛠️ Technology Stack

- **Static Site Generator**: [Hugo](https://gohugo.io/)
- **Hosting**: Azure Static Web Apps
- **Language**: Go templating with HTML/CSS/JavaScript

## 📁 Project Structure

```
Hinshelwood.com/
├── site/                           # Hugo source files
│   ├── content/                    # Markdown content files
│   │   ├── about/
│   │   ├── case-studies/
│   │   ├── insights/
│   │   ├── outcomes/
│   │   └── problems/
│   ├── layouts/                    # Hugo templates
│   │   ├── _partials/              # Reusable partial templates
│   │   ├── shortcodes/             # Hugo shortcodes
│   │   ├── baseof.html
│   │   ├── single.html
│   │   └── list.html
│   ├── hugo.yaml                   # Main Hugo configuration
│   ├── hugo.production.yaml        # Production config
│   ├── hugo.preview.yaml           # Preview config
│   └── hugo.canary.yaml            # Canary config
├── public/                         # Generated static files (output)
├── staticwebapp.config.json        # Azure Static Web Apps config
├── staticwebapp.config.production.json
├── staticwebapp.config.preview.json
└── staticwebapp.config.canary.json
```

## 🚀 Getting Started

### Prerequisites

- [Hugo](https://gohugo.io/installation/) (Extended version recommended)
- Git

### Local Development

1. **Clone the repository**
   ```bash
   git clone https://github.com/nkdAgility/hinshelwood.com.git
   cd hinshelwood.com
   ```

2. **Run Hugo locally**
   ```bash
   cd site
   hugo server --config hugo.local.yaml
   ```

3. **View the site**
   Open your browser to `http://localhost:1313`

### Building for Production

To build the static site for production:

```bash
cd site
hugo --config hugo.production.yaml
```

The generated files will be in the `public/` directory.

## 🌍 Environment Configurations

The site supports multiple deployment environments:

- **Local**: `hugo.local.yaml` - For local development
- **Preview**: `hugo.preview.yaml` - For preview deployments
- **Canary**: `hugo.canary.yaml` - For canary testing
- **Production**: `hugo.production.yaml` - For production deployments

Each configuration can override base settings from `hugo.yaml`.

## 📝 Content Management

Content is written in Markdown and stored in `site/content/`. Each content type has its own directory:

- `about/` - About page
- `case-studies/` - Client case studies
- `insights/` - Technical articles and blog posts
- `outcomes/` - Success stories and outcomes
- `problems/` - Problem domains and solutions

### Adding New Content

```bash
cd site
hugo new insights/my-new-article.md
```

## 🔧 Azure Static Web Apps Configuration

The site uses different Static Web Apps configurations per environment:

- `staticwebapp.config.json` - Base configuration
- `staticwebapp.config.production.json` - Production overrides
- `staticwebapp.config.preview.json` - Preview overrides
- `staticwebapp.config.canary.json` - Canary overrides

## 🤝 Contributing

This is a personal website, but if you notice any issues or have suggestions, please:

1. Open an issue in the GitHub repository
2. Submit a pull request with your changes

## 📄 License

Copyright © Martin Hinshelwood. All rights reserved.

## 👤 Author

**Martin Hinshelwood**
- Website: [Hinshelwood.com](https://hinshelwood.com)
- Twitter: [@mrhinsh](https://twitter.com/mrhinsh)
- GitHub: [@nkdAgility](https://github.com/nkdAgility)
