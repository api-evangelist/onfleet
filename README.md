# Onfleet (onfleet)

Onfleet is an AI-powered last-mile delivery management platform that orchestrates fleet operations,
dispatch, route optimization, and customer experience across internal and outsourced delivery fleets.
The platform powers 400M+ deliveries for brands including Eaze, Total Wine & More, Pizza Hut, Kroger,
and Urbanstems across industries from prepared meals and grocery to cannabis, pharmacy, and
furniture. Onfleet exposes a comprehensive REST API v2.7 for tasks, workers, route plans, route
optimization, orders, recipients, destinations, organizations/teams, and webhooks — backed by
official SDKs in Python, Node.js, PHP, Java, and Go, plus the 150+ courier Onfleet Connect network.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/onfleet/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/onfleet/refs/heads/main/apis.yml)

## Scope

- **Position:** Consuming
- **Access:** 3rd-Party

## Tags

- Last Mile Delivery
- Logistics
- Fleet Management
- Dispatch
- Route Optimization
- Courier
- Drivers
- Tracking
- Geocoding
- Webhooks
- AI
- SaaS

## Timestamps

- **Created:** 2026-05-25T00:00:00.000Z
- **Modified:** 2026-05-25

## APIs

### Onfleet Tasks API

Create, list, fetch, update, clone, force-complete, and delete pickup/dropoff tasks. Tasks are the
atomic unit of work in Onfleet — each has a destination, recipient, completion window, optional
dependencies, and a state lifecycle (Unassigned → Assigned → Active → Completed). Supports
batch creation (up to 100 per request) and assignment to workers via the containers endpoint.

