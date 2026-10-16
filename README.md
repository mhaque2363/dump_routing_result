# dump_routing_result

Nightly archive of the production order-routing dry-run for factories **Aoshi** (`FACT-B2107`) and **Jyy** (`FACT-6F82A`).

The snapshot is fetched from `/api/v1/routeorders-dry-run` with `sendNotification=false` so the run records assignments without sending notifications. Results are stored as JSON in this repository so they are not lost between runs.

## Files

| Path | Contents |
| --- | --- |
| `results/latest.json` | Full pretty-printed dry-run payload from the most recent fetch |
| `results/latest.summary.json` | Counts plus `OrderRoutingSummary` for the latest fetch |
| `results/routeorders-dry-run-<UTC timestamp>.json` | Dated copy of the full payload |

The Azure Function key is never committed. Callers supply it at fetch time.

## Payload shape

Top-level fields in `latest.json`:

- `ProcessId`
- `AssignedOrders`
- `UnassignedOrdersDueToFabricNotAvailable`
- `FabricMoveRequirements`
- `OrderRoutingSummary`
- `OrderAssignmentFailures`
- `SkippedOrders`

`OrderRoutingSummary` rows break item counts down by Aoshi, Jyy, unassigned (fabric), unassigned (data/dev), and skipped.
