# Global Job Board Directory

> A comprehensive directory of 4,300+ job boards across 60+ countries — plus the distribution APIs and programmatic platforms that sit between your ATS and those boards.

**Maintained by [NinjaHire](https://ninjahire.co)**

Job boards sit at the intersection of recruitment marketing and talent acquisition. This directory covers every major distribution channel — from global giants like LinkedIn and Indeed down to specialty boards for neurosurgeons and Dutch nursing associations — plus the middleware layer (multiposting APIs, programmatic advertising platforms) that powers modern job distribution at scale.

---

## Table of Contents

- [Job Distribution APIs & Programmatic Platforms](#job-distribution-apis--programmatic-platforms)
- [Platform Overview: HAPI](#platform-overview-hapi)
- [Tier-1 Global Job Boards](#tier-1-global-job-boards)
- [United States — By Industry](#united-states)
- [Europe — By Country](#europe)
- [International / Multi-Region](#international--multi-region)
- [APAC, LATAM & MENA](#apac-latam--mena)
- [Healthcare Job Boards](#healthcare-job-boards)
- [Diversity & Inclusion Boards](#diversity--inclusion-boards)
- [Full Machine-Readable Data](#full-data)

---

## Job Distribution APIs & Programmatic Platforms

These vendors sit between your ATS and the job boards — handling multiposting, feed management, programmatic spend optimization, and compliance distribution. There are two distinct categories:

| Category | What It Does | Key Vendors |
|----------|-------------|-------------|
| **Multiposting / Distribution APIs** | Single API or integration that pushes a job to hundreds or thousands of boards simultaneously | Broadbean, HAPI, eQuest, Idibu, Multiposting (SAP) |
| **Programmatic Job Advertising** | Performance-based spend optimization — AI allocates budget across boards to hit cost-per-applicant or cost-per-hire targets | Appcast, Joveo, PandoLogic, Talroo, Recruitics |

---

### Multiposting & Distribution APIs

#### Broadbean (Bullhorn Broadbean)

- **URL:** [broadbean.com](https://broadbean.com)
- **Owner:** Acquired by Bullhorn in 2019
- **Coverage:** 6,000+ job boards globally; strong in UK, EU, US, APAC
- **How it works:** Integrates natively into Bullhorn ATS; post once, distribute to any combination of boards from a single interface. Supports free boards, sponsored boards, and niche sites
- **Pricing model:** Subscription + per-posting credits; enterprise contracts for high-volume staffing
- **Best for:** Staffing firms on Bullhorn; agencies doing high-volume multiposting across UK/EU/US
- **ATS integrations:** Bullhorn (native), Vincere, JobAdder, and most major ATS via API
- **Notable:** One of the oldest and most widely-used distribution platforms in the staffing industry; deep board relationships especially in UK and ANZ markets

#### HAPI

- **Coverage:** 4,300+ job boards; strongest in EU (NL, DE, BE, FR) and expanding globally
- **How it works:** REST API — a single `/jobs` POST distributes to any combination of boards in the catalog. Supports both pre-negotiated Marketplace pricing and Bring Your Own Contract (BYOC) channels
- **Pricing model:** Pay-per-posting via Marketplace; flat API fee for BYOC channels
- **Board catalog:** See [job-boards-marketplace.json](./job-boards-marketplace.json) for the full 1,750-board Marketplace list with pricing
- **Best for:** Companies wanting API-first integration; strong EU distribution footprint
- **Direct Apply support:** Mandatory on Seek/Naukri/InfoJobs/ZipRecruiter; optional elsewhere
- **Disposition data:** Candidate status push-back supported on Indeed, InfoJobs, Naukri, ZipRecruiter

#### eQuest

- **URL:** [equest.com](https://equest.com)
- **Founded:** 1994 — one of the longest-running job distribution platforms
- **Coverage:** 50,000+ job boards, career sites, and posting destinations globally
- **How it works:** ATS-integrated distribution; bulk posting via feed or API; strong compliance and OFCCP reporting
- **Pricing model:** Subscription; volume-based enterprise contracts
- **Best for:** US enterprise employers with OFCCP compliance requirements (federal contractors must post to state job banks and diversity boards); large-scale global distribution
- **Compliance focus:** Automated posting to state workforce agencies (SWAs) — required for OFCCP-covered employers. The most comprehensive compliance distribution platform in the US market
- **ATS integrations:** Workday, SAP SuccessFactors, Oracle Taleo, iCIMS, and 100+ others

#### Idibu

- **URL:** [idibu.com](https://idibu.com)
- **Coverage:** 1,000+ job boards; strongest in UK, Ireland, and EU
- **How it works:** Multiposting platform with a browser-based interface and ATS integrations; post to multiple boards from one screen with board-specific field mapping
- **Pricing model:** Subscription per user/seat + posting credits
- **Best for:** UK and EU staffing agencies and in-house recruiters; teams that want a simple UI for multiposting without deep API work
- **ATS integrations:** Bullhorn, Vincere, Recruit CRM, Access Recruitment
- **Notable:** Strong in the UK staffing community; often compared to Broadbean for EU/UK use cases

#### Multiposting (SAP)

- **URL:** [multiposting.fr](https://multiposting.fr)
- **Owner:** Acquired by SAP; integrated into SAP SuccessFactors Recruiting
- **Coverage:** 500+ job boards in 100+ countries
- **How it works:** Embedded within SAP SuccessFactors; enterprise HR teams post directly from their SuccessFactors workflow to global boards
- **Pricing model:** Enterprise contract; bundled with SAP SuccessFactors
- **Best for:** Large enterprises on SAP SuccessFactors; global posting with multilingual support

#### DirectEmployers Association

- **URL:** [directemployers.org](https://directemployers.org)
- **Model:** Member association (not a vendor)
- **Coverage:** Jobs posted directly to member company career sites, then distributed to 1,000+ OFCCP-required state job banks and NLx (National Labor Exchange)
- **Pricing model:** Annual membership fee based on employee count
- **Best for:** US federal contractors needing OFCCP compliance without using eQuest; also used alongside eQuest for belt-and-suspenders compliance coverage

---

### Programmatic Job Advertising

These platforms optimize job posting spend algorithmically — allocating budget across boards to minimize cost-per-qualified-applicant or cost-per-hire.

#### Appcast

- **URL:** [appcast.io](https://appcast.io)
- **Owner:** Acquired by Stepstone (Axel Springer) in 2021
- **Model:** Performance-based (CPC / CPA / cost-per-hire)
- **How it works:** Single feed integration with your ATS; Appcast distributes jobs to its network of 10,000+ publishers and optimizes spend in real time based on applicant quality signals
- **Scale:** Processes 1B+ job clicks annually; used by most Fortune 500 employers
- **Best for:** High-volume enterprise hiring; reducing cost-per-applicant across a large open req portfolio
- **Notable:** The market leader in programmatic recruitment advertising; deep integrations with Workday, iCIMS, Greenhouse, Taleo

#### Joveo

- **URL:** [joveo.com](https://joveo.com)
- **Model:** Programmatic CPC / CPA; AI-driven spend optimization
- **How it works:** Connects to ATS job feed; distributes across 500+ job sites and optimizes toward job-level cost-per-hire goals using ML models
- **Differentiator:** MOJO platform — provides recruiter-level visibility into which boards deliver quality applicants for each job category and location
- **Best for:** Mid-market to enterprise employers wanting job-level programmatic control; good alternative to Appcast for companies wanting more granular analytics
- **ATS integrations:** Workday, Greenhouse, iCIMS, Lever, SmartRecruiters, Taleo

#### PandoLogic

- **URL:** [pandologic.com](https://pandologic.com)
- **Owner:** Acquired by Veritone in 2021
- **Model:** Programmatic CPC / CPA; AI autopilot
- **How it works:** pandoIQ autopilot engine analyzes historical performance data and automatically adjusts bids, pauses underperforming boards, and reallocates spend — no manual management needed
- **Best for:** Staffing firms and high-volume employers who want a fully automated "set and forget" programmatic approach; particularly strong for hourly and frontline hiring
- **Notable:** One of the earliest AI-native programmatic platforms in recruiting

#### Talroo

- **URL:** [talroo.com](https://talroo.com)
- **Model:** Cost-per-qualified-applicant (CPQA) — you only pay when a candidate meets your defined criteria
- **Focus:** Frontline, hourly, and essential workers — warehouse, logistics, healthcare aides, food service, retail
- **How it works:** Talroo's data platform matches jobs to candidates across its proprietary network; charges only when a qualified applicant applies (screening questions determine qualification)
- **Best for:** High-volume hourly hiring; employers who want performance guarantees on applicant quality

#### Recruitics

- **URL:** [recruitics.com](https://recruitics.com)
- **Model:** Managed programmatic + analytics platform
- **How it works:** Combines programmatic job advertising with analytics dashboards; manages spend across Indeed, LinkedIn, ZipRecruiter, Appcast network, and niche boards; provides recruiter-level ROI reporting
- **Best for:** Large employers who want a managed service approach to programmatic rather than self-serve; strong on reporting and attribution

#### JobTarget

- **URL:** [jobtarget.com](https://jobtarget.com)
- **Model:** Programmatic + targeted distribution
- **Focus:** Diversity recruiting and OFCCP compliance; also general programmatic
- **How it works:** Distributes to diversity-specific boards, veteran boards, disability boards, and HBCUs — in addition to mainstream programmatic optimization
- **Best for:** Organizations with DEI hiring goals or federal contractor obligations needing targeted distribution alongside performance optimization

---

### How They Stack

```
┌─────────────────────────────────────────────────────────┐
│                    ATS / HRIS                            │
│   (Workday · iCIMS · Greenhouse · Bullhorn · Taleo)     │
└──────────────┬──────────────────────────────────────────┘
               │ job feed (XML/JSON/API)
    ┌──────────▼──────────┐     ┌──────────────────────┐
    │  Multiposting APIs  │     │ Programmatic Ad Mgmt │
    │  Broadbean · HAPI   │     │ Appcast · Joveo      │
    │  eQuest · Idibu     │     │ PandoLogic · Talroo  │
    │  Multiposting (SAP) │     │ Recruitics           │
    └──────────┬──────────┘     └────────────┬─────────┘
               │                             │
    ┌──────────▼─────────────────────────────▼─────────┐
    │              Job Board Network                    │
    │  Indeed · LinkedIn · ZipRecruiter · Dice · ...   │
    │  + 4,300 specialty, regional, niche boards       │
    └───────────────────────────────────────────────────┘
```

**Key difference:** Multiposting APIs charge per posting (you control where every job goes). Programmatic platforms charge per click or applicant and decide where to spend your budget automatically.

Most large employers use **both** — multiposting for targeted specialty boards (e.g., always post nursing jobs to the American Nurses Association board) and programmatic for volume/budget optimization across general boards.

---

---

## Platform Overview: HAPI

HAPI is a job distribution API — a single integration that routes postings to thousands of job boards globally. Job boards on the platform are available under two models:

| Model | Description | # Boards |
|-------|-------------|----------|
| **Job Board Marketplace (JM)** | Pre-negotiated pricing; post without your own contract | 1,750 unique boards |
| **Bring Your Own Contract (BYOC)** | Use your existing negotiated rates; HAPI handles distribution | 2,800 unique boards |
| **Combined** | Boards available under either or both models | 4,300+ unique boards |

**Additional capabilities:**

| Feature | Description |
|---------|-------------|
| **Direct Apply** | Candidates apply directly within the job board (no redirect to ATS) — mandatory on some boards |
| **VJP (Virtual Job Post)** | HAPI-hosted job page for boards that don't support ATS redirect |
| **Disposition data sharing** | Candidate application status pushed back from the board to the source (mandatory on Indeed, InfoJobs, Naukri, ZipRecruiter) |

---

## Tier-1 Global Job Boards

These are the highest-reach channels available on HAPI, covering multiple countries and billions of monthly visitors.

| Board | Region | Direct Apply | Marketplace | BYOC | Disposition Required |
|-------|--------|-------------|------------|------|---------------------|
| [LinkedIn](https://linkedin.com) | International | Optional | Yes | Yes | No |
| [Indeed](https://indeed.com) | International | Optional | Yes | Yes | **Yes** |
| [Seek / Jobstreet / JobsDB](https://seek.com.au) | Australia / APAC | **Mandatory** | No | Yes | No |
| [Stepstone](https://stepstone.de) | Germany / Europe | Optional | In progress | — | Yes |
| [ZipRecruiter](https://ziprecruiter.com) | United States | **Mandatory** | — | — | — |
| [Monster](https://monster.com) | United States | Optional | In progress | In progress | — |
| [Talent.com](https://talent.com) | International | Optional | — | — | — |
| [Adzuna](https://adzuna.com) | International | Optional | — | — | — |
| [Jooble](https://jooble.org) | International | Optional | — | — | — |
| [Facebook Jobs](https://facebook.com/jobs) | International | Optional | — | — | — |
| [eFinancialCareers](https://efinancialcareers.com) | International | Optional | — | — | — |
| [Jobrapido](https://jobrapido.com) | International | Optional | — | — | — |
| [Naukri](https://naukri.com) | India | **Mandatory** | No | Yes | **Yes** |
| [InfoJobs](https://infojobs.net) | Spain / Italy | **Mandatory** | No | Yes | **Yes** |
| [TotalJobs](https://totaljobs.com) | United Kingdom | Optional | — | — | — |
| [CV-Library](https://cv-library.co.uk) | United Kingdom | Optional | — | — | — |
| [Reed](https://reed.co.uk) | United Kingdom | Optional | — | — | — |
| [Resume Library](https://resume-library.com) | United Kingdom | Optional | — | — | — |
| [Stepstone](https://stepstone.de) | Germany | Optional | — | — | Yes |
| [XING](https://xing.com) | Germany / DACH | Optional | — | — | — |
| [Jobware](https://jobware.de) | Germany | Optional | — | — | — |
| [Stellenanzeigen](https://stellenanzeigen.de) | Germany | Optional | — | — | — |
| [HelloWork](https://hellowork.com) | France | **Mandatory** | — | — | — |
| [Meteojob](https://meteojob.com) | France | **Mandatory** | — | — | — |
| [Bayt](https://bayt.com) | Gulf / MENA | **Mandatory** | — | — | — |
| [Kariyer](https://kariyer.net) | Turkey | **Mandatory** | — | — | — |
| [Computrabajo](https://computrabajo.com) | Latin America | **Mandatory** | — | — | — |
| [Bumeran](https://bumeran.com) | Latin America | **Mandatory** | — | — | — |
| [Work.ua](https://work.ua) | Ukraine | **Mandatory** | — | — | — |
| [DPG (Nationale Vacaturebank)](https://nationalevacaturebank.nl) | Netherlands | Optional | In progress | In progress | — |
| [Jobs.cz](https://jobs.cz) | Czech Republic | Optional | In progress | In progress | — |
| [Karriere.at / Jobs.at](https://karriere.at) | Austria | Optional | — | — | — |
| [Jobs.ch / JobCloud](https://jobs.ch) | Switzerland | Optional | — | — | — |
| [BestJobs.eu](https://bestjobs.eu) | Romania | Optional | — | — | — |
| [eJobs.ro](https://ejobs.ro) | Romania | Optional | — | — | — |

---

## United States

**352 US job boards in the HAPI Marketplace.** Breakdown by industry:

| Industry | # Boards |
|----------|---------|
| Generic / Multi-sector | 142 |
| Healthcare | 67 |
| Legal | 17 |
| Education | 16 |
| Engineering | 8 |
| Information Technology | 8 |
| Science & Research | 8 |
| Government & Public Sector | 6 |
| Automotive | 5 |
| Manufacturing | 5 |

### US — Top Generic / Multi-Sector Boards

| Board | Starting Price (USD) |
|-------|---------------------|
| Indeed | — |
| LinkedIn | — |
| ZipRecruiter | — |
| Monster | — |
| Jobget | — |
| Snagajob.com | $199 |
| Lensa | $199 |

### US — Healthcare (see [Healthcare Job Boards](#healthcare-job-boards) section for full list)

67 dedicated healthcare boards available in the US marketplace, covering nursing, surgery, radiology, cardiology, psychiatry, dental, veterinary, and more. Prices range from $159 (Marshall B. Ketchum University) to $939 (American College of Radiology Premium).

### US — Legal

| Board | Price (USD) |
|-------|------------|
| American Bar Association Career Center | — |
| Law Crossing | — |
| Lawjobs.com | — |
| Above the Law | — |

### US — Technology

| Board | Price (USD) |
|-------|------------|
| Dice | — |
| Stack Overflow Jobs | — |
| GitHub Jobs | — |
| Wellfound (AngelList) | — |

---

## Europe

### Germany (309 boards)

Germany has the largest European presence on HAPI — 309 boards covering every industry from automotive to healthcare nursing. Notable:

| Board | Industry | Price (USD) |
|-------|---------|------------|
| StepStone | Generic | — |
| XING | Generic | — |
| Jobware | Generic | — |
| Stellenanzeigen.de | Generic | — |
| HeyJobs | Generic | — |
| Deinerstertag.de | Generic (entry-level) | — |
| Jobninja.com | Multi-sector | $799 |
| Medi-karriere.de | Healthcare | $1,449 |
| arztjobs.de | Healthcare (physicians) | $1,329 |
| altenpflegejobs24.de | Healthcare (elderly care) | $1,329 |
| Krankenschwesterjobs DE | Healthcare (nursing) | $1,389 |
| Klinik.jobs | Healthcare | $519 |
| Dental Jobs | Healthcare (dental) | $869 |
| mfajobs.de | Healthcare (medical assistants) | $1,329 |
| zfajobs.de | Healthcare (dental assistants) | $1,329 |
| Jobs Medizintechnik | Healthcare (med tech) | $1,099 |
| Pharmazie.Jobs | Healthcare (pharma) | $519 |

### Netherlands (248 boards)

| Board | Industry | Price (USD) |
|-------|---------|------------|
| Nationale Vacaturebank | Generic | — |
| Intermediair | Generic | — |
| Monsterboard.nl | Generic | — |
| GeoInformatieNederland.nl | Healthcare | $379 |
| Gezondheidszorgbanen | Healthcare | $499 |
| ArtsenVacaturebank | Healthcare (physicians) | $349 |
| Esculaap | Healthcare | $239 |
| VacatureInDeZorg.nl | Healthcare | $349 |
| Ergotherapie Nederland | Healthcare (OT) | $519 |
| Farmavac | Healthcare / Pharma | $399 |
| FMT Gezondheidszorg | Healthcare | $289 |
| Jobs in Health | Healthcare | $349 |
| De Nederlandse Assistenten Site | Healthcare | $99 |

### France (85 boards)

| Board | Industry | Price (USD) |
|-------|---------|------------|
| HelloWork | Generic | — |
| Meteojob | Generic | — |
| Apec.fr | Generic (executives) | — |
| Emploimedecin | Healthcare (physicians) | $679 |
| Emploisoignant | Healthcare (nursing/care) | $529 |
| Jobvitae.fr | Healthcare / Pharma | $369 |
| Staffsante | Healthcare | $1,019 |

### United Kingdom (63 boards)

| Board | Industry | Price (USD) |
|-------|---------|------------|
| TotalJobs | Generic | — |
| CV-Library | Generic | — |
| Reed | Generic | — |
| Resume Library | Generic | — |
| CityJobs | Finance | — |
| Guardian Jobs | Public sector / Media | — |
| The Nutrition Society | Healthcare | $349 |
| The Royal College of Psychiatrists | Healthcare | $309 |
| The British Institute of Radiology | Healthcare | $489 |
| Vet Record Careers | Healthcare (veterinary) | $679 |

### Austria / Switzerland / DACH (39 / 38 boards)

| Board | Country | Industry | Price (USD) |
|-------|---------|---------|------------|
| Karriere.at | Austria | Generic | — |
| Jobs.at | Austria | Generic | — |
| Hokify.at | Austria | Generic | — |
| Jobs.ch | Switzerland | Generic | — |
| FachAerzteJobs | AT / CH / DE | Healthcare (specialist physicians) | $1,389 |
| Krankenschwesterjobs | AT / CH | Healthcare (nursing) | $1,389 |
| Docjobs.at | Austria | Healthcare | $289 |
| Medjobs.at / Medjobs.de | AT / DE | Healthcare | $879 |
| Med Jobs | Switzerland | Healthcare | $649 |
| praxisstellen.ch | Switzerland | Healthcare | $359 |
| psychologie.ch | Switzerland | Healthcare | $739 |

### Belgium (55 boards)

| Board | Industry | Price (USD) |
|-------|---------|------------|
| VDAB | Generic (Flemish public employment) | — |
| Stepstone.be | Generic | — |
| Jobat.be | Generic | — |
| Vetplace.be | Healthcare (veterinary) | $129 |

### Nordics — Denmark / Sweden / Norway / Finland

| Board | Country | Industry | Price (USD) |
|-------|---------|---------|------------|
| Sundhedsstillinger | Denmark | Healthcare | $1,389 |
| Hälsojobb | Sweden | Healthcare | $1,389 |
| Helsestillinger | Norway | Healthcare | $1,389 |
| Terveysalantyot | Finland | Healthcare | $1,389 |

### Ireland (3 boards)

| Board | Price (USD) |
|-------|------------|
| IrishJobs.ie | — |
| Jobs.ie | — |
| NIJobs.com | — |

### Romania (3 boards)

| Board | Price (USD) |
|-------|------------|
| eJobs.ro | — |
| OLX.ro | — |
| Hipo.ro | — |

---

## International / Multi-Region

Boards covering 10+ countries or global reach:

| Board | Focus | Price (USD) |
|-------|-------|------------|
| LinkedIn | All sectors | — |
| Indeed | All sectors | — |
| Talent.com | All sectors | — |
| Adzuna | All sectors | — |
| Jooble | All sectors | — |
| Jobrapido | All sectors | — |
| eFinancialCareers | Finance | — |
| ResearchGate | Research / Healthcare | $489 |
| Cardiothoracic Surgery Network (CTSNet) | Healthcare | $659 |
| Diversity In Research | Healthcare / Research / Legal | $549 |
| Medicinoxy | Healthcare | $639 |
| medi-lab.net | Healthcare (DACH + France) | $499 |

---

## APAC, LATAM & MENA

| Board | Region | Direct Apply | Notes |
|-------|--------|------------|-------|
| Seek / Jobstreet / JobsDB | Australia / APAC | **Mandatory** | Dominant in AU, MY, SG, PH |
| Naukri / Foundit.in | India | **Mandatory** | Largest Indian job board |
| Bayt | Gulf / MENA | **Mandatory** | Top board in UAE, KSA, Kuwait |
| Kariyer | Turkey | **Mandatory** | Dominant Turkish job board |
| Computrabajo | Latin America | **Mandatory** | 17 LatAm countries |
| Bumeran | Latin America | **Mandatory** | Argentina, Chile, Peru, Colombia |
| Work.ua | Ukraine | **Mandatory** | — |
| CVeskus | Estonia | Optional | Baltic region |
| CV-online.lt | Lithuania | Optional | Baltic region |
| Sapo Emprego | Portugal | Optional | — |
| BestJobs.eu | Romania | Optional | — |

---

## Healthcare Job Boards

Healthcare is the second-largest specialized vertical on HAPI after generic boards — 125 unique marketplace boards across US, Europe, and international markets.

### United States Healthcare Boards (67 boards)

**Nursing & Advanced Practice:**

| Board | Specialty | Price (USD) |
|-------|---------|------------|
| American Nurses Association | RN / all nursing | $299 |
| American Association of Nurse Practitioners | NP | $419 |
| Association Of Perioperative Registered Nurses | OR / perioperative nurses | $519 |
| American Association of Medical Dosimetrists | Dosimetry | $449 |
| Society of Trauma Nurses | Trauma nursing | $129 |

**Physician Specialty Boards:**

| Board | Specialty | Price (USD) |
|-------|---------|------------|
| American Psychiatric Association | Psychiatry | $829 |
| American College of Radiology | Radiology | $419 |
| American Academy of Neurology | Neurology | $524 |
| American Neurological Association | Neurology | $419 |
| Society for Neurojobs | Neuroscience | $549 |
| American Heart Association | Cardiology | $309 |
| Heart Failure Society of America | Cardiology | $419 |
| American Society of Nephrology | Nephrology | $499 |
| Society for Vascular Surgery | Vascular Surgery | $499 |
| American College of Surgeons Surgery Career Connection | Surgery | $469 |
| American Society for Surgery of the Hand | Hand Surgery | $729 |
| American Pediatric Surgical Association | Pediatric Surgery | $629 |
| Society of Surgical Oncology | Oncology Surgery | $349 |
| North American Spine Society | Spine | $719 |
| Society for Interventional Radiology | IR | $519 |
| Society of Abdominal Radiology | Radiology | $449 |
| Society for Pediatric Radiology | Radiology | $449 |
| Society of Breast Imaging | Radiology | $449 |
| Cardiothoracic Surgery Network (CTSNet) | CT Surgery | $659 |
| American Board of Urgent Care Medicine | Urgent Care | $309 |
| Society Hospital Medicine | Hospitalist | $604 |
| emCareers | Emergency Medicine | $604 |
| Alliance for Academic Internal Medicine | Internal Medicine | $579 |
| American Epilepsy Society | Neurology | $339 |
| American Clinical Neurophysiology Society | Neurophysiology | $209 |
| Association of Academic Physiatrists | PM&R | $369 |
| American Society of Transplantation | Transplant | $309 |
| International Behavioral Neuroscience Society | Neuroscience | $419 |
| AcademyHealth | Health Policy / Research | $419 |
| Association of American Medical Colleges | Academic Medicine | $419 |
| Healthcare Information and Management Systems Society (HIMSS) | Health IT | $369 |
| Gerontological Society of America | Geriatrics | $299 |

**Allied Health & Other:**

| Board | Specialty | Price (USD) |
|-------|---------|------------|
| American Society of Hand Therapists | OT / PT | $309 |
| American Dental Education Association | Dental Education | $419 |
| California Dental Association | Dental | $309 |
| Maryland State Dental Association | Dental | $309 |
| American College of Veterinary Internal Medicine | Veterinary | $494 |
| American Animal Hospital Association | Veterinary | $209 |
| VetCareJobs.com | Veterinary | $269 |
| Veterinary Emergency & Critical Care Society | Veterinary | $309 |
| American Association of Immunologists | Immunology | $419 |
| American Society for Microbiology | Microbiology | $419 |
| National Cancer Registrars Association | Cancer Registry | $269 |
| National Association of Healthcare Access Management | Access Mgmt | $219 |
| Healthcare & Nursing Network | RN / allied health | $229 |
| HealthcareJobsite.com | General healthcare | $169 |
| The Journal of Urgent Care Medicine | Urgent Care | $309 |
| Wisconsin Academy of Family Physicians | Family Medicine | $269 |
| American Indian Science and Engineering Society | Healthcare (diversity) | $269 |
| Association for Women Surgeons | Surgery (diversity) | $339 |
| Association of Women's Health OB/GYN (AWHONN) | OB/GYN | $439 |
| American Association for Women Radiologists | Radiology (diversity) | $689 |

### European Healthcare Boards

**Germany (27 boards) — Most specialized healthcare distribution in Europe:**

| Board | Specialty | Price (USD) |
|-------|---------|------------|
| medi-karriere.de | All healthcare | $1,449 |
| arztjobs.de | Physicians | $1,329 |
| altenpflegejobs24.de | Elderly care nursing | $1,329 |
| Krankenschwesterjobs | Nursing | $1,389 |
| krankenpflegejobs24.de | Hospital nursing | $1,329 |
| FachAerztejobs | Specialist physicians (DACH) | $1,389 |
| Pflegejob.de | Nursing | $689 |
| deutsche-pflegejobs.de | Nursing | $1,209 |
| Klinik.jobs | Hospital jobs | $519 |
| Kliniken | Hospital jobs | $459 |
| Jobs Medizintechnik | Medical devices / tech | $1,099 |
| Dental Jobs | Dental | $869 |
| zfajobs.de | Dental assistants (ZFA) | $1,329 |
| mfajobs.de | Medical assistants (MFA) | $1,329 |
| mtajobs.de | Medical-technical assistants | $1,329 |
| hebammenjobs.de | Midwives | $1,329 |
| sanitaeterjobs.de | Paramedics | $1,329 |
| Pharmazie.Jobs | Pharmacy | $519 |
| Medizin1.de | General healthcare | $929 |
| medizinzeitung.de | Healthcare news + jobs | $729 |
| Medi-jobs.de | General healthcare | $349 |
| Meine Jobs Pflege | Nursing / care | $429 |
| Psychologie-jobs.de | Psychology | $199 |
| PraktischArzt | GP / family medicine | $1,329 |
| Jobninja.com | Multi-sector (incl. healthcare) | $799 |
| pflegedienstjobs24.de | Home care nursing | $1,329 |
| Zahn-lüecken | Dental | $239 |

**Netherlands (16 boards):**

| Board | Specialty | Price (USD) |
|-------|---------|------------|
| ArtsenVacaturebank | Physicians | $349 |
| Gezondheidszorgbanen | General healthcare | $499 |
| VacatureInDeZorg.nl | General healthcare | $349 |
| Jobs in Health | General healthcare | $349 |
| Esculaap | Healthcare | $239 |
| FMT Gezondheidszorg | Allied health | $289 |
| Ergotherapie Nederland | Occupational therapy | $519 |
| Farmavac | Pharmacy | $399 |
| Nationale Zorggids | General healthcare | $239 |
| Nederlandse Vereniging van Anesthesiemedewerkers | Anesthesia | $319 |
| Nederlandse Vereniging voor Gezondheidszorgpsychologie | Health psychology | $449 |
| NVLF (Speech therapy) | Speech therapy | $289 |
| De Nederlandse Assistenten Site | Medical assistants | $99 |
| De Nederlandse Onderzoekers Site | Research / healthcare | $99 |
| OK Visie (Flemish) | OR / surgical | $499 |

**Nordic countries (4 boards, all ~$1,389):**

| Board | Country | Specialty |
|-------|---------|---------|
| Helsestillinger | Norway | All healthcare |
| Sundhedsstillinger | Denmark | All healthcare |
| Hälsojobb | Sweden | All healthcare |
| Terveysalantyot | Finland | All healthcare |

**Austria / Switzerland (8 boards):**

| Board | Country | Specialty | Price (USD) |
|-------|---------|---------|------------|
| FachAerzteJobs | AT / CH | Specialist physicians | $1,389 |
| Krankenschwesterjobs | AT / CH | Nursing | $1,389 |
| Pflegejobs.Rocks | DACH | Nursing | $1,209 |
| Medjobs.at / Medjobs.de | AT / DE | General healthcare | $879 |
| Docjobs.at | Austria | Physicians | $289 |
| Med Jobs | Switzerland | All healthcare | $649 |
| praxisstellen.ch | Switzerland | Practice positions | $359 |
| psychologie.ch | Switzerland | Psychology | $739 |

**France (4 boards):**

| Board | Specialty | Price (USD) |
|-------|---------|------------|
| Emploimedecin | Physicians | $679 |
| Emploisoignant | Nursing / care workers | $529 |
| Jobvitae.fr | Healthcare / Pharma | $369 |
| Staffsante | All healthcare | $1,019 |

---

## Diversity & Inclusion Boards

80+ boards in the HAPI marketplace specifically targeting underrepresented groups in hiring.

| Category | # Boards | Examples |
|----------|---------|--------|
| Age / Graduates / Internship | 80 | Campus recruitment, apprenticeships |
| General Diversity | 35 | DiversityJobs.com, INROADS |
| Ethnic & Cultural Diversity | 32 | HBCUs, AISES, Prospanica |
| Gender | 21 | Women in Tech boards, Women Engineers |
| Senior Level | 10 | C-suite, executive search boards |
| Veterans | 7 | VetJobs, Hire Heroes, RecruitMilitary |
| Sexual Orientation | 6 | Out & Equal, Pink Jobs |
| Disability | 4 | AbilityJobs, Getting Hired |
| Remote Only | 6 | Remote-specific job boards |

---

## Full Data

The complete HAPI marketplace board list — 1,750 unique boards with country, industry, category, and minimum USD price — is available as machine-readable JSON:

**[`job-boards-marketplace.json`](./job-boards-marketplace.json)** — 1,750 boards (419KB)

```json
{
  "total": 1750,
  "source": "HAPI Product Portfolio (Sep 2026)",
  "boards": [
    {
      "name": "American Nurses Association",
      "country": "United States",
      "industry": "Healthcare",
      "category": "",
      "min_price_usd": 299,
      "products_available": 2,
      "source": "HAPI Marketplace"
    },
    ...
  ]
}
```

An additional 2,800 BYOC boards (boards where you bring your own negotiated contract) are distributed via the HAPI JP channel — contact HAPI support for the full BYOC catalog.

---

## Related Resources

### In this repo
- [HRTech Landscape](./README.md) — Full 1,500+ vendor taxonomy across 44 categories
- [HRTech Data Providers](./data-providers.md) — Person APIs, labor market intelligence, employment verification
- [Healthcare Data Sources](./healthcare-data-sources.md) — State nursing/medical board registries and commercial HCP datasets
- [Resume Parsing & Matching](./resume-parsing-matching.md) — Parsing APIs, semantic matching platforms, acquisition log

### Related repos
- [Autonomous Recruiter](https://github.com/ninjahire/autonomous-recruiter) — Build an AI recruiting workflow that distributes jobs and sources candidates autonomously using NinjaHire's MCP server
- [Awesome Recruiter Tools](https://github.com/ninjahire/awesome-recruiter-tools) — AI prompts, playbooks, and outreach sequences for recruiters
- [Recruitment Taxonomy](https://github.com/ninjahire/recruitment-taxonomy) — Standard definitions: job board types, distribution models, posting terminology

### NinjaHire
[NinjaHire](https://ninjahire.co) automates job distribution and candidate sourcing for staffing firms and MSP/VMS teams — integrating with 4,300+ job boards, major ATS platforms, and VMS systems (Fieldglass, Beeline, Coupa). [Get started free →](https://app.ninjahire.co/auth/signup)

---

**Maintained by [NinjaHire](https://ninjahire.co)** — Autonomous AI Recruiter for staffing teams and high-volume hiring operations.

[![NinjaHire](https://img.shields.io/badge/Maintained%20by-NinjaHire-brightgreen)](https://ninjahire.co)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
