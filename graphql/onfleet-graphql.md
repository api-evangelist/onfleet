# Onfleet GraphQL Schema

Conceptual GraphQL schema for the [Onfleet](https://onfleet.com) last-mile delivery management platform. Derived from the [Onfleet REST API v2.7](https://docs.onfleet.com/reference/introduction).

## Overview

Onfleet provides an AI-powered last-mile delivery management platform that orchestrates fleet operations, dispatch, route optimization, and customer experience across internal and outsourced delivery fleets. The platform powers 400M+ deliveries for brands across grocery, pharmacy, cannabis, furniture, and prepared meals sectors.

This GraphQL schema provides a conceptual representation of Onfleet's core domain model and operations, covering all major resource types available through the REST API.

## Schema File

- [`onfleet-schema.graphql`](onfleet-schema.graphql) — Full GraphQL schema with 60+ named types, queries, and mutations.

## Domain Model

### Core Delivery Resources

| Type | Description |
|------|-------------|
| `Task` | Atomic unit of work — a single pickup or dropoff stop with destination, recipients, state lifecycle, and proof-of-delivery data |
| `TaskDetails` | Extended task fields including barcode requirements, signature, photo, ETA, and geofence |
| `TaskState` | State enum: UNASSIGNED → ASSIGNED → ACTIVE → COMPLETED / FAILED |
| `TaskCompletionDetails` | Proof of delivery captured at completion — notes, photo, signature, timestamps |
| `TaskFailure` | Failure reason and notes when a task cannot be completed |
| `TimeoutTask` | Record of a task that timed out during execution |
| `TaskRecipient` | Link between task and its recipient(s) |
| `TaskDestination` | Link between task and its destination |
| `TaskEta` | Real-time ETA in seconds and meters to the task |
| `TaskBarcodes` | Required and captured barcode scans for the task |
| `TaskSignature` | Recipient signature captured at delivery |
| `TaskPhoto` | Photo evidence captured at delivery |
| `TaskNotes` | Free-text notes attached to a task |
| `TaskGeoFence` | Geofence radius or polygon around the task destination |
| `TaskContainer` | The worker, team, or organization currently holding the task |
| `TaskOverrides` | Per-task overrides for recipient SMS and proxy settings |
| `TaskIdentity` | ID verification scan data |
| `TaskAppearance` | Visual pin color override for the driver app |

### Workers & Shifts

| Type | Description |
|------|-------------|
| `Worker` | A driver with phone, vehicle, teams, duty status, and location |
| `WorkerDetails` | Extended worker fields including capacity, additional capacities, and metadata |
| `WorkerVehicle` | Vehicle assigned to a worker (CAR / MOTORCYCLE / BICYCLE / TRUCK) |
| `WorkerCapacity` | Weight/volume capacity tracking for the worker's vehicle |
| `WorkerLocation` | Current GPS coordinates, bearing, speed, and accuracy |
| `WorkerEta` | Worker ETA to their next assigned task |
| `WorkerStatus` | On/off-duty flag with active task reference |
| `WorkerAnalytics` | Aggregated delivery performance stats for a worker |
| `Shift` | A single on-duty period for a worker |
| `ShiftDetails` | Distance traveled, task count, and duration for a shift |
| `ShiftStart` | Timestamp and location when a shift began |
| `ShiftEnd` | Timestamp and location when a shift ended |

### Teams & Hubs

| Type | Description |
|------|-------------|
| `Team` | Named group of workers managed by one or more administrators |
| `TeamDetails` | Hub reference, task completion strategy, and worker ETA mode |
| `Hub` | Physical staging area or depot associated with a team |
| `HubDetails` | Geocoded location and address for a hub |
| `HubLocation` | GeoJSON coordinates for a hub |

### Destinations & Recipients

| Type | Description |
|------|-------------|
| `Destination` | Geocoded physical address used as a task pickup or dropoff point |
| `DestinationAddress` | Parsed address fields: number, street, city, state, postal code, country |
| `DestinationGeo` | Geocoding result with coordinates and wasGeocoded flag |
| `DestinationNotes` | Free-text notes and last-updated timestamp for a destination |
| `Recipient` | End customer who receives a delivery, with SMS preferences |
| `RecipientDetails` | Extended recipient fields including name parts, email, and metadata |
| `RecipientName` | First, last, and display name components |
| `RecipientPhone` | E.164 phone number and optional extension |
| `RecipientEmail` | Email address with confirmation flag |
| `RecipientNotes` | SMS skip flag and free-text notes |

### Route Planning & Optimization

| Type | Description |
|------|-------------|
| `RoutePlan` | Ordered sequence of tasks assigned to a worker for a time window |
| `RouteTask` | A single task entry in a route with position and ETA |
| `Route` | Fully computed route with total distance and time |
| `RouteOptimization` | Async optimization job status and result metadata |
| `Trip` | Recorded path driven during task execution |
| `TripDetails` | Polyline and waypoints for a trip |
| `TripSummary` | Distance, duration, start, and end time for a trip |

### Organization & Access

| Type | Description |
|------|-------------|
| `Organization` | An Onfleet account with timezone, country, and delegatee references |
| `Administrator` | Admin user with role (SUPER/STANDARD) and read-only flag |
| `APIKey` | REST API key with scoped permissions |
| `Token` | Short-lived auth token |

### Orders (Onfleet Connect)

| Type | Description |
|------|-------------|
| `Order` | Pickup-dropoff task pair on the Onfleet Connect courier network |

### Tracking

| Type | Description |
|------|-------------|
| `Tracking` | Customer-facing tracking page data with live worker location |
| `TrackingURL` | Branded tracking link with expiry |
| `TrackingTask` | Task state and ETA surfaced on the tracking page |

### Webhooks & Events

| Type | Description |
|------|-------------|
| `Webhook` | Registered HTTPS callback endpoint for 27 event trigger types |
| `WebhookEvent` | Delivered event payload with trigger type, timestamps, and resource data |
| `WebhookEventData` | Polymorphic data container (task, worker, order, jobId) |

### Supporting Types

| Type | Description |
|------|-------------|
| `Metadata` | Key-value metadata entry for extensible resource tagging |
| `CustomField` | Custom task field defined at the organization level |
| `BatchCreateResult` | Result of async batch task creation (up to 100 tasks) |
| `AutoDispatchResult` | Result of Team Auto-Dispatch trigger |

## Key Enums

| Enum | Values |
|------|--------|
| `TaskState` | UNASSIGNED, ASSIGNED, ACTIVE, COMPLETED, FAILED |
| `VehicleType` | CAR, MOTORCYCLE, BICYCLE, TRUCK |
| `WorkerStatus` | ON_DUTY, OFF_DUTY |
| `WebhookTrigger` | 27 trigger types covering full task lifecycle, worker duty/CRUD, route plan state, SMS events, and async job completions |
| `OptimizationMode` | TASK_BASED, VEHICLE_BASED, AUTO_DISPATCH |
| `OrderStatus` | PENDING, ACCEPTED, REJECTED, ACTIVE, COMPLETED, CANCELLED |
| `AdministratorRole` | SUPER, STANDARD |

## Queries

The schema exposes queries for all major resource types:

- `organization` / `delegateeOrganizations` — Fetch your org and connected courier orgs
- `worker` / `workers` / `workerByLocation` — Retrieve drivers with optional team/status filters
- `workerAnalytics` / `workerEta` — Performance data and ETA to next task
- `team` / `teams` / `hub` / `hubs` — Team and staging area management
- `task` / `tasks` / `tasksByMetadata` — Tasks with state, time range, and metadata filters
- `destination` / `recipient` / `recipientByName` / `recipientByPhone` — Address and customer lookups
- `routePlan` / `routePlans` — Route plan retrieval
- `tracking` — Customer tracking page data
- `order` / `orders` — Onfleet Connect order management
- `webhook` / `webhooks` / `webhookSecret` — Webhook configuration
- `apiKey` / `apiKeys` — API key management

## Mutations

Full create/update/delete mutations for all resources plus:

- `createTasks` — Batch create up to 100 tasks asynchronously
- `cloneTask` / `forceCompleteTask` / `assignTask` — Task lifecycle operations
- `autoDispatchTeam` — Trigger Team Auto-Dispatch (Beta)
- `optimizeRoutes` — Start async route optimization job (Enterprise)
- `cancelOrder` / `cloneOrder` — Onfleet Connect order management

## Authentication

The REST API uses HTTP Basic Auth with the API key as the username and an empty password. In a GraphQL implementation this would map to Bearer token or API key header authentication.

## References

- [Onfleet API Reference v2.7](https://docs.onfleet.com/reference/introduction)
- [Data Types and Response Formats](https://docs.onfleet.com/reference/data-types-and-response-formats)
- [Webhooks Reference](https://docs.onfleet.com/reference/webhooks)
- [GitHub Organization](https://github.com/onfleet)
- [Onfleet Developer Portal](https://onfleet.com)
