# Onfleet

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
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Onfleet is an AI-powered last-mile delivery management platform that orchestrates fleet operations,
dispatch, route optimization, and customer experience across internal and outsourced delivery fleets.
The platform powers 400M+ deliveries for brands including Eaze, Total Wine & More, Pizza Hut, Kroger,
and Urbanstems across industries from prepared meals and grocery to cannabis, pharmacy, and
furniture. Onfleet exposes a comprehensive REST API v2.7 for tasks, workers, route plans, route
optimization, orders, recipients, destinations, organizations/teams, and webhooks — backed by
official SDKs in Python, Node.js, PHP, Java, and Go, plus the 150+ courier Onfleet Connect network.

**Areas:** Last Mile Delivery · Logistics · Fleet Management · Dispatch · Route Optimization · Couriers · Drivers · Tracking · Geocoding · Webhook · Artificial Intelligence · Software-as-a-Service

## Onfleet on APIs.io

Everything profiled for Onfleet is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/onfleet/](https://apis.io/providers/onfleet/)** — or go straight to one of the APIs or properties below.

### APIs (9)

- [Onfleet Tasks API](https://apis.io/apis/onfleet/onfleet-tasks-api/) — Create, list, fetch, update, clone, force-complete, and delete pickup/dropoff tasks. Tasks are the atomic unit of work in Onfleet — each has a destination,…
- [Onfleet Workers API](https://apis.io/apis/onfleet/onfleet-workers-api/) — Manage drivers — create, list, update, delete, fetch a worker's assigned tasks, and pull a delivery manifest for compliance reporting. Workers are bound to…
- [Onfleet Route Plans API](https://apis.io/apis/onfleet/onfleet-route-plans-api/) — Create and manage route plans — ordered sequences of tasks assigned to a worker for a time window — and kick off asynchronous route optimization jobs…
- [Onfleet Orders API](https://apis.io/apis/onfleet/onfleet-orders-api/) — Orders represent a pickup-dropoff task pair shared between a courier organization and its clients on the Onfleet Connect network. Clients can quote, create,…
- [Onfleet Organizations & Teams API](https://apis.io/apis/onfleet/onfleet-organizations-api/) — Look up your own organization and connected delegatee organizations on Onfleet Connect, manage administrators (Super and Standard, optionally read-only),…
- [Onfleet Recipients API](https://apis.io/apis/onfleet/onfleet-recipients-api/) — Create and look up end customers (recipients) by ID, name, or E.164 phone number. Recipients carry SMS notification preferences and metadata, and can be…
- [Onfleet Destinations API](https://apis.io/apis/onfleet/onfleet-destinations-api/) — Manage geocoded physical addresses used as task pickup/dropoff locations. Accepts a parsed address structure or a single `unparsed` field; coordinates are…
- [Onfleet Webhooks API](https://apis.io/apis/onfleet/onfleet-webhooks-api/) — Register HTTPS callbacks against 27 trigger types covering task lifecycle, worker duty/CRUD, route plan state changes, SMS recipient events, and async job…
- [Onfleet Route Optimization API](https://apis.io/apis/onfleet/onfleet-route-optimization-api/) — The Route Optimization API from Onfleet — 5 operation(s) for route optimization.

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### Arazzo workflows (13)

Multi-step workflows that chain operations into a business task.

- [Onfleet Assign Task to Worker](https://apis.io/arazzos/onfleet/onfleet-assign-task-to-worker-workflow/)
- [Onfleet Auto-Assign Task](https://apis.io/arazzos/onfleet/onfleet-auto-assign-task-workflow/)
- [Onfleet Batch Create and List Tasks](https://apis.io/arazzos/onfleet/onfleet-batch-create-and-list-tasks-workflow/)
- [Onfleet Build Route Plan](https://apis.io/arazzos/onfleet/onfleet-build-route-plan-workflow/)
- [Onfleet Clone and Force-Complete Task](https://apis.io/arazzos/onfleet/onfleet-clone-and-complete-task-workflow/)
- [Onfleet Dispatch Team Tasks](https://apis.io/arazzos/onfleet/onfleet-dispatch-team-tasks-workflow/)
- [Onfleet Fulfill Courier Order](https://apis.io/arazzos/onfleet/onfleet-fulfill-courier-order-workflow/)
- [Onfleet Onboard Worker to Team](https://apis.io/arazzos/onfleet/onfleet-onboard-worker-to-team-workflow/)
- [Onfleet Optimize Team Routes](https://apis.io/arazzos/onfleet/onfleet-optimize-team-routes-workflow/)
- [Onfleet Provision Administrator and Team](https://apis.io/arazzos/onfleet/onfleet-provision-admin-and-team-workflow/)
- [Onfleet Provision Delivery Task](https://apis.io/arazzos/onfleet/onfleet-provision-delivery-task-workflow/)
- [Onfleet Register Task Webhook](https://apis.io/arazzos/onfleet/onfleet-register-task-webhook-workflow/)
- [Onfleet Upsert Recipient and Create Task](https://apis.io/arazzos/onfleet/onfleet-upsert-recipient-and-create-task-workflow/)

#### AsyncAPI (1)

Event-driven and webhook contracts.

- [Onfleet Webhooks](https://apis.io/asyncapis/onfleet/onfleet-webhooks-asyncapi/)

#### Event channels (29)

Individual events and webhooks the provider emits.

- [auto_dispatch.completed](https://apis.io/channels/onfleet/auto-dispatch-completed/)
- [route_optimization.completed](https://apis.io/channels/onfleet/route-optimization-completed/)
- [route_plan.assigned](https://apis.io/channels/onfleet/route-plan-assigned/)
- [route_plan.completed](https://apis.io/channels/onfleet/route-plan-completed/)
- [route_plan.created](https://apis.io/channels/onfleet/route-plan-created/)
- [route_plan.delayed](https://apis.io/channels/onfleet/route-plan-delayed/)
- [route_plan.started](https://apis.io/channels/onfleet/route-plan-started/)
- [route_plan.unassigned](https://apis.io/channels/onfleet/route-plan-unassigned/)
- [route_plan.updated](https://apis.io/channels/onfleet/route-plan-updated/)
- [sms.recipient.opt_out](https://apis.io/channels/onfleet/sms-recipient-opt-out/)
- [sms.response.missed](https://apis.io/channels/onfleet/sms-response-missed/)
- [task.arrival](https://apis.io/channels/onfleet/task-arrival/)
- [task.assigned](https://apis.io/channels/onfleet/task-assigned/)
- [task_batch_create.completed](https://apis.io/channels/onfleet/task-batch-create-completed/)
- [task.cloned](https://apis.io/channels/onfleet/task-cloned/)
- [task.completed](https://apis.io/channels/onfleet/task-completed/)
- [task.created](https://apis.io/channels/onfleet/task-created/)
- [task.delayed](https://apis.io/channels/onfleet/task-delayed/)
- [task.deleted](https://apis.io/channels/onfleet/task-deleted/)
- [task.eta](https://apis.io/channels/onfleet/task-eta/)
- [task.failed](https://apis.io/channels/onfleet/task-failed/)
- [task.predicted.delay](https://apis.io/channels/onfleet/task-predicted-delay/)
- [task.started](https://apis.io/channels/onfleet/task-started/)
- [task.unassigned](https://apis.io/channels/onfleet/task-unassigned/)
- [task.updated](https://apis.io/channels/onfleet/task-updated/)
- …and 4 more published on APIs.io

#### GraphQL (1)

GraphQL schemas.

- [Moved to /providers/onfleet/](https://apis.io/graphqls/onfleet/onfleet-graphql/)

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [onfleet](https://apis.io/servers/onfleet/onfleet/)

#### Agentic access (1)

Which operations an agent can call, which act, and which need a human in the loop.

- [Onfleet Agentic Access](https://apis.io/agentic-access/onfleet/onfleet-agentic-access/)

#### JSON Schema (5)

The data models the API reads and writes.

- [OnfleetDestination](https://apis.io/schemas/onfleet/onfleet-destination/)
- [OnfleetRecipient](https://apis.io/schemas/onfleet/onfleet-recipient/)
- [OnfleetRoutePlan](https://apis.io/schemas/onfleet/onfleet-route-plan/)
- [OnfleetTask](https://apis.io/schemas/onfleet/onfleet-task/)
- [OnfleetWorker](https://apis.io/schemas/onfleet/onfleet-worker/)

#### JSON Structure (1)

Data models expressed in JSON Structure.

- [Onfleet Task Structure](https://apis.io/json-structure/onfleet/onfleet-task-structure/)

#### JSON-LD (1)

Linked-data contexts for the provider's vocabulary.

- [Onfleet Context](https://apis.io/jsonld/onfleet/onfleet-context/)

#### Vocabulary (1)

The provider's domain terms, defined.

- [Onfleet Vocabulary](https://apis.io/vocabularies/onfleet/onfleet-vocabulary/)

#### Examples (3)

Example requests and responses.

- [Onfleet Create Task Example](https://apis.io/examples/onfleet/onfleet-create-task-example/)
- [Onfleet Create Worker Example](https://apis.io/examples/onfleet/onfleet-create-worker-example/)
- [Onfleet Webhook Task Completed Example](https://apis.io/examples/onfleet/onfleet-webhook-task-completed-example/)

#### Collections (17)

Postman and Open Collection request collections.

- [Onfleet Destinations API](https://apis.io/collections/onfleet/open-onfleet-destinations-api/)
- [Onfleet Destinations Orders API](https://apis.io/collections/onfleet/open-onfleet-orders-api/)
- [Onfleet Destinations Organizations API](https://apis.io/collections/onfleet/open-onfleet-organizations-api/)
- [Onfleet Destinations Recipients API](https://apis.io/collections/onfleet/open-onfleet-recipients-api/)
- [Onfleet Destinations Route Optimization API](https://apis.io/collections/onfleet/open-onfleet-route-optimization-api/)
- [Onfleet Destinations Route Plans API](https://apis.io/collections/onfleet/open-onfleet-route-plans-api/)
- [Onfleet Destinations Tasks API](https://apis.io/collections/onfleet/open-onfleet-tasks-api/)
- [Onfleet Destinations Webhooks API](https://apis.io/collections/onfleet/open-onfleet-webhooks-api/)
- [Onfleet Destinations Workers API](https://apis.io/collections/onfleet/open-onfleet-workers-api/)
- [Onfleet Destinations API](https://apis.io/collections/onfleet/postman-onfleet-destinations-api/)
- [Onfleet Orders API](https://apis.io/collections/onfleet/postman-onfleet-orders-api/)
- [Onfleet Organizations API](https://apis.io/collections/onfleet/postman-onfleet-organizations-api/)
- [Onfleet Recipients API](https://apis.io/collections/onfleet/postman-onfleet-recipients-api/)
- [Onfleet Route Plans API](https://apis.io/collections/onfleet/postman-onfleet-route-plans-api/)
- [Onfleet Tasks API](https://apis.io/collections/onfleet/postman-onfleet-tasks-api/)
- [Onfleet Webhooks API](https://apis.io/collections/onfleet/postman-onfleet-webhooks-api/)
- [Onfleet Workers API](https://apis.io/collections/onfleet/postman-onfleet-workers-api/)

#### Governance rules (3)

Spectral rulesets for the provider's contracts.

- [Onfleet — asyncapi rules](https://apis.io/rules/onfleet/onfleet-asyncapi-spectral-rules/)
- [Onfleet — jsonschema rules](https://apis.io/rules/onfleet/onfleet-jsonschema-spectral-rules/)
- [Onfleet API Rules](https://apis.io/rules/onfleet/onfleet-rules/)

#### Security (4)

Authentication, trust centre, and vulnerability disclosure.

- [Onfleet Authentication](https://apis.io/security/onfleet/onfleet-authentication/)
- [Onfleet Domain Security](https://apis.io/security/onfleet/onfleet-domain-security/)
- [Onfleet Trust Center](https://apis.io/security/onfleet/onfleet-trust-center/)
- [Onfleet Vulnerability Disclosure](https://apis.io/security/onfleet/onfleet-vulnerability-disclosure/)

#### Plans and pricing (2)

Published plans, tiers and prices.

- [Onfleet Plans Pricing](https://apis.io/plans/onfleet/onfleet-plans-pricing/)
- [Onfleet Price Estimates](https://apis.io/plans/onfleet/onfleet-price-estimates/)

#### Rate limits (1)

Published request limits.

- [Onfleet Rate Limits](https://apis.io/rate-limits/onfleet/onfleet-rate-limits/)

#### FinOps (1)

What the API costs to run, by operation.

- [Onfleet Finops](https://apis.io/finops/onfleet/onfleet-finops/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://www.onfleet.com/)
- [Documentation](https://docs.onfleet.com/)
- [Getting started](https://docs.onfleet.com/reference/setup-tutorial)
- [Pricing](https://onfleet.com/pricing)
- [Support](https://onfleet.com/support)
- [Changelog](https://docs.onfleet.com/changelog/api-documentation-updates-may-2026)
- [Blog](https://onfleet.com/blog)
- [Terms of service](https://onfleet.com/legal)
- [Privacy policy](https://onfleet.com/privacy)
- [GitHub](https://github.com/onfleet)
- [Status](https://status.onfleet.com)

## API Evangelist rating

**Kin Score 60.5** — strong · rubric 0.25.0 · scored 2026-10-23

| Facet | Score |
|---|---|
| Discoverability | 73.3 |
| Contract quality | 70.4 |
| Contract governance | 27.3 |
| Operational transparency | 36.8 |
| Developer ergonomics | 57.1 |
| Access clarity | 73.7 |

**Agent readiness 46.3** — agent-ready (gated down from agent-native)

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | derived (partial credit) |
| Reversibility Documented | documented (partial credit) |
| MCP Server | verified |
| Auth Clarity | served (partial credit) |
| Idempotency | — |
| Error Semantics | — |
| OpenAPI Examples | documented (partial credit) |
| Rate Limit Signal | derived (partial credit) |
| Event Surface Described | derived (partial credit) |
| Agent Skills | — |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | served (partial credit) |
| Protected Resource Metadata | verified |
| Dynamic Client Registration | yes |
| Agentic Commerce | — |
| Pagination Ratio | — |
| Operation Distinctiveness | distinct |

**Regulatory alignment 29.1** — Horizontal (data, software, accessibility, platform)

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/onfleet/](https://apis.io/providers/onfleet/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for Onfleet: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/onfleet/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
