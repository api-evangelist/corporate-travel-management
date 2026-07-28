# Corporate Travel Management (corporate-travel-management)

Corporate Travel Management (CTM) is a Brisbane-founded, ASX-listed (CTD) travel management company established in 1994 that procures, books and services corporate, government, meetings and events, resources, sport and leisure travel across Australia and New Zealand, North America, Europe and Asia. CTM sits on the buy side of the travel distribution chain: an IATA-accredited agency that aggregates supplier content from GDS, direct airline APIs and airline NDC connections and resells it to corporate clients through its own proprietary technology stack — the Lightning online booking tool, CTM Portal, CTM Mobile app, CTM Approve pre-trip approval, CTM Fare Forecaster and CTM Data Hub reporting.

Its API posture is closed. CTM publishes no developer portal and no public API: `developer.travelctm.com`, `developers.travelctm.com`, `api.travelctm.com` and `docs.travelctm.com` do not resolve in DNS, and `/developers`, `/api`, `/docs`, `/openapi.json`, `/swagger.json`, `/api-docs` and `/.well-known/security.txt` all return HTTP 404 across the AU, US and UK sites. The only live non-marketing front door is a customer login — CTM Portal at `portal.travelctm.com` and `www.ctmsmart.com.au`.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/corporate-travel-management/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/corporate-travel-management/refs/heads/main/apis.yml)

## Tags

- Travel
- Australia
- Corporate Travel
- Travel Management Company
- Aviation
- NDC
- Distribution
- Booking
- Hotels
- Meetings and Events

## Timestamps

- **Created:** 2026-07-28
- **Modified:** 2026-07-28

## APIs

None. Corporate Travel Management publishes no documented public API. `apis[]` in `apis.yml` is intentionally empty — see [review.yml](review.yml) for the full probe log and HTTP status of every URL tested.

## Switching Cost

| Dimension | Finding |
| --- | --- |
| Interface shape | `proprietary-undocumented` — an integration surface for client HR, expense, finance, ERP and SSO systems is asserted on the technology pages, but no endpoint, schema, auth scheme or version is published. No standard is referenced for any CTM-published interface. |
| Second source | `alternatives-with-migration` — Amex GBT/Egencia, BCD Travel, FCM Travel and Corporate Traveller (Flight Centre), Navan, TravelPerk, or SAP Concur Travel with a separate fulfilment agency. Programs are genuinely re-tendered; moving is a re-implementation project. |
| Exit path | `export-on-request` — no export operation exists because no API exists. Only the GDPR/UK/Swiss and California personal-data portability rights in the privacy policy, exercised by email to `privacy@travelctm.com` or `DPO@travelctm.com`. CTM Data Hub documents no export, feed or connector. |
| Identifier portability | Not published. IATA airline/airport codes, PNR record locators and an IATA agency number are implied by CTM's accreditation; traveller profiles, policy objects, approvals, Data Hub rows and unused-ticket credits are keyed on undocumented vendor-internal identifiers. |
| Contractual lock-in | No customer services agreement is published. The website terms of use — self-scoped to "all websites and online travel platforms owned by Corporate Travel Management Limited" — prohibit "using automated screen capture or screen scraping technologies to obtain information of any sort from this site" and prohibit providing information from the site to any third party. |
| Access gate | `commercial-agreement` — no developer program, key request, sandbox or partner tier exists. Access follows from being a contracted CTM client; "Existing customers can access the CTM Portal". |
| Distribution model | `aggregator-reseller` — buy-side intermediary aggregating GDS, direct airline APIs and NDC, reselling through its own OBT and agent desk. Still GDS-intermediated for the bulk of content. |
| NDC posture | NDC consumer, not publisher. Lightning ingests live NDC from Qantas (Premium NDC connection), American Airlines and United Airlines. No IATA certification level claimed, no NDC endpoint published. |

## Properties

- [Website](https://www.travelctm.com/)
- [Website — Australia/New Zealand](https://au.travelctm.com/)
- [Portal (customers only)](https://portal.travelctm.com/)
- [Login — CTM Portal Australasia](https://www.ctmsmart.com.au/)
- [Technology](https://au.travelctm.com/technology/)
- [Lightning](https://au.travelctm.com/technology/lightning/)
- [NDC](https://au.travelctm.com/ndc/)
- [Travel Reporting — CTM Data Hub](https://au.travelctm.com/technology/travel-reporting/)
- [Blog](https://au.travelctm.com/blog/)
- [Blog RSS](https://au.travelctm.com/blog/feed/)
- [News](https://au.travelctm.com/news/)
- [Terms of Service](https://au.travelctm.com/terms-and-conditions/)
- [Privacy Policy](https://au.travelctm.com/privacy/)
- [Investor Relations](https://investor.travelctm.com.au/)
- [LinkedIn](https://www.linkedin.com/company/corporate-travel-management-ctm-group)

## Maintainers

- Kin Lane — kin@apievangelist.com — https://kinlane.com
