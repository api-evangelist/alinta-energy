# Alinta Energy (alinta-energy)

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Alinta Energy is one of Australia's largest integrated energy retailers and generators, owned by Hong Kong-based Chow Tai Fook Enterprises, supplying electricity and gas to more than a million homes and businesses across Western Australia, South Australia, Victoria, New South Wales and Queensland while operating an owned and contracted generation portfolio of roughly 3,000 MW spanning gas, coal, wind, solar and battery storage, plus the Lumo Energy retail brand. It sits at the retail end of the value chain — the tier the Australian Consumer Data Right binds. Alinta is a designated and live CDR energy data holder: its own public base URI https://public.cdr.alintaenergy.com.au serves the standards-conformant discovery endpoints (confirmed HTTP 200), and 493 of its energy plans are published anonymously through the CDR generic plan data channel — but that plan channel is hosted by the Australian Energy Regulator's Energy Made Easy platform, not by Alinta. Its API posture is therefore honestly summarised as mandate-implemented but developer-closed: everything of substance sits behind ACCC accreditation and consumer consent, Alinta publishes no developer portal, no self-serve API, no proprietary OpenAPI and no open grid or market data of its own.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/alinta-energy/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/alinta-energy/refs/heads/main/apis.yml)

## Tags

- Energy
- Australia
- Utilities
- Electricity
- Gas
- Energy Retail
- Consumer Data Right
- CDR
- Open Energy Data
- Smart Metering
- Renewables
- Generation

## Timestamps

- **Created:** 2026-07-27
- **Modified:** 2026-07-27

## APIs

### Alinta Energy CDR Discovery API

The only API Alinta Energy serves from its own infrastructure that a developer can call anonymously. Two unauthenticated operations mandated by the Australian Consumer Data Standards for every data holder — `GET /discovery/status` and `GET /discovery/outages` — which report whether the data holder's CDR surface is operational and disclose planned or current outages. Both were confirmed live on 2026-07-27 with HTTP 200 and header `x-v: 1`, returning status "OK" ("All services operational") and an empty outages array. No other path under this base URI resolves; `/energy/plans` and `/common/customer` both returned HTTP 404.

- **Human URL:** [https://consumerdatastandardsaustralia.github.io/standards/#discovery-apis](https://consumerdatastandardsaustralia.github.io/standards/#discovery-apis)
- **Base URL:** `https://public.cdr.alintaenergy.com.au/cds-au/v1`

#### Tags

- Consumer Data Right
- Discovery
- Status
- Outages

#### Properties

- [OpenAPI](openapi/alinta-energy-cds-common-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [API Reference](https://consumerdatastandardsaustralia.github.io/standards/#discovery-apis)
- [Documentation](https://consumerdatastandardsaustralia.github.io/standards/)
- [Status](https://public.cdr.alintaenergy.com.au/cds-au/v1/discovery/status)
- [API Standards](https://consumerdatastandardsaustralia.github.io/standards/)

### Alinta Energy CDR Generic Plan Data API

Alinta Energy's public electricity and gas plan catalogue, exposed as the CDR energy Generic Plan Data endpoints `GET /energy/plans` and `GET /energy/plans/{planId}`. Confirmed live on 2026-07-27 with HTTP 200 returning `meta.totalRecords` of 493 Alinta plans, and a plan detail fetch for planId `ALI1144886SRG2@EME` returning HTTP 200 at `x-v: 3`. This data is genuinely open — no key, no consent, no accreditation — but the critical fact is that it is NOT served by Alinta. Unlike Australian banking, where every bank hosts its own Product Reference Data, the CDR energy regime centralises generic plan data at the Australian Energy Regulator, and this endpoint runs on the AER's Energy Made Easy CDR platform under the retailer slug `alinta`. Alinta's own host returns 404 for the same path.

- **Human URL:** [https://www.energymadeeasy.gov.au/](https://www.energymadeeasy.gov.au/)
- **Base URL:** `https://cdr.energymadeeasy.gov.au/alinta/cds-au/v1`

#### Tags

- Consumer Data Right
- Energy Plans
- Tariffs
- Open Data
- Electricity
- Gas

#### Properties

- [OpenAPI](openapi/alinta-energy-cds-energy-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [API Reference](https://consumerdatastandardsaustralia.github.io/standards/#energy-plans)
- [Documentation](https://consumerdatastandardsaustralia.github.io/standards/)
- [API Standards](https://consumerdatastandardsaustralia.github.io/standards/)

### Alinta Energy CDR Energy API

The mandated consumer data-sharing surface. As a designated CDR energy data holder (register brand ID `8bd0fd93-9d26-ee11-a83d-000d3a8830d6`, ABN 22149658300), Alinta must serve the Consumer Data Standards energy resource endpoints — accounts, balances, invoices, billing, payment schedules, concessions, electricity service points, interval usage and distributed energy resources — to ACCC-accredited data recipients holding a valid consumer consent. No base URL is recorded because none is published: the mTLS resource and infosec base URIs are disclosed only through the CDR Register's authenticated data holder brand detail endpoint, which requires an accredited client certificate. Probes of `secure.`, `idp.` and `cdr.` subdomains of alintaenergy.com.au did not resolve, and no `/.well-known/openid-configuration` is served anonymously. The contract below is the shared Data Standards Body specification Alinta implements, not an Alinta-authored document.

- **Human URL:** [https://www.alintaenergy.com.au/help-and-support/terms-and-conditions/consumer-data-right-cdr](https://www.alintaenergy.com.au/help-and-support/terms-and-conditions/consumer-data-right-cdr)

#### Tags

- Consumer Data Right
- Energy Accounts
- Usage
- Billing
- Distributed Energy Resources
- Consent

#### Properties

- [OpenAPI](openapi/alinta-energy-cds-energy-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [OpenAPI](openapi/alinta-energy-cds-common-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [API Reference](https://consumerdatastandardsaustralia.github.io/standards/#energy-apis)
- [Documentation](https://consumerdatastandardsaustralia.github.io/standards/)
- [Consumer Data Right](https://www.alintaenergy.com.au/help-and-support/terms-and-conditions/consumer-data-right-cdr)
- [Registry](https://api.cdr.gov.au/cdr-register/v1/energy/data-holders/brands/summary)
- [API Standards](https://consumerdatastandardsaustralia.github.io/standards/)

## Common Properties

- [Website](https://www.alintaenergy.com.au/)
- [Consumer Data Right](https://www.alintaenergy.com.au/help-and-support/terms-and-conditions/consumer-data-right-cdr)
- [Privacy Policy](https://www.alintaenergy.com.au/help-and-support/terms-and-conditions/privacy-policy)
- [API Standards](https://consumerdatastandardsaustralia.github.io/standards/)
- [Registry](https://api.cdr.gov.au/cdr-register/v1/energy/data-holders/brands/summary)
- [Regulator](https://www.cdr.gov.au/)
- [GitHub Organization](https://github.com/AlintaEnergy)
- [LinkedIn](https://au.linkedin.com/company/alinta-energy)
- [Status](https://public.cdr.alintaenergy.com.au/cds-au/v1/discovery/status)

## Maintainers

- Kin Lane — kin@apievangelist.com
