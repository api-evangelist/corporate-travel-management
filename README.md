# Corporate Travel Management (corporate-travel-management)

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
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

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

None documented. Corporate Travel Management publishes no developer portal, no API documentation and no machine-readable API contract — no OpenAPI, Swagger, GraphQL SDL, AsyncAPI, Protobuf or MCP manifest exists on any CTM host.

One **undocumented** API host is recorded in `apis.yml`: the **CTM Portal Host API** at `https://portal-host.api.ctmsmart.com/api`, identified from the CTM Portal's own inline bootstrap configuration (`hostApiUrl`). It is live (`GET /` returns `Healthy`), runs on ASP.NET Core with policy-based authorization and `application/problem+json` errors, and is bearer-token protected through CTM's Auth0 tenant. Every specification path returns 404. It is listed as an observed integration surface, not as an available API — there is no documentation, sign-up, sandbox or terms permitting third-party use.

See [review.yml](review.yml) for the full probe log and HTTP status of every URL tested.

## What CTM does publish

| Surface | Finding |
| --- | --- |
| Identity discovery | Auth0 tenant `travelctm-au-production.au.auth0.com` serves anonymous [OIDC Discovery](well-known/corporate-travel-management-openid-configuration.json) and [RFC 8414](well-known/corporate-travel-management-oauth-authorization-server.json) metadata plus JWKS — the only machine-readable documents CTM operates. |
| Packages | Four first-party npm packages: `@travelctm/compass`, `@travelctm/icons`, `@travelctm/auth0-utils`, and `scout-portal-prod` (the CTM Scout widget the portal loads from unpkg). None is an API client SDK. |
| Developer docs | [compass.ctmdevelopment.com](https://compass.ctmdevelopment.com/) — CTM's Compass design system documentation (Foundations / Components / Patterns). The only developer-facing documentation CTM publishes, and it documents UI, not APIs. |
| Compliance | A real [PCI DSS v3.2.1 SAQ D Attestation of Compliance](https://au.travelctm.com/wp-content/uploads/2021/09/Payment-Card-Industry-Data-Security-Standard.pdf), self-assessed April 2021, not refreshed to PCI DSS v4. Part 2f names Sabre as CTM's GDS and Tramada Systems as its agency/mid-office platform. |
| Trust centre | `trust.travelctm.com` serves an UpGuard Trust Center shell whose public API returns `{"status":"not_published"}` — provisioned and never published. |
| Status / lifecycle | Nothing. No status page, versioning policy, deprecation policy, changelog, SLA or roadmap. |
| security.txt | None on any CTM host. |

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
