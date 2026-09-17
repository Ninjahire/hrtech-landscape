# Resume Parsing & Talent Matching Vendors

> The AI layer that extracts structured data from resumes and scores candidate-to-job fit. Covers standalone parsing APIs, semantic matching engines, and talent intelligence platforms — including the full acquisition history that has consolidated this market.

**Maintained by [NinjaHire](https://ninjahire.co)**

---

## Table of Contents

- [Market Overview](#market-overview)
- [Resume Parsing APIs](#resume-parsing-apis)
- [Semantic Matching & Talent Intelligence](#semantic-matching--talent-intelligence)
- [ATS-Native Parsing (Built-In)](#ats-native-parsing-built-in)
- [LLM-Native Parsing (New Wave)](#llm-native-parsing-new-wave)
- [Acquisition & Consolidation Log](#acquisition--consolidation-log)
- [Independent vs. Platform-Owned](#independent-vs-platform-owned)

---

## Market Overview

Resume parsing has gone through two consolidation waves:

1. **2019–2022:** Staffing platform roll-ups. Bullhorn acquired Textkernel. Recruit Holdings (Indeed's parent) acquired Daxtra. Affinda acquired Sovren. The three largest independent parsing vendors all landed inside bigger platforms.

2. **2023–present:** LLM disruption. GPT-4-class models can extract structured data from any document format without fine-tuned parsers. New entrants are building parsing as a feature rather than a product, eroding the moat of legacy vendors.

What remains independent: RChilli, Affinda, HireAbility — plus a new generation of AI-native matching platforms (Eightfold, Skillate, Arya/Leoforce) that have expanded beyond parsing into full talent intelligence.

---

## Resume Parsing APIs

These vendors expose a parsing API that takes an unstructured resume (PDF/DOCX/HTML/TXT) and returns structured JSON — name, contact, work history, education, skills, certifications.

### Textkernel (Bullhorn)

- **Acquired by:** Bullhorn (2024)
- **Products:** Parse (resume/job parsing), Semantic Search & Match, Data Enrichment APIs, Jobfeed (job market data), Source (multi-database search)
- **Languages supported:** 70+ languages; best-in-class multilingual parsing
- **Coverage:** Used by 1,500+ customers across 40 countries; processes hundreds of millions of documents annually
- **Delivery:** REST API, bulk processing, embedded within Bullhorn ATS
- **Differentiator:** Deepest multilingual support in the market; skills ontology and normalization built in; semantic understanding of job titles and career trajectories across languages
- **Post-acquisition status:** Continues to sell as a standalone API to non-Bullhorn customers; Bullhorn is positioning it as infrastructure for the broader staffing tech ecosystem
- **Pricing:** Enterprise contract; volume-based

---

### RChilli

- **URL:** [rchilli.com](https://rchilli.com)
- **Founded:** 2010; Chandigarh, India
- **Status:** Independent
- **What it does:** Resume parsing, semantic matching, resume enrichment, job description parsing, taxonomy normalization
- **Languages supported:** 40+ languages
- **Scale:** Processes 4B+ documents annually; embedded in 50+ ATS and HRIS platforms
- **Delivery:** REST API, bulk S3/SFTP, pre-built ATS plugins (SAP SuccessFactors, Oracle, Workday, Salesforce, Zoho, Bullhorn, iCIMS, Greenhouse)
- **Differentiator:** Broadest ATS ecosystem penetration of any independent parser; very competitive pricing vs. Textkernel; strong in India/APAC markets where multilingual resume formats are complex
- **Pricing:** API calls priced per document; enterprise volume discounts; typically $0.01–$0.05/resume at scale
- **Notable:** One of very few independent parsing vendors left at scale after the consolidation wave

---

### Affinda (acquired Sovren)

- **URL:** [affinda.com](https://affinda.com)
- **Founded:** 2018; Melbourne, Australia
- **Acquired Sovren:** 2022 (Sovren was one of the oldest and most accurate parsers, founded 1996)
- **Status:** Independent (privately held)
- **What it does:** Resume parsing, job description parsing, invoice parsing, ID document parsing — document AI platform beyond just HR
- **Languages supported:** 50+ languages
- **Differentiator:** Sovren lineage gives it one of the deepest resume parsing corpora in the market; Affinda has extended into general document AI (contracts, invoices, IDs) — broader than HR-only
- **Delivery:** REST API; free tier (50 parses/month); pay-as-you-go
- **Pricing:** $0.10/parse on pay-as-you-go; enterprise volume pricing
- **Sovren legacy:** Before acquisition, Sovren was the parser embedded in many legacy ATS (BrightMove, CATS, others); Affinda maintains those integrations

---

### Daxtra Technologies (Recruit Holdings)

- **URL:** [daxtra.com](https://daxtra.com)
- **Acquired by:** Recruit Holdings (Indeed's parent company) in 2020
- **Founded:** 2002; Edinburgh, UK
- **Status:** Operating as independent subsidiary of Recruit Holdings
- **What it does:** Resume parsing (DaXtra Parser), CV management and search (DaXtra Search), semantic matching (DaXtra Match), multi-database search (DaXtra Capture)
- **Differentiator:** One of the most accurate parsers for European resume formats; strong in UK/EU staffing market; DaXtra Capture searches across multiple external databases simultaneously
- **ATS integrations:** Bullhorn, Vincere, Recruitment Plus, Itris, and most UK/EU staffing ATS
- **Post-acquisition:** Still sells commercially; acquisition by Recruit Holdings was strategic to strengthen Indeed's talent data infrastructure
- **Pricing:** Enterprise contract; volume-based per parse

---

### HireAbility

- **URL:** [hireability.com](https://hireability.com)
- **Founded:** 1999; one of the original resume parsing vendors
- **Status:** Independent
- **What it does:** Resume/CV parsing (HireAbility ALEX parser), job description parsing, resume search
- **Languages supported:** 20+ languages
- **Delivery:** REST API, on-premises deployment option
- **Differentiator:** On-premises deployment is rare in modern parsing — HireAbility still offers it for customers with data sovereignty requirements (government, defense, healthcare); very low false-positive rate on structured resumes
- **Pricing:** Per-call API pricing; on-premises licensing available

---

### Klippa

- **URL:** [klippa.com](https://klippa.com)
- **Founded:** 2015; Groningen, Netherlands
- **Status:** Independent
- **What it does:** Document AI platform — resume parsing is one use case alongside invoice processing, ID verification, and expense management
- **Languages supported:** 60+ languages; strong EU multilingual support
- **Delivery:** REST API; SDK (iOS, Android, JS)
- **Differentiator:** GDPR-native (Dutch company); strong compliance story for EU-based HR teams; not exclusively an HR vendor — horizontal document AI applied to HR
- **Pricing:** Pay-per-call; enterprise subscription

---

### OpenResume / Open Source Options

For teams that want to parse without a third-party dependency:

| Project | Language | Notes |
|---------|---------|-------|
| [pyresparser](https://github.com/OmkarPathak/pyresparser) | Python | spaCy-based NER extraction; free, self-hosted |
| [resume-parser](https://github.com/antham/resume-parser) | Go | Lightweight structured extraction |
| [Resumable](https://github.com/resume/resume.github.com) | JS | Resume schema standard (JSON Resume) |
| LLM-based (GPT-4, Claude) | Any | See [LLM-Native Parsing](#llm-native-parsing-new-wave) below |

---

## Semantic Matching & Talent Intelligence

Beyond parsing, these platforms score the fit between a candidate and a job — using semantic understanding of skills, career trajectories, seniority, and inferred capabilities (not just keyword overlap).

### Eightfold AI

- **URL:** [eightfold.ai](https://eightfold.ai)
- **Status:** Independent (Series E, ~$2B+ valuation)
- **What it does:** Full talent intelligence platform — ATS, CRM, internal mobility, workforce planning — with AI matching at the core
- **Core tech:** Deep learning model trained on 1B+ career profiles and job outcomes; infers skills from experience, not just stated skills; understands adjacent and transferable skills
- **Differentiator:** The most sophisticated talent matching AI on the market; can match candidates to jobs they haven't held yet (inferred potential); strong internal mobility use case
- **Best for:** Enterprise employers with large talent databases and complex internal mobility programs; replacing legacy ATS with AI-native infrastructure
- **Pricing:** Enterprise contract

---

### Skillate

- **URL:** [skillate.com](https://skillate.com)
- **Founded:** 2018; Bengaluru, India
- **Status:** Independent (Series A)
- **What it does:** AI-powered resume screening, matching, and candidate ranking integrated into existing ATS; also JD optimization and diversity analytics
- **How it works:** Integrates with ATS (SAP SuccessFactors, Workday, Oracle, Darwinbox) via API; scores incoming applicants and ranks shortlists automatically
- **Differentiator:** Purpose-built for integrating into existing enterprise ATS stacks rather than replacing them; strong adoption in India and Southeast Asia; good diversity analytics layer
- **Pricing:** SaaS; per-seat or per-requisition

---

### Arya by Leoforce

- **URL:** [leoforce.com](https://leoforce.com)
- **Status:** Independent
- **What it does:** AI sourcing and engagement automation; Arya is the AI agent that sources candidates from internal databases + external boards, ranks by fit, and initiates outreach
- **Differentiator:** Combines parsing + matching + outreach in a single platform; strong in staffing firms managing large candidate databases with stale records; Arya re-ranks existing ATS candidates against new jobs automatically
- **Best for:** Staffing agencies and RPO firms wanting to monetize their existing candidate database before paying for external sourcing

---

### SquarePeg

- **URL:** [squarepegmatching.com](https://squarepegmatching.com)
- **Status:** Independent
- **What it does:** Matching intelligence layer that sits on top of existing ATS; re-scores the full candidate database against every new job
- **Differentiator:** Works with any ATS without replacing it; specifically designed to surface buried candidates that slipped through keyword filters the first time

---

### MapRecruit MatchAI

- **URL:** [maprecruit.com](https://maprecruit.com)
- **Status:** Independent
- **What it does:** Talent intelligence platform with AI-powered candidate-job matching, bias reduction, and pipeline analytics
- **Best for:** Mid-market employers wanting ATS-agnostic matching intelligence

---

### Sniper AI

- **URL:** [sniper.ai](https://sniper.ai)
- **Status:** Independent; UK/EU focused
- **What it does:** AI-powered resume screening and matching; integrates with Bullhorn, Vincere, and major staffing ATS
- **Differentiator:** Built specifically for staffing firms; deep Bullhorn native integration; learns from recruiter placement history to improve match quality over time
- **Best for:** UK/EU staffing agencies on Bullhorn

---

### Harver

- **URL:** [harver.com](https://harver.com)
- **Status:** Independent (merged with Pymetrics in 2022)
- **What it does:** High-volume candidate matching and pre-employment assessment; combines behavioral science assessments (from Pymetrics) with AI-matching to rank applicants
- **Differentiator:** The only platform that combines neuroscience-based game assessments with matching; strong story for bias-reduction via validated behavioral signals rather than resume keywords
- **Best for:** Retail, logistics, BPO, hospitality — high-volume hourly hiring where resume-based matching doesn't work well
- **Pymetrics merger:** Created a more complete picture of candidate fit by layering behavioral profile data onto skills/experience matching

---

### Censia

- **URL:** [censia.com](https://censia.com)
- **Status:** Independent
- **What it does:** Talent intelligence API — takes a job description and returns ranked candidates from internal or external sources; also provides workforce diversity analytics
- **Delivery:** API-first; can plug into any ATS or sourcing tool
- **Differentiator:** API-native design makes it easy to embed into custom recruiting workflows; strong diversity analytics

---

## ATS-Native Parsing (Built-In)

Most modern ATS include basic resume parsing. Quality varies significantly.

| ATS | Parsing Technology | Quality |
|-----|-------------------|---------|
| Bullhorn | Textkernel (native, post-acquisition) | ⭐⭐⭐⭐⭐ Best-in-class |
| Workday Recruiting | Workday proprietary + Skills Cloud | ⭐⭐⭐⭐ Good |
| SAP SuccessFactors | Multiposting + RChilli integration | ⭐⭐⭐⭐ Good |
| iCIMS | iCIMS proprietary + optional Textkernel | ⭐⭐⭐ Solid |
| Greenhouse | Greenhouse proprietary | ⭐⭐⭐ Solid |
| Lever | Lever proprietary | ⭐⭐⭐ Solid |
| Oracle Taleo | Oracle proprietary | ⭐⭐ Aging |
| SmartRecruiters | SmartRecruiters proprietary | ⭐⭐⭐ Solid |
| Vincere | Daxtra (native integration) | ⭐⭐⭐⭐ Good |
| JobAdder | RChilli (integration) | ⭐⭐⭐⭐ Good |

---

## LLM-Native Parsing (New Wave)

Since GPT-4 (2023), LLM-based document extraction has matured to the point where a well-prompted model can match or exceed fine-tuned parsers for English-language resumes.

### Why LLMs change the market

Traditional parsers (Textkernel, RChilli, Sovren) rely on pattern matching, NER models, and rule-based fallbacks trained on large resume corpora. LLMs handle:
- Non-standard resume layouts that break regex/NER approaches
- Inferred context ("led a team of 8" → seniority signal, not a stated title)
- Career narrative understanding ("moved from IC to manager to VP in 5 years")

### Vendors building on LLMs

| Vendor | Approach | Notes |
|--------|---------|-------|
| [Affinda](https://affinda.com) | GPT-4 augmenting legacy parser | Hybrid — LLM handles edge cases, legacy handles high-volume |
| [Skima AI](https://skima.ai) | LLM-native resume screening | Purpose-built for AI-first recruitment |
| [Webcand](https://webcand.com) | LLM parsing + auto-invite to interview | End-to-end automation |
| [CVViZ](https://cvviz.com) | AI resume screening + ATS | Screening-focused, integrates into existing workflows |
| [Paradox (Olivia)](https://paradox.ai) | Conversational AI that extracts resume data mid-conversation | No resume upload required — collects structured data through chat |
| [NinjaHire](https://ninjahire.co) | LLM orchestration via MCP | Structured extraction as one step in autonomous recruiting workflow |

### Roll-your-own with foundation models

For teams with engineering resources, direct LLM parsing via API is viable:

```python
# Claude / GPT-4 resume parsing pattern
prompt = """
Extract the following structured data from this resume as JSON:
{
  "name": "",
  "email": "",
  "phone": "",
  "location": {"city": "", "state": "", "country": ""},
  "current_title": "",
  "years_experience": 0,
  "skills": [],
  "work_history": [{"company": "", "title": "", "start": "", "end": "", "summary": ""}],
  "education": [{"school": "", "degree": "", "field": "", "year": 0}],
  "certifications": []
}

Resume:
{resume_text}
"""
```

**Cost comparison:** At Claude Haiku 4.5 pricing, parsing a 1-page resume costs ~$0.001 — 10–50× cheaper than Textkernel/RChilli at scale. Accuracy is comparable for English; significantly worse for non-Latin scripts and highly formatted PDFs.

---

## Acquisition & Consolidation Log

| Year | Event | Impact |
|------|-------|--------|
| 2020 | **Recruit Holdings acquires Daxtra** | Daxtra embedded into Indeed's talent infrastructure; continues as commercial product |
| 2021 | **Emsi + Burning Glass merge → Lightcast** | Skills taxonomy and labor market intelligence consolidated; both were data suppliers to parsing vendors |
| 2022 | **Affinda acquires Sovren** | Two of the oldest English-language parsers combined; Sovren's 25-year corpus absorbed into Affinda |
| 2022 | **Harver merges with Pymetrics** | Assessment + matching combined; behavioral science layer added to resume-based matching |
| 2022 | **Entelo acquired by Sterling** | AI sourcing absorbed into background check platform |
| 2024 | **Bullhorn acquires Textkernel** | Largest remaining independent parser goes inside the dominant staffing ATS; Textkernel's multilingual edge now a Bullhorn moat |

---

## Independent vs. Platform-Owned

| Vendor | Status | Owned By | Sells Standalone API? |
|--------|--------|---------|----------------------|
| Textkernel | Platform-owned | Bullhorn | Yes (non-Bullhorn customers) |
| Daxtra | Platform-owned | Recruit Holdings (Indeed) | Yes |
| Sovren | Absorbed | Affinda | Via Affinda |
| RChilli | **Independent** | — | Yes |
| Affinda | **Independent** | — | Yes |
| HireAbility | **Independent** | — | Yes |
| Klippa | **Independent** | — | Yes |
| Eightfold AI | **Independent** | — | Platform only (not API) |
| Skillate | **Independent** | — | Platform only |
| Arya / Leoforce | **Independent** | — | Platform only |
| Harver / Pymetrics | **Independent** | — | Platform only |
| Sniper AI | **Independent** | — | API + platform |
| Censia | **Independent** | — | API + platform |

**Bottom line:** For a standalone parsing API that isn't locked to a specific ATS ecosystem, the remaining independent options are **RChilli**, **Affinda**, **HireAbility**, and **Klippa**. Textkernel and Daxtra are technically still available as APIs but have platform loyalties that affect roadmap and pricing decisions.

For **matching intelligence** (not just parsing), the independent market is healthier: Eightfold, Skillate, Arya/Leoforce, Harver, and Sniper AI all remain independent and compete on matching accuracy rather than just extraction.

---

## Related Resources

### In this repo
- [HRTech Landscape](./README.md) — Full 1,500+ vendor taxonomy across 44 categories
- [HRTech Data Providers](./data-providers.md) — Person profile APIs, skills taxonomy, employment verification
- [Global Job Board Directory](./job-boards.md) — 4,300+ boards with distribution API reference

### Related repos
- [Autonomous Recruiter](https://github.com/ninjahire/autonomous-recruiter) — NinjaHire's MCP server uses LLM-native resume parsing as part of the autonomous screening workflow
- [Awesome Recruiter Tools](https://github.com/ninjahire/awesome-recruiter-tools) — Resume screening prompts, evaluation frameworks, and candidate-vs-JD scoring chains
- [Recruitment Taxonomy](https://github.com/ninjahire/recruitment-taxonomy) — Standard definitions for parsing, matching, screening, and skills taxonomy terms

### NinjaHire
[NinjaHire](https://ninjahire.co) uses LLM-native resume parsing (Claude/GPT-4) as part of its autonomous recruiting workflow — extracting structured data, matching against job requirements, and scoring candidates without a dedicated parsing API. [See how it works →](https://github.com/ninjahire/autonomous-recruiter)

---

**Maintained by [NinjaHire](https://ninjahire.co)** — Autonomous AI Recruiter for staffing teams and high-volume hiring operations.

[![NinjaHire](https://img.shields.io/badge/Maintained%20by-NinjaHire-brightgreen)](https://ninjahire.co)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
