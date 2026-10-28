# Alinta Energy

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

**Areas:** Energy · Australia · Utilities · Electricity · Gas · Energy Retail · Consumer Data Right · CDR · Open Energy Data · Smart Metering · Renewables · Generation

## Alinta Energy on APIs.io

Everything profiled for Alinta Energy is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/alinta-energy/](https://apis.io/providers/alinta-energy/)** — or go straight to one of the APIs or properties below.

### APIs (9)

- [Alinta Energy Data Holder Customers API](https://apis.io/apis/alinta-energy/alinta-energy-data-holder-customers-api/) — Data Holder Customer endpoints
- [Alinta Energy Data Holder Operations API](https://apis.io/apis/alinta-energy/alinta-energy-data-holder-operations-api/) — Data Holder Operations endpoints
- [Alinta Energy Distributed Energy Resources API](https://apis.io/apis/alinta-energy/alinta-energy-distributed-energy-resources-api/) — Distributed Energy Resource endpoints
- [Alinta Energy Electricity Service Points API](https://apis.io/apis/alinta-energy/alinta-energy-electricity-service-points-api/) — Electricity Service Point endpoints
- [Alinta Energy Electricity Usage API](https://apis.io/apis/alinta-energy/alinta-energy-electricity-usage-api/) — Electricity Usage endpoints
- [Alinta Energy Account Balances API](https://apis.io/apis/alinta-energy/alinta-energy-energy-account-balances-api/) — Energy Account Balance endpoints
- [Alinta Energy Account Billing API](https://apis.io/apis/alinta-energy/alinta-energy-energy-account-billing-api/) — Energy Account Billing endpoints
- [Alinta Energy Accounts API](https://apis.io/apis/alinta-energy/alinta-energy-energy-accounts-api/) — Energy Account endpoints
- [Alinta Energy Plans API](https://apis.io/apis/alinta-energy/alinta-energy-energy-plans-api/) — Energy Plan endpoints

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [alinta-energy-cdr](https://apis.io/servers/alinta-energy/alinta-energy-cdr/)

#### Agentic access (1)

Which operations an agent can call, which act, and which need a human in the loop.

- [Alinta Energy Agentic Access](https://apis.io/agentic-access/alinta-energy/alinta-energy-agentic-access/)

#### Collections (2)

Postman and Open Collection request collections.

- [CDR Common API](https://apis.io/collections/alinta-energy/open-alinta-energy-cds-common-api/)
- [CDR Energy API](https://apis.io/collections/alinta-energy/open-alinta-energy-cds-energy-api/)

#### Overlays (2)

OpenAPI overlays, including conversational phrasing for each operation.

- [Alinta Energy Cds Common Api Overlay](https://apis.io/overlays/alinta-energy/alinta-energy-cds-common-api-overlay/)
- [Alinta Energy Cds Energy Api Overlay](https://apis.io/overlays/alinta-energy/alinta-energy-cds-energy-api-overlay/)

#### Security (2)

Authentication, trust centre, and vulnerability disclosure.

- [Alinta Energy Authentication](https://apis.io/security/alinta-energy/alinta-energy-authentication/)
- [Alinta Energy Domain Security](https://apis.io/security/alinta-energy/alinta-energy-domain-security/)

#### OAuth scopes (1)

The permissions the API asks for.

- [Alinta Energy Scopes](https://apis.io/scopes/alinta-energy/alinta-energy-scopes/)

#### Rate limits (1)

Published request limits.

- [Alinta Energy Rate Limits](https://apis.io/rate-limits/alinta-energy/alinta-energy-rate-limits/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://www.alintaenergy.com.au/)
- [Documentation](https://consumerdatastandardsaustralia.github.io/standards/)
- [API reference](https://consumerdatastandardsaustralia.github.io/standards/#energy-apis)
- [Support](https://www.alintaenergy.com.au/help-and-support/help-and-support/customer-support)
- [Terms of service](https://www.alintaenergy.com.au/help-and-support/terms-and-conditions/website-terms-and-conditions)
- [Privacy policy](https://www.alintaenergy.com.au/help-and-support/terms-and-conditions/privacy-policy)
- [GitHub](https://github.com/AlintaEnergy)
- [Status](https://public.cdr.alintaenergy.com.au/cds-au/v1/discovery/status)

## API Evangelist rating

**Kin Score 41.3** — developing · rubric 0.25.0 · scored 2026-10-23

| Facet | Score |
|---|---|
| Discoverability | 73.2 |
| Contract quality | 44.7 |
| Contract governance | 4.5 |
| Operational transparency | 65.8 |
| Developer ergonomics | 35.1 |
| Access clarity | 21.1 |

**Agent readiness 28.0** — agent-aware

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | derived (partial credit) |
| Reversibility Documented | — |
| MCP Server | — |
| Auth Clarity | bearer (partial credit) |
| Idempotency | — |
| Error Semantics | verified |
| OpenAPI Examples | — |
| Rate Limit Signal | documented (partial credit) |
| Event Surface Described | — |
| Agent Skills | derived (partial credit) |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | — |
| Protected Resource Metadata | — |
| Dynamic Client Registration | — |
| Agentic Commerce | — |
| Pagination Ratio | na |
| Operation Distinctiveness | distinct |

**Regulatory alignment 34.4** — Energy & Utilities

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/alinta-energy/](https://apis.io/providers/alinta-energy/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for Alinta Energy: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/alinta-energy/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
