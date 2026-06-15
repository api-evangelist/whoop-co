# WHOOP (whoop-co)

WHOOP is a wearable health and performance company whose wrist-worn strap (WHOOP 5.0 and medical-grade WHOOP MG) measures heart rate, HRV, respiratory rate, skin temperature, and SpO2 24/7 to compute daily Recovery, Strain, and Sleep Performance scores. The WHOOP Developer Platform exposes member fitness data through an OAuth-protected REST API (v2) covering physiological cycles, sleep, workouts, recovery, and body measurements, plus webhooks for resource updates and a Trusted Partner API for lab/diagnostics integrations.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/whoop-co/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/whoop-co/refs/heads/main/apis.yml)

## Scope

- **Position:** Consuming
- **Access:** 3rd-Party

## Tags

- Fitness
- Wearables
- Health
- Recovery
- Sleep
- Strain
- Heart Rate
- Workout
- Biometrics

## Timestamps

- **Created:** 2026-05-25
- **Modified:** 2026-05-25

## APIs

### WHOOP API

The WHOOP API exposes member fitness, strain, recovery, sleep, workout, and body measurement data captured by the WHOOP wrist-worn wearable. v2 endpoints return UUID-based resources covering physiological cycles, sleep activities, workouts, recovery scores, and user profile data, with webhook notifications for `recovery.updated`, `recovery.deleted`, `sleep.updated`, `sleep.deleted`, `workout.updated`, and `workout.deleted` events. OAuth 2.0 authorization-code flow protects member data; a separate client-credentials flow (Trusted Partner) supports lab-grade health partners. Rate limits default to 100 requests/minute and 10,000 requests/day per client.

- **Human URL:** [https://developer.whoop.com/api/](https://developer.whoop.com/api/)
- **Base URL:** `https://api.prod.whoop.com/developer`

#### Tags

- Fitness
- Wearables
- Health
- Recovery
- Sleep
- Strain
- Workout

#### Properties

- [Documentation](https://developer.whoop.com/api/)
- [Documentation](https://developer.whoop.com/docs/introduction/)
- [OpenAPI](https://api.prod.whoop.com/developer/doc/openapi.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [OpenAPI](openapi/whoop-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/whoop-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/whoop-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [JSON Schema](json-schema/whoop-cycle-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [JSON Schema](json-schema/whoop-recovery-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [JSON Schema](json-schema/whoop-sleep-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [JSON Schema](json-schema/whoop-workout-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [JSON-LD](json-ld/whoop-co-context.jsonld) — [JSON-LD](https://www.w3.org/TR/json-ld11/)
- [Example](examples/whoop-list-workouts-example.json)
- [Example](examples/whoop-get-recovery-example.json)
- [Example](examples/whoop-list-sleep-example.json)
- [Example](examples/whoop-webhook-sleep-updated-example.json)
- [Spectral Ruleset](rules/whoop-rules.yml)
- [Authentication](https://developer.whoop.com/docs/developing/oauth/)
- [Rate Limits](https://developer.whoop.com/docs/developing/rate-limiting/)
- [Webhooks](https://developer.whoop.com/docs/developing/webhooks/)

### WHOOP Trusted Partner API

The WHOOP Trusted Partner API enables lab and diagnostics partners to manage lab requisitions, service requests, appointments, and diagnostic report results for WHOOP members. It uses an OAuth 2.0 client-credentials flow scoped to `whoop-partner/token`, and exposes endpoints for retrieving and updating service-request status, creating diagnostic-report observations, and generating test data in development environments.

- **Human URL:** [https://developer.whoop.com/api/](https://developer.whoop.com/api/)
- **Base URL:** `https://api.prod.whoop.com/developer`

#### Tags

- Healthcare
- Diagnostics
- Labs
- Service Requests
- Partner

#### Properties

- [Documentation](https://developer.whoop.com/api/)
- [OpenAPI](openapi/whoop-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/whoop-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/whoop-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

## Common Properties

- [Portal](https://www.whoop.com/)
- [Documentation](https://developer.whoop.com/)
- [Documentation](https://developer.whoop.com/docs/introduction/)
- [Getting Started](https://developer.whoop.com/docs/developing/oauth/)
- [Authentication](https://developer.whoop.com/docs/developing/oauth/)
- [Rate Limits](https://developer.whoop.com/docs/developing/rate-limiting/)
- [Webhooks](https://developer.whoop.com/docs/developing/webhooks/)
- [Support](https://developer.whoop.com/docs/developing/support/)
- [Migration](https://developer.whoop.com/docs/developing/v1-v2-migration/)
- [Developer Dashboard](https://developer-dashboard.whoop.com/)
- [Pricing](https://www.whoop.com/us/en/membership/)
- [Support](https://support.whoop.com/)
- [LinkedIn](https://www.linkedin.com/company/whoop/)
- [Twitter](https://twitter.com/whoop)
- [Contact Us](https://www.whoop.com/us/en/contact-us/)
- [Privacy Policy](https://www.whoop.com/legal/privacy-policy/)
- [Terms of Service](https://www.whoop.com/legal/terms-of-use/)
- [A P I Terms](https://www.whoop.com/legal/api-terms/)
- [Plans](plans/whoop-co-plans-pricing.yml)
- [Rate Limits](rate-limits/whoop-co-rate-limits.yml)
- [Fin Ops](finops/whoop-co-finops.yml)
- [Vocabulary](vocabulary/whoop-co-vocabulary.yml)
- [Features](undefined)

## Maintainers

**FN:** Kin Lane
**Email:** info@apievangelist.com
**URL:** https://apievangelist.com
