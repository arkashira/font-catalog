# STORIES.md

## Epic 1 – Schema & Types  
**Goal:** Establish a robust, type‑safe foundation for font metadata.

| # | User Story | Acceptance Criteria |
|---|-------------|---------------------|
| 1 | **As a developer, I want a JSON‑Schema for font families, so that I can validate data before it reaches Sanity.** | • `schema/fontFamily.schema.json` exists and validates sample data.<br>• Validation errors are returned as a list of messages. |
| 2 | **As a developer, I want TypeScript interfaces generated from the JSON‑Schema, so that I can use them throughout the codebase.** | • `src/schema/types.ts` contains `FontFamily`, `FontWeight`, `FontStyle`, `License` types.<br>• All CLI and API modules import these types without type errors. |
| 3 | **As a QA engineer, I want unit tests for the schema validation logic, so that regressions are caught early.** | • Jest tests cover valid and invalid payloads.<br>• Test coverage ≥ 90% for `src/schema/validation.ts`. |

---

## Epic 2 – Sanity Integration  
**Goal:** Enable seamless CRUD operations with Sanity’s GraphQL API.

| # | User Story | Acceptance Criteria |
|---|-------------|---------------------|
| 4 | **As a Sanity admin, I want helper functions that map our schema to Sanity document types, so that I can create and update fonts without writing raw GraphQL.** | • `src/sanity/documents.ts` defines `createFontFamilyDoc`, `updateFontFamilyDoc`.<br>• Functions return the created/updated document ID. |
| 5 | **As a developer, I want a GraphQL client wrapper that automatically injects the Sanity token, so that I can focus on business logic.** | • `src/sanity/client.ts` exposes `query<T>(query: string, variables?: any): Promise<T>`.<br>• Client throws a clear error if the token is missing. |
| 6 | **As a product owner, I want to see a preview of the Sanity schema in the repo, so that stakeholders can review it.** | • `sanity/schemaPreview.md` contains a rendered view of the document structure.<br>• Updated automatically on each schema change. |

---

## Epic 3 – License Lifecycle  
**Goal:** Automate license expiry monitoring and renewal notifications.

| # | User Story | Acceptance Criteria |
|---|-------------|---------------------|
| 7 | **As a designer, I want the CLI to flag fonts with licenses expiring within 30 days, so that I can act before they become unusable.** | • `font-catalog sync` outputs a table of expiring licenses.<br>• Flags are color‑coded (e.g., red for <7 days). |
| 8 | **As a developer, I want a scheduler that runs daily and sends an email to the license owner, so that renewals are handled automatically.** | • Scheduler uses `node-cron` and runs `npm run license:notify`.<br>• Email payload includes font name, expiry date, and renewal link. |
| 9 | **As a QA engineer, I want integration tests for the license notification workflow, so that I can verify email content.** | • Tests mock the email service and assert the correct subject/body.<br>• Test covers edge cases (no expiry, already renewed). |

---

## Epic 4 – CLI Tooling  
**Goal:** Provide a user‑friendly command‑line interface for common tasks.

| # | User Story | Acceptance Criteria |
|---|-------------|---------------------|
| 10 | **As a developer, I want a `font-catalog sync` command that pulls local font files and syncs metadata to Sanity, so that the catalog stays up‑to‑date.** | • Command reads `fonts/` directory, extracts metadata, and upserts into Sanity.<br>• CLI shows progress bar and summary of created/updated docs. |
| 11 | **As a designer, I want a `font-catalog validate` command that checks all font files against the schema, so that I can catch errors early.** | • Command outputs a list of invalid files with reasons.<br>• Exits with code 1 if any validation fails. |
| 12 | **As a developer, I want a `font-catalog generate` command that creates Markdown docs from the schema, so that designers can reference usage guidelines.** | • Generates `docs/fontCatalog.md` with tables for families, weights, styles, and license info.<br>• Markdown is lint‑clean and passes `markdownlint`. |

---

## Epic 5 – Typed API  
**Goal:** Expose a type‑safe client for consuming font data in front‑end projects.

| # | User Story | Acceptance Criteria |
|---|-------------|---------------------|
| 13 | **As a front‑end developer, I want a `useFontCatalog()` hook that returns a memoized list of fonts, so that I can render typography options efficiently.** | • Hook uses React Query to fetch data.<br>• Returned data matches `FontFamily[]` type. |
| 14 | **As a Vue developer, I want an equivalent composable `useFontCatalog()` that works with Vue 3 Composition API, so that I can reuse the same logic.** | • Composable returns `ref<FontFamily[]>` and handles loading/error states.<br>• TypeScript types are enforced. |
| 15 | **As a Node.js backend engineer, I want a serverless function that returns the font catalog as JSON
