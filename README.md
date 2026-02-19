# DEDZED Documentation

Documentation site for the DEDZED platform, built with [Mintlify](https://mintlify.com).

**Live site:** [docs.icbm.dev](https://docs.icbm.dev)

## Development

Requires Node.js >= 19. Install the Mintlify CLI:

```bash
npm i -g mint
```

Preview locally:

```bash
mint dev
```

View at `http://localhost:3000`.

To check for broken links:

```bash
mint broken-links
```

## Structure

| Path | Content |
|---|---|
| `docs.json` | Site configuration (navigation, theme, logos, navbar) |
| `index.mdx` | Landing page |
| `getting-started/` | Onboarding: prerequisites, registration, cluster deployment |
| `kasm-workspaces/` | Kasm VDI: workspace setup, cluster connection, software installation |
| `knowledge-base/` | Reference: platform overview, ephemeral environments, k9s, Python, DEDZED AI |
| `support/` | Contact, terms, privacy |
| `logo/` | SVG logos (light/dark variants) |
| `favicon.svg` | Site favicon |

## Adding a page

1. Create an `.mdx` file with YAML frontmatter:

   ```mdx
   ---
   title: "Page title"
   description: "Short description"
   ---

   Content here.
   ```

2. Register it in `docs.json` under `navigation.tabs[].groups[].pages`.

## Deployment

Changes pushed to the default branch auto-deploy via the [Mintlify GitHub app](https://dashboard.mintlify.com/settings/organization/github-app).

## Support

Contact **dedzed-tech@shebash.io** for questions or issues.
