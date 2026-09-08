# dump_routing_result

Daily snapshots of the production order-routing dry-run for factories **FACT-B2107** (Aoshi) and **FACT-6F82A** (Jyy).

The DumpRouting automation calls `GET /api/v1/routeorders-dry-run` with `sendNotification=false` and writes the JSON payload here so results are retained.

## Files

| Path | Purpose |
| --- | --- |
| `results/latest.json` | Most recent full dry-run response |
| `results/latest.summary.json` | Counts and `OrderRoutingSummary` for the latest run |
| `results/routeorders-dry-run-<UTC>.json` | Timestamped full response |

The Function host key is not stored in this repository.

## Latest snapshot (2026-09-08T21:45:47Z)

- ProcessId: `452fa112-3024-4995-92dc-f7e22ba4b780`
- Assigned orders: 181
- Unassigned (fabric not available): 96
- Assignment failures: 72
- Skipped: 0
- Order items: 720 (Aoshi 227 / Jyy 124)
