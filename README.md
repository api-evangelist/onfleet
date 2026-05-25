# Onfleet (onfleet)

Onfleet is an AI-powered last-mile delivery management platform that orchestrates fleet operations, dispatch, route optimization, and customer experience across internal and outsourced delivery fleets. The platform powers 400M+ deliveries for brands including Eaze, Total Wine & More, Pizza Hut, Kroger, and Urbanstems across industries from prepared meals and grocery to cannabis, pharmacy, and furniture. Onfleet exposes a comprehensive REST API v2.7 for tasks, workers, route plans, route optimization, orders, recipients, destinations, organizations/teams, and webhooks — backed by official SDKs in Python, Node.js, PHP, Java, and Go, plus the 150+ courier Onfleet Connect network.

**URL:** [Visit APIs.json](https://raw.githubusercontent.com/api-evangelist/onfleet/refs/heads/main/apis.yml)

**Run:** [Capabilities Using Naftiko](https://github.com/naftiko/fleet?utm_source=api-evangelist&utm_medium=readme&utm_campaign=company-api-evangelist&utm_content=repo)

## Tags

 - Last Mile Delivery, Logistics, Fleet Management, Dispatch, Route Optimization, Courier, Drivers, Tracking, Geocoding, Webhooks, AI, SaaS

## Timestamps

- **Created:** 2026-05-25
- **Modified:** 2026-05-25

## Plans (US)

| Plan | Price | Tasks Included | Users | Highlights |
|---|---|---|---|---|
| Launch | $619 / mo | 2,500 | Unlimited | Proof of delivery, driver-dispatcher chat, basic route optimization, branded tracking, API access |
| Scale | $1,349 / mo | 5,000 | Unlimited | Advanced route optimization with API, barcode scanning, ID verification, auto-dispatch, custom fields |
| Enterprise | $3,099+ / mo | 10,000+ | Unlimited | Multi-brand/region, SSO, lifetime reporting, Route Optimization API, premium support |
| Courier Suite (add-on) | $299+ / mo | — | — | Client portals, invoicing, label printing, e-commerce integrations |

## APIs

### Onfleet Tasks API
Create, list, fetch, update, clone, force-complete, and delete pickup/dropoff tasks. Tasks are the atomic unit of work — each carries a destination, recipient, completion window, optional dependencies, and a state lifecycle (Unassigned → Assigned → Active → Completed). Supports batch creation up to 100 per request and assignment to workers via the containers endpoint.

**Human URL:** [https://docs.onfleet.com/reference/tasks](https://docs.onfleet.com/reference/tasks)

- [Documentation — Tasks](https://docs.onfleet.com/reference/tasks.md)
- [Documentation — Create Task](https://docs.onfleet.com/reference/create-task.md)
- [Documentation — List Tasks](https://docs.onfleet.com/reference/list-tasks.md)
- [OpenAPI](openapi/onfleet-tasks-api-openapi.yml)
- [JSON Schema — Task](json-schema/onfleet-task-schema.json)
- [JSON Structure — Task](json-structure/onfleet-task-structure.json)
- [Example — Create Task](examples/onfleet-create-task-example.json)
- [Naftiko Capability — Tasks](capabilities/shared/tasks.yaml)

### Onfleet Workers API
Manage drivers — create, list, update, delete, fetch a worker's assigned tasks, and pull a delivery manifest for compliance reporting. Workers are bound to teams, have vehicle metadata (CAR / MOTORCYCLE / BICYCLE / TRUCK), and report duty status and location.

**Human URL:** [https://docs.onfleet.com/reference/workers](https://docs.onfleet.com/reference/workers)

- [Documentation — Create Worker](https://docs.onfleet.com/reference/create-worker.md)
- [Documentation — Delivery Manifest](https://docs.onfleet.com/reference/delivery-manifest.md)
- [OpenAPI](openapi/onfleet-workers-api-openapi.yml)
- [JSON Schema — Worker](json-schema/onfleet-worker-schema.json)
- [Example — Create Worker](examples/onfleet-create-worker-example.json)
- [Naftiko Capability — Workers](capabilities/shared/workers.yaml)

### Onfleet Route Plans API
Create and manage route plans — ordered sequences of tasks assigned to a worker for a time window — and kick off asynchronous route optimization jobs (task-based, vehicle-based, or auto-dispatch). Optimization endpoints are an Enterprise plan feature; results delivered via the `routeOptimizationJobCompleted` webhook.

**Human URL:** [https://docs.onfleet.com/reference/routeplan](https://docs.onfleet.com/reference/routeplan)

- [Documentation — Route Plans](https://docs.onfleet.com/reference/routeplan.md)
- [Documentation — Route Optimization](https://docs.onfleet.com/reference/route-optimization.md)
- [OpenAPI](openapi/onfleet-route-plans-api-openapi.yml)
- [JSON Schema — Route Plan](json-schema/onfleet-route-plan-schema.json)
- [Naftiko Capability — Route Plans](capabilities/shared/route-plans.yaml)

### Onfleet Orders API
Orders represent a pickup-dropoff task pair shared between a courier organization and its clients on the Onfleet Connect network. Clients can quote, create, update, clone, cancel, or reject orders; couriers can create orders on behalf of clients and respond to them.

**Human URL:** [https://docs.onfleet.com/reference/orders](https://docs.onfleet.com/reference/orders)

- [Documentation — Orders](https://docs.onfleet.com/reference/orders.md)
- [OpenAPI](openapi/onfleet-orders-api-openapi.yml)
- [Naftiko Capability — Orders](capabilities/shared/orders.yaml)

### Onfleet Organizations & Teams API
Look up your own organization and connected delegatee organizations on Onfleet Connect, manage administrators (Super and Standard, optionally read-only), create and list teams, and trigger Team Auto-Dispatch — Onfleet's batch task-to-worker assignment engine (Beta).

**Human URL:** [https://docs.onfleet.com/reference/team-auto-dispatch](https://docs.onfleet.com/reference/team-auto-dispatch)

- [Documentation — Team Auto-Dispatch](https://docs.onfleet.com/reference/team-auto-dispatch.md)
- [OpenAPI](openapi/onfleet-organizations-api-openapi.yml)

### Onfleet Recipients API
Create and look up end customers (recipients) by ID, name, or E.164 phone number. Recipients carry SMS notification preferences and metadata, and can be reused across tasks.

- [OpenAPI](openapi/onfleet-recipients-api-openapi.yml)
- [JSON Schema — Recipient](json-schema/onfleet-recipient-schema.json)

### Onfleet Destinations API
Manage geocoded physical addresses used as task pickup/dropoff locations. Accepts a parsed address structure or a single `unparsed` field; coordinates are returned as GeoJSON `[longitude, latitude]`.

- [Documentation — Create Destination](https://docs.onfleet.com/reference/create-destination.md)
- [OpenAPI](openapi/onfleet-destinations-api-openapi.yml)
- [JSON Schema — Destination](json-schema/onfleet-destination-schema.json)

### Onfleet Webhooks API
Register HTTPS callbacks against 27 trigger types covering task lifecycle, worker duty/CRUD, route plan state changes, SMS recipient events, and async job completions (auto-dispatch, task batch create, route optimization). Payloads are signed with HMAC-SHA256 using the secret obtained from `/webhooks/secret`.

**Human URL:** [https://docs.onfleet.com/reference/webhooks](https://docs.onfleet.com/reference/webhooks)

- [Documentation — Webhooks](https://docs.onfleet.com/reference/webhooks.md)
- [Documentation — Webhook Signing Secret](https://docs.onfleet.com/reference/secrets.md)
- [OpenAPI](openapi/onfleet-webhooks-api-openapi.yml)
- [AsyncAPI](asyncapi/onfleet-webhooks-asyncapi.yml)
- [Example — taskCompleted Webhook](examples/onfleet-webhook-task-completed-example.json)
- [Naftiko Capability — Webhooks](capabilities/shared/webhooks.yaml)

## Workflow Capabilities

- [Last-Mile Delivery](capabilities/last-mile-delivery.yaml) — Create recipient and destination, create a task, register webhook, assign to worker, observe lifecycle, and pull the delivery manifest.
- [Dispatch & Optimize](capabilities/dispatch-and-optimize.yaml) — Batch-create tasks, kick off route optimization, apply the result, and auto-dispatch the remainder for a team.

## Webhook Events

27 trigger types delivered via HTTPS POST with an `X-Onfleet-Signature` (HMAC-SHA256) header.

| ID | Trigger | Domain |
|---|---|---|
| 0 | taskStarted | Task |
| 1 | taskEta | Task (threshold) |
| 2 | taskArrival | Task (threshold) |
| 3 | taskCompleted | Task |
| 4 | taskFailed | Task |
| 5 | workerDuty | Worker |
| 6 | taskCreated | Task |
| 7 | taskUpdated | Task |
| 8 | taskDeleted | Task |
| 9 | taskAssigned | Task |
| 10 | taskUnassigned | Task |
| 12 | taskDelayed | Task (threshold) |
| 13 | taskCloned | Task |
| 14 | smsRecipientResponseMissed | SMS |
| 15 | workerCreated | Worker |
| 16 | workerDeleted | Worker |
| 17 | SMSRecipientOptOut | SMS |
| 18 | autoDispatchJobCompleted | Async Job |
| 19 | taskBatchCreateJobCompleted | Async Job |
| 20 | routeOptimizationJobCompleted | Async Job |
| 22 | routePlanCreated | Route Plan |
| 23 | routePlanStarted | Route Plan |
| 24 | routePlanCompleted | Route Plan |
| 25 | workerUpdated | Worker |
| 26 | routePlanUpdated | Route Plan |
| 27 | routePlanUnassigned | Route Plan |
| 28 | routePlanAssigned | Route Plan |
| 29 | routePlanDelayed | Route Plan |
| 30 | predictedTaskDelay | Task (AI-predicted) |

## SDKs and Tools

- [Python — pyonfleet](https://github.com/onfleet/pyonfleet)
- [Node.js — node-onfleet](https://github.com/onfleet/node-onfleet)
- [PHP — php-onfleet](https://github.com/onfleet/php-onfleet)
- [Java — java-onfleet](https://github.com/onfleet/java-onfleet)
- [Go — gonfleet](https://github.com/onfleet/gonfleet)
- [Ruby — ruby-onfleet (archived)](https://github.com/onfleet/ruby-onfleet)
- [Developer repository (example payloads)](https://github.com/onfleet/developer)
- [Postman Collection](https://app.getpostman.com/run-collection/14168007-2dc047db-9556-442a-b643-e913027a74cf)

## Integrations

Shopify · Zapier · Dutchie · GigSmart · Zendrive · Onfleet Connect (150+ courier partners)

## Common Resources

- [Portal](https://onfleet.com)
- [Documentation](https://docs.onfleet.com/)
- [API Reference (v2.7)](https://docs.onfleet.com/reference/introduction)
- [Quickstart](https://docs.onfleet.com/reference/setup-tutorial)
- [Data Types and Response Formats](https://docs.onfleet.com/reference/data-types-and-response-formats)
- [Querying by Metadata](https://docs.onfleet.com/reference/querying-by-metadata)
- [Changelog — May 2026](https://docs.onfleet.com/changelog/api-documentation-updates-may-2026)
- [Status Page](https://status.onfleet.com)
- [Pricing](https://onfleet.com/pricing)
- [Sign Up](https://onfleet.com/signup)
- [Support](https://onfleet.com/support)
- [Blog](https://onfleet.com/blog)
- [Terms of Service](https://onfleet.com/legal)
- [Privacy Policy](https://onfleet.com/privacy)
- [GitHub Organization](https://github.com/onfleet)
- [Plans (machine-readable)](plans/onfleet-plans-pricing.yml)
- [Rate Limits (machine-readable)](rate-limits/onfleet-rate-limits.yml)
- [FinOps (machine-readable)](finops/onfleet-finops.yml)
- [JSON-LD Context](json-ld/onfleet-context.jsonld)
- [Vocabulary](vocabulary/onfleet-vocabulary.yml)
- [Spectral Rules](rules/onfleet-rules.yml)

## Maintainers

- Kin Lane — [@apievangelist](https://x.com/apievangelist) — info@apievangelist.com
