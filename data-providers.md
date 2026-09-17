# HRTech Data Providers & Infrastructure

> The data layer that powers the entire Talent Acquisition stack — from candidate enrichment and job posting intelligence to employment verification and skills taxonomies.

**Maintained by [NinjaHire](https://ninjahire.co)**

Most HR tech buying decisions focus on the application layer (ATS, CRM, sourcing tools). But underneath every sourcing platform, background check system, and AI recruiter is a set of data providers and infrastructure vendors that make it work. This document maps that layer.

---

## Table of Contents

- [Person & Professional Profile APIs](#1-person--professional-profile-apis)
- [Labor Market Intelligence](#2-labor-market-intelligence)
- [Web Data Infrastructure](#3-web-data-infrastructure)
- [Employment Verification & Payroll Data](#4-employment-verification--payroll-data)
- [Skills & Taxonomy Data](#5-skills--taxonomy-data)
- [Company & Funding Signal Data](#6-company--funding-signal-data)
- [How These Layers Connect](#how-these-layers-connect)
- [Healthcare Data Sources →](./healthcare-data-sources.md) — NPI registry, state nursing/medical boards (all 50 states), commercial HCP datasets
- [Resume Parsing & Matching →](./resume-parsing-matching.md) — Parsing APIs (RChilli, Affinda, HireAbility, Klippa), matching platforms, acquisition log, LLM-native parsing

---

## 1. Person & Professional Profile APIs

These vendors aggregate public professional data (LinkedIn, resumes, social profiles) and deliver it via API for candidate enrichment, sourcing, and deduplication inside ATS and CRM tools.

| Vendor | Database Size | Delivery | Pricing Model | Notes |
|--------|--------------|----------|---------------|-------|
| [People Data Labs (PDL)](https://peopledatalabs.com) | 1.5B+ person profiles, 200M+ companies | API, bulk files | Pay-per-call / enterprise | Largest person-level enrichment API; co-op model aggregates data from thousands of sources |
| [Coresignal](https://coresignal.com) | 500M+ employee profiles, 399M+ job postings | API, flat file | Subscription | Best for data freshness and LinkedIn-sourced professional data; strong on company headcount tracking |
| [Proxycurl](https://nubela.co) | Real-time LinkedIn scraping | API | $0.01/profile pay-as-you-go | LinkedIn filed federal lawsuit Jan 2026 — monitor compliance risk |
| [Crustdata](https://crustdata.com) | Company + employee intelligence | API | Subscription | Real-time headcount, hiring signals, org chart data; fast-growing competitor to PDL and Coresignal |
| [Datagma](https://datagma.com) | Person + company enrichment | API | Pay-as-you-go | Email finder, phone, LinkedIn; popular with EU-based recruiting teams (GDPR-aware) |
| [Harmonic.ai](https://harmonic.ai) | Company signals | API, dashboard | Subscription | Tracks hiring velocity, funding events, headcount changes in real time; used by investors and sourcing teams |
| [Clearbit](https://clearbit.com) | B2B company + person data | API | Subscription | Real-time form fill, lead scoring, candidate enrichment; acquired by HubSpot 2024 |
| [Diffbot](https://diffbot.com) | Web knowledge graph | API | Subscription | AI web extraction; builds structured org charts and employee profiles from public web at scale |
| [FullContact](https://fullcontact.com) | Person identity graph | API | Subscription | Matches email/phone to professional profiles; used for candidate enrichment and deduplication |

### Use Cases in HRTech
- **ATS enrichment** — Auto-populate candidate records from email or LinkedIn URL
- **Outreach personalization** — Enrich sourced profiles with current title, company, contact info
- **Deduplication** — Merge duplicate candidate records across databases
- **Pipeline scoring** — Augment candidate records with seniority, tenure, and career trajectory signals

---

## 2. Labor Market Intelligence

These vendors provide macro-level data on workforce supply and demand: job postings, skills in-demand, salary benchmarks, talent flows, and competitive hiring intelligence.

| Vendor | Coverage | Data Types | Delivery | Notes |
|--------|----------|-----------|----------|-------|
| [Lightcast](https://lightcast.io) | 165 countries, 99% of world GDP | Job postings, skills taxonomy (50K+), salary benchmarks, workforce supply/demand | API, dashboards, data feeds | Formed by Emsi + Burning Glass Technologies merger (2021). Industry standard for skills data. Powers Workday, LinkedIn, and 500+ HR platforms |
| [Revelio Labs](https://reveliolabs.com) | Global | 1.1B+ profiles, job postings, career transitions, salary, sentiment, layoffs (COSMOS dataset) | API, data feed, dashboard | Updated weekly. Used by investors, hedge funds, and enterprise HR teams. Available via WRDS (Wharton) |
| [TalentNeuron](https://talentneuron.com) | Global | Labor market demand, talent supply, competitive hiring benchmarks | API, recurring exports | Gartner-owned. Up to 4 years historical access. Enterprise-grade |
| [LinkUp](https://linkup.com) | Global | Job postings sourced exclusively from company career sites | API, data feed | Cleaner signal than aggregated boards — reflects actual employer intent. Used by economists and hedge funds |
| [Draup](https://draup.com) | Global | Talent supply, demand, skills mapping, peer benchmarking | Dashboard, exports | AI-powered. Built for Fortune 500 workforce and location strategy |
| [Claro Analytics](https://claroanalytics.com) | US + Global | Job postings, professional profiles, diversity signals, compensation | API | Real-time. Integrates with HRIS and TA platforms |

### Use Cases in HRTech
- **Location strategy** — Which city has the most Python engineers at the right compensation?
- **Competitive benchmarking** — How fast is Competitor X hiring in your target function?
- **Workforce planning** — Model future talent supply/demand for a given skill or role
- **Recruiter enablement** — Give recruiters live market data inside their ATS

---

## 3. Web Data Infrastructure

These vendors provide the plumbing for collecting data from the public web at scale — proxy networks, headless browsers, scraping APIs, and web extraction tools.

| Vendor | Infrastructure Type | Scale | Notes |
|--------|-------------------|-------|-------|
| [Bright Data](https://brightdata.com) | Residential proxy network + datasets | 400M+ IPs, 195 countries | World's largest legitimate residential proxy network. Also sells pre-collected datasets (job postings, LinkedIn profiles, company data) |
| [Oxylabs](https://oxylabs.io) | Proxy network + scraper APIs | 100M+ residential IPs | Enterprise-grade. Specific scraper APIs for LinkedIn, Indeed, Glassdoor |
| [Apify](https://apify.com) | Web scraping platform | Cloud-based | Marketplace of ready-made scrapers (Actors) for HR data sources. API-first. Used by smaller HR tech vendors |
| [Zyte](https://zyte.com) | Managed scraping + proxy | Enterprise | Built on Scrapy (open source). Handles rendering, CAPTCHAs, and anti-bot detection |
| [ScraperAPI](https://scraperapi.com) | Proxy + headless browser API | Mid-scale | Simple API for job board and profile scraping. Handles IP rotation automatically |

### Who Uses This Layer
- **Job posting aggregators** (Indeed, Appcast) — to collect postings from company career sites
- **Sourcing platforms** (hireEZ, Findem, SeekOut) — to index public professional profiles
- **Labor market intelligence vendors** (Lightcast, Revelio) — to collect job postings at scale
- **AI recruiting startups** — to build proprietary training datasets

---

## 4. Employment Verification & Payroll Data

These vendors connect HR, lending, and background check workflows to verified employment and income records — either from employer-contributed databases or direct payroll connectivity.

| Vendor | Approach | Coverage | Use Case | Notes |
|--------|----------|----------|----------|-------|
| [The Work Number (Equifax)](https://theworknumber.com) | Employer-contributed database | 839M+ employee records, 5M+ employers | Employment and income verification for background checks and lending | FCRA-compliant. Dominant market position. Data contributed by ADP, Workday, and most major payroll processors |
| [Argyle](https://argyle.com) | Consumer-permissioned payroll API | 150+ payroll providers | Real-time income/employment verification for hiring and lending | Direct-source data. No database staleness. Strong FCRA compliance |
| [Truework](https://truework.com) | Multi-method waterfall | Wide coverage | Employment verification for background check firms | Waterfall: instant DB → payroll connection → credentialed human outreach |
| [Pinwheel](https://pinwheelapi.com) | Consumer-permissioned payroll API | 1,500+ payroll integrations | Income verification, direct deposit switching, earned wage access | Strong in banking/lending; increasingly used in background check workflows |
| [Atomic](https://atomicfi.com) | Payroll connectivity API | 450+ payroll systems | Income verification, direct deposit switching, payroll data access | Embedded financial infrastructure layer for workforce platforms |

### Use Cases in HRTech
- **Background check firms** — Verify past employment dates and income automatically
- **Staffing firms** — Verify contractor pay history and employment records
- **Onboarding** — Automate direct deposit setup and payroll connectivity for new hires
- **EWA (Earned Wage Access)** — Enable real-time wage access for hourly workers

---

## 5. Skills & Taxonomy Data

These vendors provide standardized skills ontologies and occupation frameworks — the shared language that allows ATS, LMS, and workforce planning tools to match people to roles.

| Vendor | Skills Count | Coverage | Access | Notes |
|--------|-------------|----------|--------|-------|
| [Lightcast Open Skills](https://lightcast.io/open-skills) | 50,000+ skills | Global, multilingual | API, open license | Industry standard. Powers Workday, LinkedIn, Greenhouse, and hundreds of HR platforms. Updated from real job postings |
| [ESCO](https://esco.ec.europa.eu) | 13,000+ skills, 13,890 occupations | 28 EU languages | Free API | European Commission standard. Required for EU public sector HR systems |
| [O*NET (US DOL)](https://onetcenter.org) | 1,000+ occupations with 200+ data elements | US | Free API | US Department of Labor standard. Foundation for US labor market research and career pathing tools |
| [Workday Skills Cloud](https://workday.com) | 180M+ data points | Workday ecosystem | Embedded in Workday HCM | AI-inferred skills from Workday customer data. Maps employees to adjacent skills and roles |

---

## 6. Company & Funding Signal Data

These vendors surface company-level signals — funding events, headcount growth, tech stack, and buyer intent — that help TA teams and HR vendors time their outreach.

| Vendor | Signal Type | Use Case |
|--------|------------|----------|
| [Crunchbase](https://crunchbase.com) | Funding, investors, headcount, news | TA teams target companies after Series A/B raises; HR vendors identify new customers |
| [PitchBook](https://pitchbook.com) | Private markets data, deal flow, cap tables | Exec search and enterprise TA teams time outreach to funding cycles |
| [Harmonic.ai](https://harmonic.ai) | Real-time hiring velocity, funding signals, org changes | Sourcing teams identify fast-growing target companies before competitors |
| [Bombora](https://bombora.com) | B2B intent data (what companies are researching) | HR vendors identify companies actively evaluating their category |
| [G2 Buyer Intent](https://g2.com/for-sellers/buyer-intent) | Software comparison activity on G2 | HR vendors see which companies are comparing them vs. competitors |

---

## How These Layers Connect

```
┌─────────────────────────────────────────────────────────────────┐
│                    HR APPLICATION LAYER                          │
│         ATS │ CRM │ Sourcing │ Background Checks │ Analytics    │
└─────────────────────┬───────────────────────────────────────────┘
                      │ APIs / Webhooks / Data Feeds
┌─────────────────────▼───────────────────────────────────────────┐
│                    HR DATA LAYER                                  │
│                                                                   │
│  Person APIs      Labor Market     Web Infrastructure            │
│  (PDL, Coresignal, (Lightcast,     (Bright Data,                │
│   Crustdata)       Revelio Labs,    Oxylabs, Apify)             │
│                    LinkUp)                                        │
│                                                                   │
│  Employment        Skills &         Company Signals              │
│  Verification      Taxonomy         (Crunchbase,                 │
│  (Work Number,     (Lightcast,      Harmonic.ai,                 │
│   Argyle,          ESCO, O*NET)     Bombora)                     │
│   Truework)                                                       │
└───────────────────────────────────────────────────────────────────┘
```

Most HR tech vendors are consumers of multiple data layers simultaneously. For example:
- **NinjaHire** uses person profile APIs for candidate enrichment + labor market intelligence for salary benchmarking + skills taxonomy for job-to-candidate matching
- **Background check firms** (Checkr, Sterling) use The Work Number for employment verification + web infrastructure for public record collection
- **Sourcing platforms** (hireEZ, SeekOut) use web infrastructure to index profiles + person APIs for contact enrichment

---

## Contributing

Know a data provider we missed? Submit a PR with:
- Vendor name and URL
- Category (from the 6 above)
- Database size or coverage scope
- Primary use case in HRTech
- Access model (API, bulk file, dashboard)

---

## Related Resources

### In this repo
- [HRTech Landscape](./README.md) — Full 1,500+ vendor taxonomy across 44 categories
- [Healthcare Data Sources](./healthcare-data-sources.md) — NPI registry, state nursing/medical boards, commercial HCP datasets
- [Global Job Board Directory](./job-boards.md) — 4,300+ boards with HAPI Marketplace pricing and distribution API reference
- [Resume Parsing & Matching](./resume-parsing-matching.md) — Parsing APIs, semantic matching platforms, acquisition log

### Related repos
- [Autonomous Recruiter](https://github.com/ninjahire/autonomous-recruiter) — NinjaHire's MCP server wires person profile APIs, skills taxonomy, and employment verification directly into the recruiting workflow
- [Awesome Recruiter Tools](https://github.com/ninjahire/awesome-recruiter-tools) — AI prompts and playbooks for sourcing, screening, and outreach
- [Recruitment Taxonomy](https://github.com/ninjahire/recruitment-taxonomy) — Standard definitions for data terms used across HRTech: skills taxonomy, labor market data, enrichment

### NinjaHire
[NinjaHire](https://ninjahire.co) integrates with person profile APIs (Apollo, ZoomInfo, Lusha), NPI/NPPES registries for healthcare, and labor market data to power autonomous sourcing and candidate enrichment — without manual data lookup. [Get started free →](https://app.ninjahire.co/auth/signup)

---

**Maintained by [NinjaHire](https://ninjahire.co)** — Autonomous AI Recruiter for staffing teams and high-volume hiring operations.

[![NinjaHire](https://img.shields.io/badge/Maintained%20by-NinjaHire-brightgreen)](https://ninjahire.co)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
