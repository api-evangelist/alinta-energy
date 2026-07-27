---
name: Check Alinta Energy CDR availability and outages
description: Poll Alinta Energy's public CDR data-holder health check and planned-outage feed before and during data-sharing calls.
api: openapi/alinta-energy-cds-common-api-openapi.yml
method: generated
generated: '2026-07-27'
operations: [getStatus, getOutages]
---

# Check Alinta Energy CDR availability and outages

These two operations are the **only** API Alinta Energy serves from its own
infrastructure that anyone can call anonymously. They are the CDR Common Discovery pair
mandated of every data holder, and they are the provider's entire operational-transparency
surface — there is no HTML status page.

Host: `https://public.cdr.alintaenergy.com.au/cds-au/v1`
Sibling brand (Lumo Energy): `https://public.cdr.lumoenergy.com.au/cds-au/v1`

## Steps

1. **Check status** — `getStatus`
   `GET /discovery/status` with header `x-v: 1`.
   Response: `data.status` is one of `OK`, `PARTIAL_FAILURE`, `UNAVAILABLE`,
   `SCHEDULED_OUTAGE`, plus `data.updateTime` and `data.explanation`.
   Confirmed live on 2026-07-27:
   `{"data":{"status":"OK","updateTime":"2026-07-27T20:26:07Z","explanation":"All services operational"}}`.

2. **Check planned outages** — `getOutages`
   `GET /discovery/outages` with header `x-v: 1`.
   Response: `data.outages[]` with `outageTime`, `duration`, `isPartial`, `explanation`.
   Confirmed live on 2026-07-27: empty array.

3. **Gate your data-sharing work on the result.** If `status` is not `OK`, or an outage
   window covers now, back off rather than retrying resource calls — under the CDR
   non-functional requirements a data holder may throttle or reject excess traffic, and
   an outage returns `503` (`urn:au-cds:error:cds-all:Service/Unavailable`).

## Rules

- **No authentication.** Only the mandatory `x-v: 1` header. Do not send FAPI headers on
  these unauthenticated calls; `x-fapi-auth-date` is not required here.
- **This is a poll, not a subscription.** Alinta publishes no AsyncAPI, webhooks or event
  stream — outage notification is polling-only.
- **Planned outages** are required to be published to data recipients with at least one
  week's lead time (critical security fixes excepted), against a 99.5% monthly
  availability obligation. See `lifecycle/alinta-energy-lifecycle.yml`.
- **These endpoints are in the CDR "high priority" performance tier** (1000ms threshold
  for 95% of calls per hour).
- **Nothing else resolves on this host.** `/energy/plans`, `/common/customer` and `/` all
  return `404` — by design (see `overlays/alinta-energy-cds-common-api-overlay.yaml`).
