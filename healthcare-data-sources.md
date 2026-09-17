# Healthcare Data Sources: Nursing Boards, Medical Boards & Commercial Datasets

> A practitioner's guide to acquiring US healthcare provider data — federal open registries, buyable commercial datasets, and state-by-state licensing board access methods.

**Maintained by [NinjaHire](https://ninjahire.co)**

This document covers every major source for healthcare provider data in the US: who has it, how to get it, and what form it comes in. Built from direct experience scraping state nursing boards across KS, IN, and GA and enriching records with NPPES/NPI data.

---

## Table of Contents

- [Federal Open Data Sources](#federal-open-data-sources)
- [Commercial Healthcare Data Providers](#commercial-healthcare-data-providers)
- [State Nursing Board Registry — All 50 States](#state-nursing-board-registry)
- [State Medical Board Registry](#state-medical-board-registry)
- [Data Collection Patterns](#data-collection-patterns)

---

## Federal Open Data Sources

These are fully free, publicly accessible datasets from the US government. No license, no fee, no approval needed.

### NPPES / NPI Registry

The National Plan and Provider Enumeration System is the gold standard for US healthcare provider data. Every licensed provider who bills Medicare or Medicaid must have an NPI number.

| Property | Details |
|----------|---------|
| **Coverage** | 8M+ individual providers (NPI-1) + 4M+ organizations (NPI-2) |
| **Data fields** | Name, credential, specialty/taxonomy code, practice address, phone, license number, license state, enumeration date |
| **Bulk download** | `https://npiregistry.cms.hhs.gov/registry/download-npi-data` — monthly full files, weekly updates (CSV/ZIP, ~7GB unzipped) |
| **API** | `https://npiregistry.cms.hhs.gov/api/?version=2.1` — free, unauthenticated, paginated (max 200/request) |
| **Filter by taxonomy** | `taxonomy_description=Registered+Nurse&state=TX` — pulls all RNs in Texas |
| **Update frequency** | Weekly incremental + monthly full replacement |

**Nursing taxonomy codes to filter on:**

| Code | Description |
|------|-------------|
| `163W00000X` | Registered Nurse |
| `164W00000X` | Licensed Practical Nurse |
| `163WP2201X` | Nurse Practitioner (Pediatrics) |
| `363L00000X` | Nurse Practitioner (general) |
| `367500000X` | Nurse Anesthetist (CRNA) |
| `176B00000X` | Midwife |

**Medical taxonomy codes:**

| Code | Description |
|------|-------------|
| `207Q00000X` | Family Medicine |
| `207R00000X` | Internal Medicine |
| `208000000X` | Pediatrics |
| `208600000X` | Surgery (General) |
| `207X00000X` | Orthopedic Surgery |
| `2084P0800X` | Psychiatry |
| `207N00000X` | Dermatology |
| `207V00000X` | Obstetrics & Gynecology |

**Pattern used in nh-website project:** Pull all nursing taxonomies for a target state via the CMS API → export to CSV → merge with state board data by license number to get NPI, phone, and address.

---

### CMS Medicare Provider Data

| Dataset | URL | What's In It |
|---------|-----|--------------|
| Medicare Physician & Other Practitioners | `data.cms.gov/provider-summary-by-type-of-service` | Billing patterns, procedure volumes, payment amounts per provider |
| Medicare Fee Schedule | `cms.gov/medicare/payment/fee-schedules` | RVU/payment rates by procedure code and geography |
| Medicare Enrollment | `data.cms.gov/enrollment` | Active provider enrollment status |
| Medicare Advantage Plan Finder | `data.cms.gov/plan-management` | Plan-level data including provider networks |

All free, all downloadable as CSV.

---

### CMS Open Payments (Sunshine Act)

Tracks payments from drug/device manufacturers to physicians and hospitals.

- **URL:** `openpaymentsdata.cms.gov`
- **Coverage:** ~$12B+ in payments annually, all MDs + DOs + NPs + PAs
- **Use case for recruiting/outreach:** Identifies physicians with strong industry relationships; useful for medical device, pharma, and life sciences recruiting

---

### HRSA Data Warehouse

Health Resources & Services Administration — workforce shortage and facility data.

- **URL:** `data.hrsa.gov`
- **Key datasets:** Health Professional Shortage Areas (HPSAs), Medically Underserved Areas, National Health Service Corps sites, rural health facility locations
- **Use case:** Identifying underserved markets and geographic targeting for travel nurse/physician placement

---

### Other Federal Sources

| Source | URL | Coverage |
|--------|-----|----------|
| DEA Diversion Control | `dea.gov/drug-information/csa` | Controlled substance registrants (prescriber DEA numbers) |
| AHRQ Healthcare Cost and Utilization Project | `hcupus.ahrq.gov` | Hospital utilization, diagnoses, procedures |
| CDC Provider Data | `cdc.gov/nchs` | Vital statistics, public health workforce |
| VA Provider Data | `data.va.gov` | Veterans health system provider rosters |
| CMS PECOS | `pecos.cms.hhs.gov` | Medicare enrollment by provider (search only, no bulk API) |

---

## Commercial Healthcare Data Providers

When federal and state data isn't sufficient — or you need enriched, deduplicated, contact-level data — these are the vendors with buyable datasets.

### Tier 1: Comprehensive HCP Databases

| Vendor | Coverage | Delivery | Pricing | Notes |
|--------|----------|----------|---------|-------|
| **[Definitive Healthcare](https://definitivehc.com)** | 10M+ providers, 8,000+ hospitals, org hierarchies | API, bulk CSV, Salesforce integration | Enterprise contract (~$50K–$200K+/yr) | Most comprehensive hospital + provider dataset in the US; includes affiliations, procedure volumes, tech stack (EMR), and financial data for health systems |
| **[IQVIA](https://iqvia.com)** | 10M+ global HCPs, Rx prescribing data, patient-level claims | API, bulk license, OneKey database | Enterprise only (multi-$100K range) | Formed by IMS Health + Quintiles merger. The de facto standard for pharma/biotech commercial data. Prescriber-level Rx data is their core moat. SK&A brand handles mailing lists |
| **[Veeva OpenData](https://veeva.com/products/opendata/)** | 5M+ HCPs (US + global) | CRM-native, API | Enterprise SaaS | Integrated into Veeva CRM; widely used in life sciences for field rep targeting |
| **[Doximity](https://doximity.com)** | 2M+ US physicians, NPs, PAs, pharmacists; social graph | API (partner-only), platform ads | Partner contract | Largest physician social network in the US. Physician-verified. Used in nh-website project to enrich nursing profiles. API access requires partnership agreement |
| **[Healthgrades](https://healthgrades.com)** | 3M+ providers with patient ratings, hospital affiliations | Licensing, API | Custom | Consumer-facing but strong underlying provider database; licenses data to payers and health systems for provider directories |

---

### Tier 2: List & Mailing Data

| Vendor | Coverage | Delivery | Use Case |
|--------|----------|----------|----------|
| **[Data Axle (formerly Infogroup)](https://data-axle.com)** | 4M+ physicians, dentists, nurses, allied health | List rental/purchase, API | Targeted direct mail and email outreach to HCPs |
| **[SK&A (IQVIA)](https://skainfo.com)** | 2.6M+ HCPs, specialty breakdown, practice affiliations | List rental, bulk file | Pharma field force, medical device sales targeting |
| **[MDLists](https://mdlists.com)** | Physician + specialty mailing lists by state, specialty, ZIP | List purchase | Direct mail; one of the oldest medical list providers |
| **[Exact Data](https://exactdata.com)** | Healthcare provider mailing lists | List rental | Targeted outreach; lower cost than IQVIA-level sources |
| **[BioPharm Research](https://biopharmresearch.com)** | HCP specialty lists, hospital staff rosters | List purchase | Pharma and biotech commercial use |

---

### Tier 3: Provider Directory / Network Data

| Vendor | Coverage | Use Case |
|--------|----------|----------|
| **[Kyruus Health (BetterDoctor)](https://kyruus.com)** | Provider directory data for health plans and health systems | Accurate provider directory maintenance for insurance networks |
| **[Phynd (now symplr)](https://symplr.com)** | Provider management platform | Health system credentialing and workforce management |
| **[CAQH ProView](https://caqh.org)** | 1.5M+ provider credentialing records | Industry standard for provider credentialing/enrollment |
| **[Vivian Health](https://vivian.com)** | 1M+ nurse/allied health professional profiles | Travel nurse and per-diem healthcare staffing |
| **[Trusted Health](https://trustedhealth.com)** | Travel nurse marketplace | Direct nurse placement, strong profile data |
| **[Aya Healthcare](https://ayahealthcare.com)** | 250K+ clinician candidates | Travel/per-diem nurse and allied health |

---

### Tier 4: Analytics & Market Intelligence

| Vendor | Coverage | Notes |
|--------|----------|-------|
| **[Advisory Board (Optum)](https://advisory.com)** | Health system performance benchmarks, market share | Acquired by Optum; used by hospital leadership for competitive analysis |
| **[Sg2 (Vizient)](https://sg2.com)** | Clinical utilization data, service line planning | Procedure volume projections by market |
| **[Stericycle Communication Solutions](https://stericycle.com)** | HIPAA-compliant patient and provider outreach | Used by health systems for appointment reminders and targeted HCP communication |
| **[Press Ganey](https://pressganey.com)** | Patient experience benchmarks, workforce engagement | Broad health system relationships; also tracks clinical staff satisfaction |

---

## State Nursing Board Registry

**51 jurisdictions** (50 states + DC). For each state, the most effective data collection approach is:

1. Check if the board participates in **NURSYS** (`nursys.com`) — the national nurse licensure verification system managed by NCSBN. NURSYS covers 40+ states and allows individual lookups but does not provide bulk export.
2. Check the state board's own portal for bulk download or public license search.
3. If no bulk download: file a public records request (most states treat license rosters as public records) or scrape the verification portal.

**Source:** Nurse.org State Board of Nursing Directory — `https://nurse.org/education/state-board-nursing-directory/` (last verified July 2026)

| State | Board Name | Portal URL | Phone | Scraped |
|-------|-----------|-----------|-------|---------|
| Alabama | Alabama Board of Nursing | [abn.alabama.gov](https://www.abn.alabama.gov/) | 800-656-5318 | — |
| Alaska | Alaska Board of Nursing | [commerce.alaska.gov/…/boardofnursing](https://www.commerce.alaska.gov/web/cbpl/professionallicensing/boardofnursing.aspx) | 907-269-8161 | — |
| Arizona | Arizona State Board of Nursing | [azbn.gov](https://www.azbn.gov/) | 602-771-7800 | — |
| Arkansas | Arkansas State Board of Nursing | [healthy.arkansas.gov/…/nursing](https://healthy.arkansas.gov/boards-commissions/boards/nursing-arkansas-state-board/) | 501-686-2700 | — |
| California | California Board of Registered Nursing | [rn.ca.gov](https://www.rn.ca.gov/) | 916-322-3350 | — |
| Colorado | Colorado Board of Nursing | [dpo.colorado.gov/Nursing](https://dpo.colorado.gov/Nursing) | 303-894-2430 | — |
| Connecticut | Connecticut Board of Examiners for Nursing | [portal.ct.gov/dph/…/board-of-examiners-for-nursing](https://portal.ct.gov/dph/public-health-hearing-office/board-of-examiners-for-nursing/board-of-examiners-for-nursing) | 860-509-7603 | — |
| Delaware | Delaware Board of Nursing | [dpr.delaware.gov/boards/nursing](https://dpr.delaware.gov/boards/nursing/) | 302-744-4500 | — |
| District of Columbia | DC Board of Nursing | [dchealth.dc.gov/bon](https://dchealth.dc.gov/bon) | 877-672-2174 | — |
| Florida | Florida Board of Nursing | [floridasnursing.gov](https://floridasnursing.gov/) | 850-245-4125 | — |
| Georgia | Georgia Board of Nursing | [sos.ga.gov/georgia-board-nursing](https://sos.ga.gov/georgia-board-nursing) | 844-753-7825 | ✅ scraped (Salesforce Aura API) |
| Hawaii | Hawaii Board of Nursing | [cca.hawaii.gov/pvl/boards/nursing](https://cca.hawaii.gov/pvl/boards/nursing/) | 808-586-3000 | — |
| Idaho | Idaho Board of Nursing | [dopl.idaho.gov/bon](https://dopl.idaho.gov/bon/) | 208-577-2476 | — |
| Illinois | Illinois Board of Nursing (IDFPR) | [idfpr.illinois.gov/profs/nursing.html](https://idfpr.illinois.gov/profs/nursing.html) | 800-560-6420 | — |
| Indiana | Indiana State Board of Nursing | [in.gov/pla/professions/nursing-home](https://www.in.gov/pla/professions/nursing-home/) | 317-234-2043 | ✅ scraped (213K records + NPI merged) |
| Iowa | Iowa Board of Nursing | [nursing.iowa.gov](https://nursing.iowa.gov/) | 515-281-3255 | — |
| Kansas | Kansas State Board of Nursing | [ksbn.kansas.gov](https://ksbn.kansas.gov/) | 785-296-4929 | ✅ scraped (12K records) |
| Kentucky | Kentucky Board of Nursing | [kbn.ky.gov](https://kbn.ky.gov/) | 502-429-3300 | — |
| Louisiana | Louisiana State Board of Nursing | [lsbn.state.la.us](https://www.lsbn.state.la.us/) | 225-755-7500 | — |
| Maine | Maine State Board of Nursing | [maine.gov/boardofnursing](https://www.maine.gov/boardofnursing/) | 207-287-1133 | — |
| Maryland | Maryland Board of Nursing | [health.maryland.gov/mbon](https://health.maryland.gov/mbon/pages/default.aspx) | 410-585-1900 | — |
| Massachusetts | Massachusetts Board of Registration in Nursing | [mass.gov/orgs/board-of-registration-in-nursing](https://www.mass.gov/orgs/board-of-registration-in-nursing) | 617-973-0900 | — |
| Michigan | Michigan Board of Nursing (LARA) | [michigan.gov/lara](https://www.michigan.gov/lara/bureau-list/bpl/health/hp-lic-health-prof/nursing) | 517-241-0199 | — |
| Minnesota | Minnesota Board of Nursing | [mn.gov/boards/nursing](https://mn.gov/boards/nursing/) | 612-317-3000 | — |
| Mississippi | Mississippi Board of Nursing | [msbn.ms.gov](https://www.msbn.ms.gov/) | 601-957-6300 | — |
| Missouri | Missouri State Board of Nursing | [pr.mo.gov/nursing.asp](https://pr.mo.gov/nursing.asp) | 573-751-0681 | — |
| Montana | Montana Board of Nursing | [boards.bsd.dli.mt.gov/nursing](https://boards.bsd.dli.mt.gov/nursing/) | 406-444-6880 | — |
| Nebraska | Nebraska Board of Nursing | [dhhs.ne.gov/licensure](https://dhhs.ne.gov/licensure/pages/nurse-licensing.aspx) | 402-471-4376 | — |
| Nevada | Nevada State Board of Nursing | [nevadanursingboard.org](https://nevadanursingboard.org/) | 775-687-7700 | — |
| New Hampshire | New Hampshire Board of Nursing | [oplc.nh.gov/new-hampshire-board-nursing](https://www.oplc.nh.gov/new-hampshire-board-nursing) | 603-271-2152 | — |
| New Jersey | New Jersey Board of Nursing | [njconsumeraffairs.gov/nur](https://www.njconsumeraffairs.gov/nur/Pages/default.aspx) | 973-504-6430 | — |
| New Mexico | New Mexico Board of Nursing | [bon.nm.gov](https://www.bon.nm.gov/) | 505-841-8340 | — |
| New York | New York State Board of Nursing | [op.nysed.gov/registered-professional-nursing](https://www.op.nysed.gov/registered-professional-nursing) | 518-474-3817 | — |
| North Carolina | North Carolina Board of Nursing | [ncbon.com](https://www.ncbon.com/) | 919-782-3211 | — |
| North Dakota | North Dakota Board of Nursing | [ndbon.org](https://www.ndbon.org/) | 701-751-3000 | — |
| Ohio | Ohio Board of Nursing | [nursing.ohio.gov](https://nursing.ohio.gov/) | 614-466-3947 | — |
| Oklahoma | Oklahoma Board of Nursing | [oklahoma.gov/nursing.html](https://oklahoma.gov/nursing.html) | 405-962-1800 | — |
| Oregon | Oregon State Board of Nursing | [oregon.gov/osbn](https://www.oregon.gov/osbn) | 971-673-0685 | — |
| Pennsylvania | Pennsylvania State Board of Nursing | [pa.gov/agencies/dos/…/nursing](https://www.pa.gov/agencies/dos/department-and-offices/bpoa/boards-commissions/nursing) | 833-367-2762 | — |
| Rhode Island | Rhode Island Board of Nursing | [health.ri.gov/licensing/nurses](https://health.ri.gov/licensing/nurses) | 401-222-5700 | — |
| South Carolina | South Carolina Board of Nursing | [llr.sc.gov/nurse](https://llr.sc.gov/nurse/) | 803-896-4550 | — |
| South Dakota | South Dakota Board of Nursing | [sdbon.org](https://www.sdbon.org/) | 605-362-2760 | — |
| Tennessee | Tennessee Board of Nursing | [tn.gov/health/licensure/nurs.html](https://www.tn.gov/health/licensure/nurs.html) | 615-532-5166 | — |
| Texas | Texas Board of Nursing | [bon.texas.gov](https://www.bon.texas.gov/) | 512-305-7400 | — |
| Utah | Utah Division of Professional Licensing — Nursing | [commerce.utah.gov/dopl/nursing](https://commerce.utah.gov/dopl/nursing/) | 801-530-6628 | — |
| Vermont | Vermont Board of Nursing | [sos.vermont.gov/nursing](https://sos.vermont.gov/nursing/) | 802-828-2396 | — |
| Virginia | Virginia Board of Nursing | [dhp.virginia.gov/nursing](https://www.dhp.virginia.gov/nursing/) | 804-367-4515 | — |
| Washington | Washington State Board of Nursing | [nursing.wa.gov](https://nursing.wa.gov/) | 360-236-4703 | — |
| West Virginia | West Virginia Board of Registered Nurses | [wvrnboard.wv.gov](https://wvrnboard.wv.gov/) | 304-744-0900 | — |
| Wisconsin | Wisconsin Board of Nursing (DSPS) | [dsps.wi.gov](https://dsps.wi.gov/Pages/BoardsCouncils/Nursing/Default.aspx) | 608-266-2112 | — |
| Wyoming | Wyoming State Board of Nursing | [wsbn.wyo.gov](https://wsbn.wyo.gov/) | 307-777-7601 | — |

### NURSYS — National Nurse License Verification

NURSYS (`nursys.com`) is managed by the National Council of State Boards of Nursing (NCSBN) and provides centralized license verification for participating states.

- **Individual lookups:** Free public search at `nursys.com/LUIndex.do`
- **e-Notify:** Alerts when a nurse's license status changes (used by hospitals and staffing firms)
- **Bulk/enterprise access:** NCSBN offers data licensing for healthcare organizations — contact `ncsbn.org` for terms
- **Coverage:** 40+ states participate; exact list at `ncsbn.org/nursys-participating-boards`
- **Limitation:** NURSYS does not provide bulk export of the full roster — only individual lookups and change notifications

### Nurse Licensure Compact (NLC)

As of 2026, 42+ states participate in the NLC, which allows a nurse licensed in one compact state to practice in all other compact states under a single multistate license.

- **Full compact member list:** `nursecompact.com/get-to-know-nlc/states-in-nlc/`
- **Practical impact for data collection:** NLC states' licensees appear in the issuing state's board records, but the license is valid across all compact states — your roster from Indiana will include nurses licensed in Indiana but practicing anywhere in the compact

---

## State Medical Board Registry

The Federation of State Medical Boards (FSMB) maintains the authoritative directory of all US state medical boards.

- **FSMB Directory:** `https://www.fsmb.org/contact-a-state-medical-board/`
- **DocInfo:** `docinfo.org` — FSMB's free public physician search covering all 50 states + DC
- **FSMB Data Services:** Bulk physician credential and disciplinary data available via licensing — contact `fsmb.org/data-and-research/`

### Key Medical Board Data Points Available

| Data Point | Available From |
|-----------|----------------|
| License number and status | State board portal |
| Medical school and graduation year | FSMB DocInfo, AMA |
| Residency/specialty board certification | FSMB, ABMS |
| Disciplinary actions | FSMB DocInfo, state boards |
| DEA registration | DEA Diversion Control |
| NPI number | NPPES (cross-reference by name/state) |
| Prescribing patterns | CMS Open Payments, Medicare Part D data |

### Verified Medical Board Directory

For direct links to all 50 state medical board websites and contact numbers, use the FSMB's AI-accessible directory:

**`https://www.fsmb.org/contact-a-state-medical-board/?st_source=ai_mode`**

---

## Data Collection Patterns

The following patterns were developed during the nh-website project to collect and enrich nursing license data state by state. Scripts live in `nh-website/scripts/doximity-scraper/`.

### Pattern 1: CMS NPI API → State Filter → CSV

The fastest starting point for any state. Pull all nurses (or physicians) with an NPI number registered in a given state directly from the CMS public API.

```python
# Free, unauthenticated, no rate limit documented (polite 200ms sleep used in practice)
API = "https://npiregistry.cms.hhs.gov/api/"

params = {
    "version": "2.1",
    "enumeration_type": "NPI-1",       # individual providers only
    "taxonomy_description": "Registered Nurse",
    "state": "TX",                      # any 2-letter state code
    "limit": 200,
    "skip": 0,                          # paginate in 200-record pages
}
```

**Output fields available:** NPI number, name, credential, sex, phone, fax, address, taxonomy code, license number, license state, enumeration date, last updated.

**Limitation:** NPI data is self-reported and can lag 30–90 days behind state board data. ~15–25% of nurses may not have an NPI (not required to bill Medicare/Medicaid). Use as enrichment layer on top of state board data, not as primary source.

---

### Pattern 2: State Board Portal Scraper

Each state has a public license verification portal. These vary by technology stack:

| Approach | States | Tech Used | Notes |
|----------|--------|-----------|-------|
| Pure HTTP (requests/BS4) | Indiana (`mylicense.in.gov`) | Python `requests` + `BeautifulSoup` | No CAPTCHA, simple POST pagination. ~213K records collected |
| Playwright + reCAPTCHA bypass | Kansas (`portal.egov.ksbn.ks.gov`) | Playwright (Chromium), JS injection | reCAPTCHA was over-quota (no image puzzle); checkbox click + token polling sufficient |
| Salesforce Aura API | Georgia | Direct API calls to SF Community portal | State boards running Salesforce Community/Experience Cloud expose a structured JSON API |
| ASP.NET WebForms | Many states | `__VIEWSTATE`/`__EVENTARGUMENT` POST | Common pattern: capture viewstate tokens, POST back pagination events |

**Tools used:** `playwright`, `requests`, `beautifulsoup4`, `lxml`, `curl_cffi` (Chrome TLS fingerprint for bot-resistant portals)

---

### Pattern 3: State Board Data + NPI Merge

After collecting both the state board CSV and the NPI CSV for the same state:

```
State Board CSV columns:
  first_name, last_name, license_no, license_type, status, city, state, zip

NPI CSV columns:
  npi, first_name, last_name, phone, fax, address_1, city, state, zip,
  taxonomy_desc, license_no, license_state, enumeration_date

Merge key: license_no (uppercase-normalized)
```

Match rate observed in Indiana: ~85–90% of active licensed nurses have an NPI and can be matched. The merge adds phone, fax, NPI number, and address to each nurse record.

**Script:** `nh-website/scripts/doximity-scraper/npi_scraper.py --merge in_nursing_full.csv`

---

### Pattern 4: Public Records Request (for states without bulk portals)

For states whose portals only support individual name/license lookups and have no scrapable pagination:

1. Draft a public records request citing your state's open records law (most states treat license data as public records):
   - FOIA (federal)
   - State equivalents: California CPRA, Texas TPIA, Florida Sunshine Law, New York FOIL, etc.
2. Request: *"All active nursing license records including name, license type, license number, license status, and city/state of practice"*
3. Most boards respond within 10–20 business days; some have online request portals
4. Format received: typically CSV or Excel; occasionally PDF (requiring OCR)

---

## Data Quality Notes

| Issue | Details | Mitigation |
|-------|---------|-----------|
| **NPI staleness** | NPI address/phone can be 1–2 years out of date | Use as enrichment layer; treat phone as "best effort" |
| **Name variations** | State board may have "Mary J Smith" vs NPI "SMITH MARY JANE" | Fuzzy match on last name + first initial + license number |
| **Inactive records** | State board files include expired, lapsed, and surrendered licenses | Filter on `status = Active` or `status = Active - Multistate` |
| **Duplicate NPIs** | Nurses with both compact and single-state licenses appear twice in some boards | Deduplicate by `result_guid` or license number |
| **PO Box addresses** | Some nurses register with a PO Box; NPI address may differ from practice location | Prefer NPI practice location address over state board mailing address |

---

## Related Resources

### In this repo
- [HRTech Landscape](./README.md) — 1,500+ vendor taxonomy including healthcare staffing platforms
- [HRTech Data Providers](./data-providers.md) — Data infrastructure layer powering HRTech: person APIs, employment verification, skills taxonomy
- [Resume Parsing & Matching](./resume-parsing-matching.md) — Parsing and matching for clinical resumes and healthcare credentials

### Related repos
- [Autonomous Recruiter](https://github.com/ninjahire/autonomous-recruiter) — NinjaHire's MCP server for automating healthcare staffing workflows: source nurses, run outreach, screen credentials, submit to VMS
- [Awesome Recruiter Tools](https://github.com/ninjahire/awesome-recruiter-tools) — Prompts and playbooks for healthcare recruiting: sourcing RNs, screening credentials, outreach sequences
- [Recruitment Taxonomy](https://github.com/ninjahire/recruitment-taxonomy) — Healthcare staffing terminology: per diem, travel nursing, compact license, NLC, bill rate, pay package

### NinjaHire
[NinjaHire](https://ninjahire.co) is built for healthcare staffing firms — automating sourcing from NPPES/NPI data, state board registries, and ATS talent pools, then running outreach, credential screening, and VMS submissions autonomously. [Book a demo →](https://calendly.com/bharatsigtia/30min)

---

**Maintained by [NinjaHire](https://ninjahire.co)** — Autonomous AI Recruiter for staffing teams and high-volume hiring operations.

[![NinjaHire](https://img.shields.io/badge/Maintained%20by-NinjaHire-brightgreen)](https://ninjahire.co)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
