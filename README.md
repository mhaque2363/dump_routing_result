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

- Fetched at: `2026-10-07T21:45:35Z`
- HTTP status: `200`
- ProcessId: `48db30da-c064-42bc-824c-3c521ee65648`
- Assigned orders: `242`
- Unassigned (fabric): `67`
- Assignment failures: `62`
- Skipped orders: `0`
- Order items: `909` (Aoshi `131` / Jyy `428`)
