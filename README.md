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

- Fetched at: `2026-10-06T21:45:49Z`
- HTTP status: `200`
- ProcessId: `65b1e85d-7ac6-4d35-8960-ccc2ab202b4c`
- Assigned orders: `211`
- Unassigned (fabric): `79`
- Assignment failures: `57`
- Skipped orders: `0`
- Order items: `673` (Aoshi `109` / Jyy `296`)
