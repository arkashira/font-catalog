<h3 align="center">🛠️ font-catalog</h3>

<div align="center">
  <img src="https://img.shields.io/github/license/axentx/font-catalog" alt="License: MIT">
  <img src="https://img.shields.io/github/languages/top/axentx/font-catalog" alt="Language">
  <img src="https://img.shields.io/github/actions/workflow/status/axentx/font-catalog/ci.yml" alt="Build Status">
  <img src="https://img.shields.io/github/stars/axentx/font-catalog" alt="Stars">
</div>

---

# 🚀 font-catalog

**Power designers and developers with a unified, type-safe font catalog.**  
A domain‑specific schema system and tooling for managing typeface families, font file metadata, and font license lifecycles, integrated with Sanity.

## Why font-catalog?

- **Schema‑first**: 100 % typed definitions for every font asset, reducing runtime errors.  
- **Lifecycle‑aware**: Automatic license expiry alerts and renewal workflows.  
- **Sanity‑native**: Seamless CRUD via Sanity’s GraphQL API, no custom backend.  
- **Performance‑oriented**: Lazy‑loaded font lists with caching, < 50 ms lookup.  
- **Built for**: UI/UX teams that need a single source of truth for web and mobile typography.

## Feature Overview

| Feature | Description |
|---------|-------------|
| **Domain‑specific schema** | JSON‑Schema + TypeScript types for families, weights, styles, and licenses. |
| **Sanity integration** | CRUD helpers that map schema to Sanity documents. |
| **License lifecycle** | Scheduler that flags expiring licenses and triggers renewal notifications. |
| **CLI tooling** | `font-catalog sync`, `font-catalog validate`, `font-catalog generate`. |
| **Documentation generator** | Auto‑creates Markdown docs from schema for designers. |
| **Type‑safe API** | Exposes a typed client for consuming font data in React/Vue/Node. |

## Tech Stack

- **TypeScript** – type safety across the codebase.  
- **Node.js** – runtime for CLI and serverless functions.  
- **Sanity.io** – headless CMS for storing font metadata.  
- **GraphQL** – Sanity’s query language for efficient data fetching.  
- **Jest** – unit testing framework.  
- **ESLint + Prettier** – code linting and formatting.  

*(All decisions are listed in `decisions/tech-stack.md`.)*

## Project Structure

```
business/
└─ src/
   ├─ schema/          # JSON‑Schema & TS types
   ├─ sanity/          # Sanity document definitions & helpers
   ├─ cli/             # Command‑line interface
   ├─ api/             # Typed client for consuming font data
   └─ docs/            # Generated documentation
```

## Getting Started

```bash
# Clone the repo
git clone https://github.com/axentx/font-catalog.git
cd font-catalog

# Install dependencies
npm install

# Build the project
npm run build

# Run the CLI to sync fonts with Sanity
npx font-catalog sync
```

## Deploy

```bash
# Deploy the CLI as a GitHub Action
# (See `decisions/tech-stack.md` for CI configuration)
```

## Status

Active – last commit `064cb6b` (Initial commit)

## Contributing

See the [CONTRIBUTING.md](CONTRIBUTING.md) guide.

## License

MIT