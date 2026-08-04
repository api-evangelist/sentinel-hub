# Sentinel Hub

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

Sentinel Hub by Sinergise (acquired by Planet Labs in 2022) is a cloud-based satellite imagery
processing platform providing REST APIs for accessing, processing, and analysing data from
Sentinel, Landsat, MODIS, and commercial satellite constellations. APIs deliver raw imagery,
rendered images, and geospatial statistics on demand using custom EvalScript processing without
requiring data downloads or local storage.

## APIs

| API | Description |
|-----|-------------|
| [Process API](https://docs.sentinel-hub.com/api/latest/api/process/) | On-demand imagery retrieval and processing with custom EvalScripts |
| [Catalog API](https://docs.sentinel-hub.com/api/latest/api/catalog/) | STAC-compliant geospatial data discovery and search |
| [Statistical API](https://docs.sentinel-hub.com/api/latest/api/statistical/) | Band statistics and histograms without image downloads |
| [Batch Processing API](https://docs.sentinel-hub.com/api/latest/api/batch-processing/) | Large-area asynchronous processing at 1/3 PU cost |
| [OGC Services](https://docs.sentinel-hub.com/api/latest/api/ogc/) | WMS, WCS, WFS, WMTS for GIS application integration |
| [BYOC API](https://docs.sentinel-hub.com/api/latest/data/byoc/) | Ingest custom Cloud-Optimised GeoTIFFs alongside public collections |

## Authentication

OAuth2 Client Credentials flow. Register an OAuth client in the
[Sentinel Hub Dashboard](https://apps.sentinel-hub.com/dashboard/) to obtain a client ID and
secret. Exchange credentials for a JWT access token at:

```
POST https://services.sentinel-hub.com/auth/realms/main/protocol/openid-connect/token
```

Reuse tokens within their validity window to avoid token-request rate limits.

## Base URL

```
https://services.sentinel-hub.com
```

## Pricing

Billing is based on Processing Units (PUs). One PU equals a 512x512 pixel request using 3
input bands in 8/16-bit format. Subscriptions grant a monthly PU and request allocation that
does not roll over. See [plans/sentinel-hub-plans-pricing.yml](plans/sentinel-hub-plans-pricing.yml)
for details.

## Resources

- [API Documentation](https://docs.sentinel-hub.com/api/latest/)
- [API Reference (OpenAPI)](https://docs.sentinel-hub.com/api/latest/reference/)
- [Dashboard](https://apps.sentinel-hub.com/dashboard/)
- [Community Forum](https://forum.sentinel-hub.com/)
- [GitHub](https://github.com/sentinel-hub)
- [Planet Pricing](https://www.planet.com/pricing/)
