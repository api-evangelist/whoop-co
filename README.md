# WHOOP (whoop-co)

WHOOP is a wearable health and performance company whose wrist-worn strap (WHOOP 5.0 and the medical-grade WHOOP MG) measures heart rate, heart-rate variability, respiratory rate, skin temperature, and SpO2 24/7 to compute daily Recovery, Strain, and Sleep Performance scores. The WHOOP Developer Platform exposes member fitness data through an OAuth-protected REST API (v2) covering physiological cycles, sleep, workouts, recovery, and body measurements, plus webhooks for resource updates and a Trusted Partner API for lab and diagnostics integrations.

**URL:** [Visit APIs.json](https://raw.githubusercontent.com/api-evangelist/whoop-co/refs/heads/main/apis.yml)

**Run:** [Capabilities Using Naftiko](https://github.com/naftiko/fleet?utm_source=api-evangelist&utm_medium=readme&utm_campaign=company-api-evangelist&utm_content=repo)

## Tags

- Fitness, Wearables, Health, Recovery, Sleep, Strain, Heart Rate, Workout, Biometrics

## Timestamps

- **Created:** 2026-05-25
- **Modified:** 2026-05-25

## At a Glance

| Surface | Value |
|---|---|
| Base URL | `https://api.prod.whoop.com/developer` |
| Authentication | OAuth 2.0 — Authorization Code (member data) and Client Credentials (Trusted Partner) |
| Authorization URL | `https://api.prod.whoop.com/oauth/oauth2/auth` |
| Token URL | `https://api.prod.whoop.com/oauth/oauth2/token` |
| Developer Dashboard | https://developer-dashboard.whoop.com |
| OpenAPI | https://api.prod.whoop.com/developer/doc/openapi.json |
| Rate Limits | 100 req/min and 10,000 req/day per OAuth client |
| Webhook Events | `recovery.updated`, `recovery.deleted`, `sleep.updated`, `sleep.deleted`, `workout.updated`, `workout.deleted` |
| Signature | `X-WHOOP-Signature` = `base64(HMAC-SHA256(timestamp + body, client_secret))` |

## Member Data Scopes

| Scope | Purpose |
|---|---|
| `read:recovery` | Recovery score, HRV, resting heart rate |
| `read:cycles` | Day Strain, average heart rate, physiological cycles |
| `read:workout` | Workout Strain, average heart rate, HR-zone durations |
| `read:sleep` | Sleep performance % and duration per stage |
| `read:profile` | Basic profile — name, email |
| `read:body_measurement` | Height, weight, max heart rate |
| `offline` | Returns a refresh token alongside the access token |

## APIs

### WHOOP API
The WHOOP API exposes member fitness, strain, recovery, sleep, workout, and body-measurement data. v2 endpoints use UUID identifiers (Sleep, Workout) and integer IDs (Cycle, User) and support cursor pagination. Webhooks push delta notifications for recovery, sleep, and workout events.

**Human URL:** [https://developer.whoop.com/api/](https://developer.whoop.com/api/)

- [WHOOP API Reference](https://developer.whoop.com/api/)
- [Developer Platform Docs](https://developer.whoop.com/docs/introduction/)
- [Official OpenAPI (JSON)](https://api.prod.whoop.com/developer/doc/openapi.json)
- [OpenAPI (mirrored)](openapi/whoop-api-openapi.yml)
- [JSON Schema — Cycle](json-schema/whoop-cycle-schema.json)
- [JSON Schema — Recovery](json-schema/whoop-recovery-schema.json)
- [JSON Schema — Sleep](json-schema/whoop-sleep-schema.json)
- [JSON Schema — Workout](json-schema/whoop-workout-schema.json)
- [JSON-LD](json-ld/whoop-co-context.jsonld)
- [Example — List Workouts](examples/whoop-list-workouts-example.json)
- [Example — Get Recovery](examples/whoop-get-recovery-example.json)
- [Example — List Sleep](examples/whoop-list-sleep-example.json)
- [Example — `sleep.updated` Webhook](examples/whoop-webhook-sleep-updated-example.json)
- [Spectral Rules](rules/whoop-rules.yml)
- [Naftiko Capability — Cycle](capabilities/whoop-cycle.yaml)
- [Naftiko Capability — Recovery](capabilities/whoop-recovery.yaml)
- [Naftiko Capability — Sleep](capabilities/whoop-sleep.yaml)
- [Naftiko Capability — Workout](capabilities/whoop-workout.yaml)
- [Naftiko Capability — User](capabilities/whoop-user.yaml)

### WHOOP Trusted Partner API
Lab and diagnostics partners use a client-credentials flow (`whoop-partner/token`) to manage lab requisitions, service requests, status updates, and diagnostic report results for WHOOP members. Includes a test-data endpoint for development.

**Human URL:** [https://developer.whoop.com/api/](https://developer.whoop.com/api/)

- [Partner Endpoints — WHOOP API Reference](https://developer.whoop.com/api/)
- [OpenAPI (mirrored)](openapi/whoop-api-openapi.yml)
- [Naftiko Capability — Partner](capabilities/whoop-partner.yaml)

## Plans

WHOOP is sold as an annual membership that bundles hardware and unlimited app + API access. There is no consumption-based pricing on the Developer Platform — API access is gated by rate limits rather than metered.

| Plan | Annual | What it adds |
|---|---|---|
| WHOOP ONE | $199 | WHOOP 5.0 strap, daily Recovery/Strain/Sleep, Stress Monitor, full Developer API access |
| WHOOP PEAK | $239 | Health Monitor, Healthspan, WHOOP Coach (generative AI), wireless PowerPack |
| WHOOP LIFE | $359 | WHOOP MG medical-grade strap with ECG and blood-pressure insights |

See [plans/whoop-co-plans-pricing.yml](plans/whoop-co-plans-pricing.yml).

## Rate Limits

| Window | Limit | Scope |
|---|---|---|
| 60 seconds | 100 requests | per OAuth client |
| 24 hours | 10,000 requests | per OAuth client |

Headers: `X-RateLimit-Limit` (e.g. `100;window=60`), `X-RateLimit-Remaining`, `X-RateLimit-Reset`. Throttled responses are HTTP 429. See [rate-limits/whoop-co-rate-limits.yml](rate-limits/whoop-co-rate-limits.yml).

## FinOps

See [finops/whoop-co-finops.yml](finops/whoop-co-finops.yml). Subscription-based, member-allocated, no per-call metering.

## Resources

- [Portal](https://www.whoop.com/)
- [Developer Platform](https://developer.whoop.com/)
- [API Reference](https://developer.whoop.com/api/)
- [OAuth Guide](https://developer.whoop.com/docs/developing/oauth/)
- [Rate Limiting](https://developer.whoop.com/docs/developing/rate-limiting/)
- [Webhooks](https://developer.whoop.com/docs/developing/webhooks/)
- [v1 → v2 Migration](https://developer.whoop.com/docs/developing/v1-v2-migration/)
- [Developer Dashboard](https://developer-dashboard.whoop.com/)
- [Pricing / Membership](https://www.whoop.com/us/en/membership/)
- [Support](https://support.whoop.com/)
- [API Terms](https://www.whoop.com/legal/api-terms/)

## Maintainers

- Kin Lane — [apievangelist.com](https://apievangelist.com) — info@apievangelist.com