- **Human URL:** [https://docs.onfleet.com/reference/tasks](https://docs.onfleet.com/reference/tasks)
- **Base URL:** `https://onfleet.com/api/v2`

#### Tags

- Last Mile Delivery
- Logistics
- Tasks

#### Properties

- [Documentation](https://docs.onfleet.com/reference/tasks.md)
- [Documentation](https://docs.onfleet.com/reference/create-task.md)
- [Documentation](https://docs.onfleet.com/reference/list-tasks.md)
- [OpenAPI](openapi/onfleet-tasks-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/onfleet-tasks-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/onfleet-tasks-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [JSON Schema](json-schema/onfleet-task-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [JSON Structure](json-structure/onfleet-task-structure.json)
- [Example](examples/onfleet-create-task-example.json)

### Onfleet Workers API

Manage drivers — create, list, update, delete, fetch a worker's assigned tasks, and pull a
delivery manifest for compliance reporting. Workers are bound to teams, have vehicle metadata
(CAR/MOTORCYCLE/BICYCLE/TRUCK), and report duty status and location.

- **Human URL:** [https://docs.onfleet.com/reference/workers](https://docs.onfleet.com/reference/workers)
- **Base URL:** `https://onfleet.com/api/v2`

#### Tags

- Last Mile Delivery
- Drivers
- Workers

#### Properties

- [Documentation](https://docs.onfleet.com/reference/create-worker.md)
- [Documentation](https://docs.onfleet.com/reference/delivery-manifest.md)
- [OpenAPI](openapi/onfleet-workers-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/onfleet-workers-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/onfleet-workers-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [JSON Schema](json-schema/onfleet-worker-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [Example](examples/onfleet-create-worker-example.json)

### Onfleet Route Plans API

Create and manage route plans — ordered sequences of tasks assigned to a worker for a time window
— and kick off asynchronous route optimization jobs (task-based, vehicle-based, or auto-dispatch).
Optimization endpoints are an Enterprise plan feature; results delivered via the
routeOptimizationJobCompleted webhook.

- **Human URL:** [https://docs.onfleet.com/reference/routeplan](https://docs.onfleet.com/reference/routeplan)
- **Base URL:** `https://onfleet.com/api/v2`

#### Tags

- Last Mile Delivery
- Route Optimization
- Route Plans

#### Properties

- [Documentation](https://docs.onfleet.com/reference/routeplan.md)
- [Documentation](https://docs.onfleet.com/reference/route-optimization.md)
- [OpenAPI](openapi/onfleet-route-plans-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/onfleet-route-plans-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/onfleet-route-plans-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [JSON Schema](json-schema/onfleet-route-plan-schema.json) — [JSON Schema](https://json-schema.org/specification)

### Onfleet Orders API

Orders represent a pickup-dropoff task pair shared between a courier organization and its clients
on the Onfleet Connect network. Clients can quote, create, update, clone, cancel, or reject orders;
couriers can create orders on behalf of clients and respond to them.

- **Human URL:** [https://docs.onfleet.com/reference/orders](https://docs.onfleet.com/reference/orders)
- **Base URL:** `https://onfleet.com/api/v2`

#### Tags

- Last Mile Delivery
- Orders
- Courier

#### Properties

- [Documentation](https://docs.onfleet.com/reference/orders.md)
- [OpenAPI](openapi/onfleet-orders-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/onfleet-orders-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/onfleet-orders-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Onfleet Organizations & Teams API

Look up your own organization and connected delegatee organizations on Onfleet Connect, manage
administrators (Super and Standard, optionally read-only), create and list teams, and trigger
Team Auto-Dispatch — Onfleet's batch task-to-worker assignment engine (Beta).

- **Human URL:** [https://docs.onfleet.com/reference/team-auto-dispatch](https://docs.onfleet.com/reference/team-auto-dispatch)
- **Base URL:** `https://onfleet.com/api/v2`

#### Tags

- Last Mile Delivery
- Organizations
- Teams
- Administrators

#### Properties

- [Documentation](https://docs.onfleet.com/reference/team-auto-dispatch.md)
- [OpenAPI](openapi/onfleet-organizations-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/onfleet-organizations-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/onfleet-organizations-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Onfleet Recipients API

Create and look up end customers (recipients) by ID, name, or E.164 phone number. Recipients carry
SMS notification preferences and metadata, and can be reused across tasks.

- **Human URL:** [https://docs.onfleet.com/reference/recipients](https://docs.onfleet.com/reference/recipients)
- **Base URL:** `https://onfleet.com/api/v2`

#### Tags

- Last Mile Delivery
- Recipients
- Customers

#### Properties

- [OpenAPI](openapi/onfleet-recipients-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/onfleet-recipients-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/onfleet-recipients-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [JSON Schema](json-schema/onfleet-recipient-schema.json) — [JSON Schema](https://json-schema.org/specification)

### Onfleet Destinations API

Manage geocoded physical addresses used as task pickup/dropoff locations. Accepts a parsed
address structure or a single `unparsed` field; coordinates are returned as GeoJSON
[longitude, latitude].

- **Human URL:** [https://docs.onfleet.com/reference/destinations](https://docs.onfleet.com/reference/destinations)
- **Base URL:** `https://onfleet.com/api/v2`

#### Tags

- Last Mile Delivery
- Destinations
- Geocoding

#### Properties

- [Documentation](https://docs.onfleet.com/reference/create-destination.md)
- [OpenAPI](openapi/onfleet-destinations-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/onfleet-destinations-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/onfleet-destinations-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [JSON Schema](json-schema/onfleet-destination-schema.json) — [JSON Schema](https://json-schema.org/specification)

### Onfleet Webhooks API

Register HTTPS callbacks against 27 trigger types covering task lifecycle, worker duty/CRUD,
route plan state changes, SMS recipient events, and async job completions (auto-dispatch, task
batch create, route optimization). Payloads are signed with HMAC-SHA256 using the secret
obtained from /webhooks/secret.

- **Human URL:** [https://docs.onfleet.com/reference/webhooks](https://docs.onfleet.com/reference/webhooks)
- **Base URL:** `https://onfleet.com/api/v2`

#### Tags

- Last Mile Delivery
- Webhooks
- Events

#### Properties

- [Documentation](https://docs.onfleet.com/reference/webhooks.md)
- [Documentation](https://docs.onfleet.com/reference/secrets.md)
- [OpenAPI](openapi/onfleet-webhooks-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/onfleet-webhooks-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/onfleet-webhooks-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [AsyncAPI](asyncapi/onfleet-webhooks-asyncapi.yml) — [AsyncAPI Specification](https://www.asyncapi.com/docs/reference/specification/latest)
- [Example](examples/onfleet-webhook-task-completed-example.json)

## Common Properties

- [Arazzo Workflows](arazzo/) — [Arazzo Specification](https://spec.openapis.org/arazzo/latest.html)
- [Portal](https://onfleet.com)
- [Documentation](https://docs.onfleet.com/)
- [Documentation](https://docs.onfleet.com/reference/introduction)
- [Getting Started](https://docs.onfleet.com/reference/setup-tutorial)
- [Documentation](https://docs.onfleet.com/reference/data-types-and-response-formats)
- [Documentation](https://docs.onfleet.com/reference/querying-by-metadata)
- [Changelog](https://docs.onfleet.com/changelog/api-documentation-updates-may-2026)
- [Changelog](https://docs.onfleet.com/changelog/order-endpoints)
- [Changelog](https://docs.onfleet.com/changelog/custom-fields)
- [Status Page](https://status.onfleet.com)
- [Blog](https://onfleet.com/blog)
- [Sign Up](https://onfleet.com/signup)
- [Pricing](https://onfleet.com/pricing)
- [Terms of Service](https://onfleet.com/legal)
- [Privacy Policy](https://onfleet.com/privacy)
- [Support](https://onfleet.com/support)
- [GitHub Organization](https://github.com/onfleet)
- [SDK](https://github.com/onfleet/pyonfleet)
- [SDK](https://github.com/onfleet/node-onfleet)
- [SDK](https://github.com/onfleet/php-onfleet)
- [SDK](https://github.com/onfleet/java-onfleet)
- [SDK](https://github.com/onfleet/gonfleet)
- [SDK](https://github.com/onfleet/ruby-onfleet)
- [Code Examples](https://github.com/onfleet/developer)
- [Documentation](https://app.getpostman.com/run-collection/14168007-2dc047db-9556-442a-b643-e913027a74cf)
- [Plans](plans/onfleet-plans-pricing.yml)
- [Rate Limits](rate-limits/onfleet-rate-limits.yml)
- [Fin Ops](finops/onfleet-finops.yml)
- [JSON-LD](json-ld/onfleet-context.jsonld) — [JSON-LD](https://www.w3.org/TR/json-ld11/)
- [Vocabulary](vocabulary/onfleet-vocabulary.yml)
- [Rules](rules/onfleet-rules.yml)
- [Features](undefined)
- [Integrations](undefined)

## Maintainers

**FN:** Kin Lane
**Email:** info@apievangelist.com
**URL:** https://apievangelist.com
