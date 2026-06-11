# TECH_SPEC.md
## Technical Specification: font-catalog
### Overview

The font-catalog project is a domain-specific schema system and tooling for managing typeface families, font file metadata, and font license lifecycles. It integrates with Sanity.io, a headless CMS, to provide a unified, type-safe font catalog for designers and developers.

### Architecture

The font-catalog architecture consists of the following components:

* **Schema**: A domain-specific schema defined using JSON-Schema and TypeScript types, which provides a typed definition for every font asset.
* **Sanity Integration**: A set of CRUD helpers that map the schema to Sanity documents, enabling seamless interaction with the Sanity.io CMS.
* **License Lifecycle**: A scheduler that flags expiring licenses and triggers renewal notifications, ensuring that font licenses are up-to-date.
* **CLI Tooling**: A set of command-line tools (`font-catalog sync`, `font-catalog validate`, `font-catalog generate`) that provide functionality for syncing fonts with Sanity, validating font data, and generating documentation.
* **Documentation Generator**: A tool that auto-creates Markdown documentation from the schema, providing designers with a single source of truth for web and mobile typography.
* **Type-Safe API**: A typed client that exposes a type-safe API for consuming font data in React, Vue, and Node.js applications.

### Data Model

The font-catalog data model consists of the following entities:

* **Font Family**: A collection of fonts that share a common name and style.
* **Font**: A single font file with associated metadata (e.g., weight, style, license).
* **License**: A font license with associated metadata (e.g., expiry date, renewal notifications).

The data model is defined using JSON-Schema and TypeScript types, ensuring that all font data is typed and validated.

### Key APIs/Interfaces

The font-catalog project exposes the following APIs/interfaces:

* **Sanity GraphQL API**: A GraphQL API that provides efficient data fetching and querying capabilities for font data.
* **Type-Safe API**: A typed client that provides a type-safe API for consuming font data in React, Vue, and Node.js applications.
* **CLI Tooling**: A set of command-line tools that provide functionality for syncing fonts with Sanity, validating font data, and generating documentation.

### Tech Stack

The font-catalog project uses the following technologies:

* **TypeScript**: A superset of JavaScript that provides type safety across the codebase.
* **Node.js**: A runtime environment for executing JavaScript code on the server-side.
* **Sanity.io**: A headless CMS that provides a scalable and flexible data storage solution.
* **GraphQL**: A query language that provides efficient data fetching and querying capabilities.
* **Jest**: A unit testing framework that provides a comprehensive testing solution.
* **ESLint + Prettier**: A code linting and formatting solution that ensures consistent code quality.

### Dependencies

The font-catalog project depends on the following libraries and frameworks:

* **@sanity/client**: A JavaScript client for interacting with the Sanity.io CMS.
* **@sanity/types**: A set of TypeScript types for working with Sanity.io data.
* **graphql**: A JavaScript implementation of the GraphQL query language.
* **jest**: A unit testing framework for JavaScript applications.
* **eslint**: A code linting solution for JavaScript applications.
* **prettier**: A code formatting solution for JavaScript applications.

### Deployment

The font-catalog project can be deployed as a GitHub Action, which provides a scalable and automated deployment solution. The deployment process involves the following steps:

1. Clone the repository and install dependencies.
2. Build the project using the `npm run build` command.
3. Deploy the CLI as a GitHub Action using the `npx font-catalog deploy` command.

### Status

The font-catalog project is currently in an active development state, with the last commit being `064cb6b` (Initial commit).

### Contributing

Contributions to the font-catalog project are welcome and encouraged. Please see the [CONTRIBUTING.md](CONTRIBUTING.md) file for more information on how to contribute to the project.
