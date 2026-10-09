# dump_routing_result

Stores production order-routing dry-run snapshots so each nightly run can be compared later.

## What is captured

A GET against the production Order Routing Azure Function:

- Endpoint: `/api/v1/routeorders-dry-run`
- Factories: `FACT-B2107` (Aoshi), `FACT-6F82A` (Jyy)
- `sendNotification=false` so the dry-run does not notify factories

The function key is used only at request time and is never written into this repository.

## Result files

After a successful fetch, JSON is written under `results/`:

| File | Purpose |
| --- | --- |
| `results/latest.json` | Full dry-run payload from the most recent run |
| `results/latest.summary.json` | Counts and routing summary only |
| `results/routeorders-dry-run-<UTC timestamp>.json` | Dated copy of that same full payload |

## Payload shape

The dry-run body includes:

- `ProcessId`
- `AssignedOrders`
- `UnassignedOrdersDueToFabricNotAvailable`
- `FabricMoveRequirements`
- `OrderRoutingSummary`
- `OrderAssignmentFailures`
- `SkippedOrders`

## Latest snapshot

See `results/latest.summary.json` for the most recent counts without opening the full payload.

- Fetched at: `2026-10-09T21:46:06Z`
- HTTP status: `200`
- ProcessId: `276f5e5f-ba10-4b2c-9173-8bcbbad09bc7`
- Assigned orders: `227`
- Unassigned (fabric): `85`
- Assignment failures: `78`
- Skipped orders: `0`
- Order items: `772` (Aoshi `143` / Jyy `269`)
