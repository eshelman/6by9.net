# CLAUDE.md - AI Assistant Guide for 6by9.net

This file provides guidance for AI assistants working on the 6by9.net repository.

## Project Overview

**Repository:** 6by9.net
**Owner:** Eliot Eshelman
**License:** MIT License (2026)
**URL:** https://6by9.net

Personal website for Eliot Eshelman built with Node.js.

## Technology Stack

- **Runtime:** Node.js
- **Deployment:** Digital Ocean App Platform (auto-deploys on push to GitHub)
- **Database:** None - static content only
- **External Integrations:** Interactive panels pulling data from external APIs (e.g., X/Twitter posts)

## Architecture

```
┌─────────────────────────────────────────────────────────┐
│                    6by9.net                             │
├─────────────────────────────────────────────────────────┤
│  Static Content          │  Interactive Panels          │
│  - HTML/CSS/JS           │  - X/Twitter feeds           │
│  - Assets                │  - Other external APIs       │
└─────────────────────────────────────────────────────────┘
                           │
                           ▼
              ┌─────────────────────────┐
              │ Digital Ocean App Platform │
              │   (Auto-deploy on push)    │
              └─────────────────────────┘
```

## Current Repository Structure

```
6by9.net/
├── LICENSE              # MIT License
├── CLAUDE.md            # This file - AI assistant guidance
├── design-language.html # Design system reference
└── .git/                # Git version control
```

*Structure will expand as the project develops*

## Design Language

The project uses a custom design system documented in `design-language.html`. Key principles:

### Visual Identity

- **Color Palette:** Charcoal backgrounds (#1a1a1f, #24242b) with orange (#ff6b2c) and blue (#2d8fc9) accents
- **Typography:** Inter for UI text, JetBrains Mono for code
- **Spacing:** 8px base unit with consistent scale (4, 8, 12, 16, 24, 32, 48, 64, 96px)

### Design Tokens (CSS Variables)

```css
/* Primary Colors */
--orange-500: #ff6b2c;
--blue-500: #2d8fc9;
--charcoal-900: #1a1a1f;  /* page background */
--charcoal-800: #24242b;  /* card background */

/* Typography */
--font-sans: 'Inter', system-ui, sans-serif;
--font-mono: 'JetBrains Mono', monospace;
```

### Core Principles

1. **High Data-Ink Ratio:** Maximize meaningful content, minimize decoration
2. **Generous Whitespace:** 8px base unit creates breathing room
3. **Geometric Accents:** Hexagons and triangles used sparingly as visual motifs
4. **Tufte-Inspired:** Follow data visualization best practices—no chartjunk, honest scales

When implementing new features, reference `design-language.html` for component patterns, color usage, and typography guidelines.

## Development Guidelines

### Git Workflow

- **Main Branch:** Development happens on feature branches
- **Commit Messages:** Use clear, descriptive commit messages that explain the "why"
- **Branch Naming:** Feature branches should use descriptive names (e.g., `feature/add-homepage`, `fix/broken-links`)

### Code Style & Conventions

As the project grows, maintain these principles:

1. **Keep it Simple:** Avoid over-engineering; implement only what's needed
2. **Document Changes:** Update this CLAUDE.md as new patterns emerge
3. **Follow Standards:** Use conventional formatting for the languages/frameworks adopted

### Security Considerations

- Never commit secrets, API keys, or credentials
- Review dependencies for known vulnerabilities
- Follow OWASP best practices for any web-facing code

## Common Tasks

### Initial Setup

```bash
# Clone the repository
git clone <repository-url>
cd 6by9.net

# Install dependencies
npm install

# Run development server
npm run dev
```

### Adding New Features

1. Create a feature branch
2. Implement changes
3. Test locally with `npm run dev`
4. Commit with descriptive messages
5. Push to GitHub (triggers auto-deploy to Digital Ocean)

### Deployment

Deployment is automatic via Digital Ocean App Platform:
- Push to main branch triggers production deployment
- No manual deployment steps required
- Monitor deployment status in Digital Ocean dashboard

## External API Integrations

When adding interactive panels that pull external data:

1. **X/Twitter:** Use embedded widgets or API calls for displaying posts
2. **Other APIs:** Document any new integrations in this section
3. **Rate Limits:** Be mindful of API rate limits; cache responses when appropriate
4. **Client-side:** Prefer client-side API calls to avoid server dependencies

## Notes for AI Assistants

When working on this repository:

1. **Read before modifying:** Always understand existing code before making changes
2. **Minimal changes:** Only make changes that are directly requested
3. **Verify paths:** Check that files and directories exist before operations
4. **Update documentation:** Keep this CLAUDE.md current as the project evolves
5. **Respect the license:** All contributions fall under the MIT License

---

*Last updated: 2026-01-11*
