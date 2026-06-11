# 📄 Product Requirements Document (PRD)  
**Project:** `font-catalog`  
**Owner:** Senior Product/Engineering Lead – Axentx  
**Date:** 2026‑06‑11  

---  

## 1. Problem Statement  

Design and development teams constantly juggle typography assets across web, mobile, and print projects. Current pain points include:  

| Symptom | Impact |
|---------|--------|
| **Fragmented font metadata** – Font files live in disparate repos, Google Fonts, or design tools. | Duplicate effort, inconsistent naming, and version drift. |
| **Manual license tracking** – Teams manually record purchase dates and renewal reminders. | Risk of legal exposure, unexpected downtime when licenses expire. |
| **Runtime errors** – Missing or miss‑typed font references cause UI glitches that surface only in production. | Lost developer productivity, degraded user experience. |
| **No single source of truth** – Designers use Sketch/Figma libraries, developers query fonts via ad‑hoc scripts. | Misalignment between design intent and implementation. |

**Result:** Teams spend ≈ 15 % of their sprint capacity on font‑related housekeeping, and legal/compliance teams incur ≈ $12k / yr in audit overhead for missed renewals.

---

## 2. Target Users & Personas  

| Persona | Role | Primary Needs |
|---------|------|---------------|
| **UI/UX Designer** | Visual design lead | Discoverable, up‑to‑date font families; exportable spec docs. |
| **Front‑end Engineer** | React/Vue/Node developer | Type‑safe, auto‑completed font references; fast lookup at build/runtime. |
| **Product Manager** | Feature owner | Visibility into license expiry dates; ability to approve renewals in one place. |
| **Design Ops / Asset Manager** | Asset governance | Centralized catalog, audit trails, bulk import/export, compliance reporting. |

---

## 3. Vision & Success Goals  

| Goal | Metric | Target (12 mo) |
|------|--------|----------------|
| **Reduce font‑related toil** | % of sprint time spent on font tasks | ≤ 5 % (down from 15 %) |
| **Eliminate license violations** | Number of missed renewals | 0 |
| **Increase developer velocity** | Avg. time to add a new font reference (incl. type‑checking) | ≤ 2 min |
| **Adoption** | Active projects using `font-catalog` (GitHub stars, internal usage) | 30+ projects / 500+ developers |
| **Reliability** | 99.9 % successful API calls for font data | ≥ 99.9 % |

---

## 4. Scope  

### 4.1 In‑Scope (Must‑Have)  

| Feature | Description | Priority |
|---------|-------------|----------|
| **Typed Font Schema** | JSON‑Schema + generated TypeScript types for families, weights, styles, and license metadata. | ★★★★★ |
| **Sanity.io Integration** | CRUD helpers that map the schema to Sanity documents; automatic sync CLI. | ★★★★★ |
| **License Lifecycle Engine** | Scheduler that flags expiring licenses (30‑day, 7‑day, 1‑day alerts) and emits webhook/Slack notifications. | ★★★★★ |
| **CLI Toolkit** | `font-catalog sync` (push/pull), `validate` (schema lint), `generate` (Markdown docs). | ★★★★☆ |
| **Typed Client Library** | Runtime‑safe API (`getFontFamily`, `listFonts`, `searchByStyle`) for React/Vue/Node consumption. | ★★★★☆ |
| **Documentation Generator** | Auto‑generate designer‑friendly Markdown (family overview, usage examples, license terms). | ★★★☆☆ |
| **Caching Layer** | In‑memory + optional Redis cache for lookup < 50 ms, with TTL invalidation on sync. | ★★★☆☆ |
| **CI/CD Integration** | GitHub Action that validates schema, runs unit tests, and publishes the CLI as a release asset. | ★★★☆☆ |

### 4.2 Out‑of‑Scope (Will Not Be Delivered in MVP)  

| Feature | Reason |
|---------|--------|
| **WYSIWYG Font Preview UI** | Requires a separate front‑end app; will be explored in a later phase. |
| **Multi‑CMS support (Contentful, Strapi, etc.)** | Focus on Sanity as the canonical source for the first release. |
| **Automated font file hosting / CDN** | Font files remain stored in existing asset pipelines; catalog only tracks metadata. |
| **AI‑driven font pairing recommendations** | Outside core problem of cataloging & compliance. |
| **Mobile SDKs (iOS/Android native)** | Initial target is web/Node; native SDKs can be built on top of the TypeScript client later. |

---

## 5. Key Features – Detailed Requirements  

### 5.1 Typed Font Schema  

* **Requirement 5.1.1** – Define a JSON‑Schema (`schema/font.schema.json`) covering:  
  * `familyName` (string, required)  
  * `weights` (enum: 100‑900)  
  * `styles` (enum: normal, italic, oblique)  
  * `files` (array of objects: `url`, `format`, `sizeKB`)  
  * `license` (object: `type`, `purchaseDate`, `expiryDate`, `renewalUrl`)  
* **Requirement 5.1.2** – Generate matching TypeScript interfaces (`src/schema/types.ts`) via `json-schema-to-typescript`.  
* **Requirement 5.1.3** – Enforce schema validation on every `sync` operation; CI must fail on schema drift.

### 5.2 Sanity.io Integration  

* **Requirement 5.2.1** – Map each font family to a Sanity document type `fontFamily`.  
* **Requirement 5.2.2** – Provide CRUD helpers (`src/sanity/client.ts`) that expose `createFamily`, `updateFamily`, `deleteFamily`, `fetchFamily`.  
* **Requirement 5.2.3** – Leverage Sanity’s GraphQL API for read‑only queries; batch fetch all
