# BMC.md – **font‑catalog**

---

## 1. Value Proposition
| What we deliver | Why it matters |
|-----------------|----------------|
| **Typed, schema‑first font catalog** – 100 % TypeScript‑typed definitions for every font family, weight, style, and license. | Eliminates runtime font‑lookup errors and speeds up dev onboarding. |
| **License‑lifecycle management** – Automated expiry detection, renewal notifications, and audit trails. | Reduces legal risk and operational overhead for design teams. |
| **Sanity‑native integration** – CRUD helpers map directly to Sanity documents; data lives in a single source of truth. | No custom backend, instant sync with existing content pipelines. |
| **Performance‑optimized API** – Lazy‑loaded, cached font lists with < 50 ms lookup latency. | Guarantees snappy UI rendering on web & mobile. |
| **CLI & docs generator** – `font-catalog sync/validate/generate` + auto‑generated Markdown style guide. | Empowers designers to stay aligned and developers to ship faster. |

---

## 2. Customer Segments
| Primary | Secondary |
|---------|-----------|
| **UI/UX design teams** at SaaS, e‑commerce & digital agencies that maintain large typeface libraries. | **Front‑end engineering squads** building design‑system libraries (React, Vue, Angular). |
| **Product managers** needing compliance visibility for font licenses. | **Freelance designers** who need a portable, version‑controlled font inventory. |
| **Design system maintainers** (e.g., Atlassian, Shopify) that require a single source of truth across products. | **Headless‑CMS operators** already using Sanity.io and looking to extend its data model. |

---

## 3. Channels
| Channel | Tactics |
|---------|---------|
| **Open‑source repo (GitHub)** – README, badges, issue templates, contribution guide. | SEO‑optimized README, showcase demos, star‑driven community growth. |
| **Sanity Marketplace / Integrations** – Publish as a Sanity plugin. | Joint webinars with Sanity, cross‑promo in Sanity blog. |
| **Developer communities** – Hacker News, Reddit r/webdev, Dev.to, Twitter/X. | Blog posts (“How to avoid font‑license headaches”), short video demos. |
| **Design system conferences & meet‑ups** – Live coding sessions. | Sponsor talks, provide swag (e.g., “Font‑Catalog Starter Kit”). |
| **Paid SaaS add‑on** – Hosted licensing‑audit service & premium support. | Direct sales outreach to enterprise design‑system owners. |

---

## 4. Revenue Streams
| Stream | Description | Pricing Model |
|--------|-------------|---------------|
| **Enterprise SaaS add‑on** – Hosted license‑expiry monitoring, audit logs, SSO, SLA. | Tiered subscription (Starter $49/mo, Pro $199/mo, Enterprise custom). |
| **Premium support & consulting** – Migration, custom schema extensions, CI/CD integration. | Hourly rate ($250/h) or retainer packages. |
| **Marketplace royalties** – If listed as a Sanity plugin, a % of paid Sanity plans. | 5 % of plan revenue (standard Sanity partner terms). |
| **Training & certification** – Workshops, certification for “Font‑Catalog Architects”. | One‑off fees ($399 per workshop) or bundle with SaaS tier. |
| **Open‑source sponsorship** – GitHub Sponsors, OpenCollective. | Voluntary contributions, tiered perks (early‑access, branding). |

---

## 5. Cost Structure
| Category | Typical Monthly Cost | Notes |
|----------|----------------------|-------|
| **Cloud hosting (optional SaaS)** | $150 – $500 (AWS Lambda / Vercel) | Scales with number of monitored licenses. |
| **Sanity.io plan (team tier)** | $99 – $399 | Required for production data store. |
| **Developer salaries (core team)** | $20k – $35k per engineer | 2‑3 senior TS engineers + 1 PM. |
| **CI/CD & tooling** | $50 – $100 | GitHub Actions, code‑coverage services. |
| **Marketing & community** | $500 – $1k | Content creation, ads, conference sponsorships. |
| **Legal & compliance** | $200 – $400 | License audit tooling, GDPR compliance. |
| **Support & ops** | $300 – $600 | Ticketing system, SLA monitoring. |

---

## 6. Key Resources
| Resource | Role |
|----------|------|
| **Typed schema library** (JSON‑Schema + generated TS types) | Core product – ensures type safety. |
| **Sanity integration layer** (document definitions, GraphQL helpers) | Enables zero‑backend CRUD. |
| **CLI tooling** (`sync`, `validate`, `generate`) | Automates sync & documentation pipelines. |
| **License‑lifecycle scheduler** (cron‑based, webhook alerts) | Drives compliance value. |
| **Developer community** (GitHub contributors, issue reporters) | Extends feature set & adoption. |
| **Axentx BRAIN (pgvector)** – Knowledge base for continuous improvement. | Feeds product decisions, market validation. |

---

## 7. Key Activities
| Activity | Frequency / Owner |
|----------|-------------------|
| **Schema design & evolution** | Ongoing – product lead + senior engineer. |
| **Sanity CMS sync & migration** | Per release – CI pipeline. |
| **License monitoring & alerting** | Continuous – scheduler service. |
| **CLI release & packaging** | Bi‑weekly – release engineer. |
| **Documentation generation** | On schema change – automated script. |
| **Community engagement** (issues, PR reviews) | Daily – maintainers. |
| **Enterprise sales & onboarding** | As needed – sales lead. |
| **Performance testing & benchmarking** | Per sprint – QA engineer. |

---

## 8. Key Partners
| Partner | Contribution |
|---------|--------------|
| **Sanity.io** | Headless CMS platform, GraphQL API, marketplace exposure. |
| **Font foundries / licensing aggregators** (e.g., Google Fonts, Adobe Fonts) | Source of license metadata, potential co‑marketing. |
| **Design system vendors** (Storybook, Chakra UI) | Integration hooks, joint demos. |
| **CI/CD providers** (GitHub Actions, CircleCI) | Automated testing & deployment pipelines. |
| **Legal compliance services** (e.g., Termly) | License‑expiry rule definitions, audit templates. |
| **Axentx internal BRAIN** | Continuous market validation, data‑driven roadmap. |

---

### Quick Summary
`font-catalog` delivers a **type‑safe, Sanity‑backed font inventory** with built‑in **license lifecycle automation**. It targets **design‑system teams** that need reliability and compliance, reaching them via **open‑source channels** and a **premium SaaS add‑on** for enterprises. Revenue is diversified across **subscriptions, services, and marketplace royalties**, while costs stay lean through **cloud‑native hosting** and **leveraging existing Axentx infrastructure**. This positions `font-catalog` as a **high‑margin, defensible product** that expands Axentx’s portfolio into the **design‑ops** space without overlapping existing offerings.
