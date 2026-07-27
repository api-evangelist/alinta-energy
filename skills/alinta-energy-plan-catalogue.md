---
name: Retrieve Alinta Energy plan catalogue (CDR generic plan data)
description: List Alinta Energy's publicly offered electricity and gas plans and fetch full contract detail for one plan, from the anonymous CDR generic plan data endpoints.
api: openapi/alinta-energy-cds-energy-api-openapi.yml
method: generated
generated: '2026-07-27'
operations: [listEnergyPlans, getEnergyPlanDetail]
---

# Retrieve Alinta Energy plan catalogue (CDR generic plan data)

Alinta Energy's plan catalogue is **public and requires no authentication** — only the
mandatory `x-v` version header. The critical fact: it is **not served by Alinta**. In the
Australian CDR energy regime, generic plan data is centralised on the Australian Energy
Regulator's Energy Made Easy CDR platform under the retailer slug `alinta`. Alinta's own
base URI returns `404` for this path.

- Plan data host (use this): `https://cdr.energymadeeasy.gov.au/alinta/cds-au/v1`
- Alinta's own host (discovery only): `https://public.cdr.alintaenergy.com.au/cds-au/v1`

## Steps

1. **List plans** — `listEnergyPlans`
   `GET /energy/plans` with header `x-v: 1`.
   Optional query params: `type` (`STANDING`|`MARKET`|`REGULATED`|`ALL`, default `ALL`),
   `fuelType` (`ELECTRICITY`|`GAS`|`DUAL`|`ALL`, default `ALL`),
   `effective` (`CURRENT`|`FUTURE`|`ALL`, default `CURRENT`), `updated-since`, `brand`,
   `page`, `page-size` (default 25, max 1000).
   Read `data.plans[]`; page through with `meta.totalPages` / `links.next`.
   Results are ordered by `lastUpdated` descending.
   Confirmed live on 2026-07-27: `meta.totalRecords` 493.

2. **Get one plan's detail** — `getEnergyPlanDetail`
   `GET /energy/plans/{planId}` with header `x-v: 3`, where `planId` comes from a
   `data.plans[].planId` in step 1 (e.g. `ALI1144886SRG2@EME`).
   The detail response adds the electricity/gas contract, tariff periods, controlled
   load, solar feed-in tariff, discounts, incentives, fees, eligibility and green power
   charges.

## Rules

- **`x-v` is mandatory.** Use `1` for the list and `3` for the detail. A missing or
  non-integer `x-v` returns `400` (`Header/Missing`, `Header/InvalidVersion`); an
  unsupported version returns `406` (`Header/UnsupportedVersion`).
- **Errors** use the CDR error list format — `{"errors":[{"code","title","detail","meta"}]}`
  with `urn:au-cds:error:*` codes, **not** RFC 9457 problem+json. See
  `errors/alinta-energy-problem-types.yml`.
- **Pagination** is page-number based; `page-size` above 1000 returns `400`
  (`Field/InvalidPageSize`) and an out-of-range `page` returns `422` (`Field/InvalidPage`).
  See `conventions/alinta-energy-conventions.yml`.
- **Cache aggressively.** Plan data is low-velocity; the CDR non-functional requirements
  expect recipients to cache and cap public traffic at 300 TPS across all consumers. See
  `rate-limits/alinta-energy-rate-limits.yml`.
- **Sibling brand.** Alinta's second retail brand, Lumo Energy, is a separate data holder:
  `https://cdr.energymadeeasy.gov.au/lumo/cds-au/v1/energy/plans` (175 plans).
