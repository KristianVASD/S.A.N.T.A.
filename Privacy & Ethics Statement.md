# S.A.N.T.A. — Fairness, Transparency & Data Ethics Statement

**S**ervice **A**uthenticity **N**etwork for **T**rusted **A**ttestations  
*A public-interest verification layer for the home services industry*

---

## What this project is

S.A.N.T.A. is an open-source trust verification system that helps homeowners identify genuinely local, qualified, and trustworthy service companies — and helps expose fraudulent operators who game local search results through fake addresses, cloned websites, and fabricated reviews.

This document explains exactly how we collect data, what we do with it, and why we believe our approach is not only legally sound but ethically superior to the systems we are designed to complement and correct.

---

## Our core principle: synthesis, not copying

S.A.N.T.A. does not reproduce, store, or redistribute any source database in its original form. We never output a copy of someone else's data. What we produce is an **original analytical synthesis** — a trust signal derived from the *convergence or divergence* of multiple independent public sources.

Think of it the way a journalist works: they read ten documents, none of which they reproduce verbatim, and write an original article that reflects what those documents collectively reveal. Our output is that article, not a photocopy of any one document.

---

## What data we use and why it is lawful

### 1. Public business registers

**Sources:** KvK (Dutch Chamber of Commerce) open data, SBB erkend leerbedrijf register, TLOKB CO-safety register, InstallQ / Techniek Nederland member registers.

These are statutory public registers. They exist specifically to be consulted by third parties. Accessing and referencing them for consumer protection purposes is consistent with their intended function and explicitly permitted under Dutch and EU law. We reference registration facts (company age, registration number, sector code, legal address) — we do not mirror the full database.

### 2. Publicly accessible web content

**Sources:** Company websites, local business association pages (BNI chapters, ondernemersverenigingen), review platforms (Google Maps, Kiyoh, Trustpilot), LinkedIn company pages.

This content is voluntarily made public by the companies themselves, or by their customers. We do not access any content behind authentication walls. We do not circumvent any technical access control. We read what anyone with a browser can read.

What we extract is not the content itself but **structural signals derived from it**: infrastructure fingerprints (hosting cluster, analytics identifiers, SSL issuance patterns), text similarity patterns across domains, and review metadata (temporal distribution, linguistic variance). These derivations are our original analytical work — not reproductions of the source.

### 3. What we explicitly do not collect

- Private contact details of natural persons acting in a personal capacity
- Any data from password-protected or login-gated sources
- Health, financial, or sensitive personal data of any kind
- The full text of reviews or website copy as stored artifacts
- Any data about individuals who are not acting in a professional/commercial capacity

---

## How we handle sole traders (eenmanszaken)

A sole trader operating under their own name is both a business and a natural person. We treat this carefully. We process only information directly related to their professional activity — business name, registered address, sector, certifications, public reviews of their work. We do not profile them as individuals. We do not process home addresses, personal phone numbers, or any information outside the scope of their commercial function.

Any sole trader can request removal from our index at any time (see the opt-out section below). Their professional data will be removed within 14 days.

---

## Legal basis under GDPR (where applicable)

Where data relates to natural persons acting in a commercial capacity (sole traders, named company representatives), our legal basis is **legitimate interest** under Article 6(1)(f) GDPR. That interest is:

**Consumer protection and fraud prevention in the home services market.**

This is a documented, material harm: fraudulent operators using fake local identities extract significant sums from homeowners, often vulnerable ones (elderly, post-disaster, urgent repair situations). The legitimate interest of protecting consumers from this harm outweighs the minimal privacy impact of referencing publicly available professional information about businesses.

We have assessed this under the three-part legitimate interest test:
- **Purpose test:** Fraud prevention and consumer protection are recognised legitimate interests under GDPR Recital 47.
- **Necessity test:** The data we process is the minimum required to produce a meaningful trust signal. We do not process more than necessary.
- **Balancing test:** The individuals whose data we reference are acting commercially, have voluntarily published this information, and face minimal intrusion from its analytical use. The benefit to consumers is proportionate and material.

---

