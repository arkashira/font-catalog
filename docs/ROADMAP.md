# ROADMAP.md

## 📅 Vision & Scope

`font‑catalog` is a **schema‑first, type‑safe font catalog** that unifies font families, file metadata, and license lifecycles for designers and developers.  
The goal is to ship a **MVP** that delivers a reliable, developer‑friendly foundation, then iterate with feature‑rich, performance‑oriented releases that expand the ecosystem and tooling.

---

## 🚀 MVP (Must‑Have for Launch)

| # | Feature | Description | Deliverable | MVP‑Critical |
|---|---------|-------------|-------------|--------------|
| 1 | **Domain‑Specific Schema** | JSON‑Schema + TS types for families, weights, styles, licenses. | `src/schema/` + `src/schema/index.ts` | ✅ |
| 2 | **Sanity Integration** | CRUD helpers that map schema to Sanity documents. | `src/sanity/` + GraphQL client | ✅ |
| 3 | **CLI – `font‑catalog sync`** | Sync local font metadata to Sanity, validate schema. | `src/cli/` + `bin/font-catalog.js` | ✅ |
| 4 | **Typed API Client** | Exposes a type‑safe client for React/Vue/Node. | `src/api/` + `dist/` | ✅ |
| 5 | **Basic License Lifecycle** | Scheduler that flags expiring licenses (email stub). | `src/license/` + cron job | ❌ (Optional) |
| 6 | **Automated Docs Generator** | Generates Markdown docs from schema for designers. | `src/docs/` | ❌ |
| 7 | **Testing & CI** | Jest tests, linting, CI pipeline. | `tests/` + GitHub Actions | ✅ |
| 8 | **Documentation** | README, usage guide, contribution docs. | `docs/` | ✅ |

> **MVP‑Critical** items are the minimal set that must be shipped for a successful launch.  
> Items marked **❌** are optional for MVP but will be prioritized in later phases.

---

## 📦 v1 – “Foundation & Performance”

| Theme | Focus | Key Deliverables |
|-------|-------|------------------|
| **1️⃣ Core Enhancements** | Expand schema to cover advanced font metadata (variable fonts, OpenType features). | `src/schema/advanced.ts` |
| **2️⃣ License Lifecycle** | Full lifecycle: expiry alerts, renewal workflow, integration with email/Slack. | `src/license/` + `src/notifications/` |
| **3️⃣ Caching & Performance** | Lazy‑loaded font lists, in‑memory cache, CDN integration. | `src/api/cache.ts` |
| **4️⃣ Documentation & UX** | Auto‑generated docs + design‑system integration guide. | `docs/` + `src/docs/generator.ts` |
| **5️⃣ Testing & Coverage** | 90% coverage, end‑to‑end tests for CLI & API. | `tests/` + CI updates |
| **6️⃣ CI/CD** | Publish NPM package, GitHub Actions for release automation. | `release.yml` |

> **Timeline**: 3‑month sprint (Jan‑Mar 2026)

---

## 📈 v2 – “Ecosystem & Extensibility”

| Theme | Focus | Key Deliverables |
|-------|-------|------------------|
| **1️⃣ Multi‑Platform SDKs** | Native JS, TypeScript, and optional Rust bindings. | `packages/sdk/` |
| **2️⃣ UI Library** | React/Vue components that consume the catalog. | `packages/ui/` |
| **3️⃣ Analytics & Insights** | Usage metrics, license health dashboards. | `src/analytics/` |
| **4️⃣ Plugin System** | Community plugins for custom license checks, third‑party CMS. | `plugins/` |
| **5️⃣ Internationalization** | Locale‑aware font metadata, multilingual docs. | `src/i18n/` |
| **6️⃣ Security & Compliance** | GDPR‑friendly data handling, audit logs. | `src/security/` |

> **Timeline**: 4‑month sprint (Apr‑Jul 2026)

---

## 📌 Release Cadence

| Release | Date | Version | Highlights |
|---------|------|---------|------------|
| **MVP** | 2026‑01‑15 | `0.1.0` | Core schema, Sanity CRUD, CLI sync, typed API |
| **v1.0** | 2026‑03‑31 | `1.0.0` | Advanced schema, license lifecycle, caching, docs |
| **v2.0** | 2026‑07‑15 | `2.0.0` | SDKs, UI library, analytics, plugin ecosystem |

---

## 📌 Dependencies & Risks

| Category | Item | Mitigation |
|----------|------|------------|
| **Sanity** | API rate limits | Implement exponential back‑off, caching |
| **License** | Email service downtime | Fallback to Slack + webhook |
| **CI** | Build failures | Strict linting, pre‑commit hooks |
| **Community** | Plugin quality | Vetting process, documentation standards |

---

## 📌 Success Metrics

| Metric | Target | Tool |
|--------|--------|------|
| **CLI Adoption** | 80% of repo installs use `sync` | GitHub Actions usage |
| **API Coverage** | 90% unit test coverage | Jest |
| **License Alerts** | 95% of expiring licenses notified | Email/Slack |
| **Performance** | < 50 ms lookup in production
