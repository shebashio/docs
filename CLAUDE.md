# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project overview

This is the DEDZED (Digital Environment and Development for Zero-trust Enablement and Data) documentation site built on Mintlify. Pages are MDX files with YAML frontmatter. Site configuration lives in `docs.json`.

## Commands

```bash
# Install the Mintlify CLI (requires Node.js >= 19)
npm i -g mint

# Local preview at http://localhost:3000
mint dev

# Custom port
mint dev --port 3333

# Check for broken links
mint broken-links

# Update CLI to latest version
npm mint update
```

## Architecture

- `docs.json` — site configuration: navigation, theme, colors, logos, navbar, footer
- `index.mdx` — landing page with service links and navigation cards
- `getting-started/` — onboarding guides: prerequisites, self-registration, cluster deployment, provisioning info
- `kasm-workspaces/` — Kasm VDI documentation: working within Kasm, cluster connection, software installation
- `knowledge-base/` — reference material: what is DEDZED, ephemeral environments FAQ, k9s cheat sheet, Python dev, Ask Pablo
- `support/` — contact info, terms, privacy policy
- `images/`, `logo/` — static assets
- `.mintignore` — files excluded from Mintlify builds (drafts, `*.draft.mdx`)

## Important terminology

- **DEDZED** / **D3DZ3D** — the platform name (Digital Environment and Development for Zero-trust Enablement and Data)
- **DEDZED Command Dashboard** — the main portal UI (do NOT refer to this as "Backstage")
- **Ping Identity** — the authentication provider (do NOT refer to this as "EntraID" or "Microsoft EntraID")
- **Kasm** — the Virtual Desktop Infrastructure (VDI) browser-based desktop
- **Big Bang** — the DevSecOps Kubernetes platform deployed on ephemeral clusters

## Content conventions

- All pages must register in `docs.json` under `navigation.tabs[].groups[].pages` to appear in the site
- Use active voice and second person ("you")
- Sentence case for headings
- Bold for UI elements: Click **Settings**
- Code formatting for file names, commands, paths, and code references
- One idea per sentence

## Deployment

Changes pushed to the default branch auto-deploy via the Mintlify GitHub app.