## Why we are categorically different from the bad actors we detect

The fraudulent operators S.A.N.T.A. identifies operate by **deceiving** the public — fabricating local presence, purchasing fake reviews, cloning website content to simulate scale. They actively harm consumers.

S.A.N.T.A. operates in the opposite direction:

| Dimension | Fraudulent operators | S.A.N.T.A. |
|---|---|---|
| Intent | Extract money through deception | Protect consumers through transparency |
| Data use | Fabricate and falsify | Synthesise and verify |
| Transparency | Hidden, anonymous | Open-source, documented |
| Accountability | None | Public codebase, opt-out, contact |
| Source | Fake or purchased | Public registers and open web |

We are, in effect, doing for the home services market what credit reference agencies do for financial services, or what food hygiene inspectors do for restaurants — providing a publicly accessible, evidence-based trust signal that the market itself has failed to produce.

---

## robots.txt and terms of service

We respect `robots.txt` directives for all automated access. Where a site's terms of service restrict automated access, we do not scrape that site programmatically. For such sources, we rely on their publicly available structured outputs (APIs, open data exports, official registers) rather than direct crawling.

We do not circumvent any technical protection measure. We do not conduct denial-of-service-level request volumes against any source. Our crawl rates are conservative and identify themselves honestly via user-agent strings.

---

## Opt-out and correction

Any business listed in the S.A.N.T.A. index has the right to:

1. **Request removal** — we will delist within 14 days. Removal does not affect detection of fraudulent operator *networks* that the removed entity may be part of; only their individual listing is removed.
2. **Request correction** — if our data is factually incorrect, we will correct it promptly upon verified submission.
3. **Request explanation** — any business may request an explanation of why they received a particular trust classification.

Contact: open an issue in this repository with the label `data-request`, or email the maintainer as listed in the repository profile.

---

## What we share and with whom

S.A.N.T.A. is open-source. The **methodology** — how we score, what signals we use, how we weight them — is fully public. This is deliberate: transparency in our method is itself a trust signal.

The **raw data store** (company-level records) is not published as a bulk download. It is queryable via the S.A.N.T.A. API on a per-query basis, with rate limiting, to prevent bulk extraction that would replicate source databases.

Aggregated, anonymised pattern data (e.g. "we identified 47 domains belonging to a single fraudulent operator network in Zuid-Holland") may be published as public research findings.

We do not sell data. We do not share data with advertisers. We do not accept payment to alter trust scores.

---

## Relationship to existing search and index systems

Search engines like Google crawl and index the public web to make it discoverable. S.A.N.T.A. crawls a targeted subset of the public web to make it *trustworthy*. The legal foundation is the same — public accessibility, no circumvention of access controls, original synthesis rather than reproduction. The difference is focus and purpose: Google optimises for relevance, S.A.N.T.A. optimises for authenticity.

European courts (including the CJEU in *Ryanair v PR Aviation*, C-30/14) have confirmed that accessing and using publicly available information for a purpose other than direct competition with the source database does not constitute database right infringement. Our use is analytical and derivative, not competitive with any source.

---

## Future signal categories

As S.A.N.T.A. matures, additional trust signals will be added — including community engagement indicators (sponsoring local charity events, participating in apprenticeship programmes), employee wellbeing signals (Glassdoor ratings, CAO compliance), and environmental certifications. All additional signals will be subject to the same data minimisation and legitimate interest principles documented here.

Bad actor pattern libraries — documented methods used by fraudulent operators — will be published openly as a contribution to the broader fraud-detection research community, with all identifying information about victims redacted.

---

## Version and review

This statement was first published with the initial S.A.N.T.A. repository release. It will be reviewed and updated when:

- New data source categories are added
- The legal landscape under GDPR or the EU Data Act materially changes
- A significant opt-out or correction request reveals a gap in our approach

*S.A.N.T.A. is a project within the H3 (HandyHouseHelp) open infrastructure initiative. It is released under the MIT licence. The ethical commitments in this document are not part of the licence — they are a statement of how we choose to operate.*

---

*Last updated: June 2026*
