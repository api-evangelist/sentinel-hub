# Sentinel Hub

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
