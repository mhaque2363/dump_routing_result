# dump_routing_result

Storehouse for production **order-routing dry-run** snapshots.

Each run calls `GET /api/v1/routeorders-dry-run` on the production Order Routing Azure Function (`order-routing-prd-af`) for factories **FACT-B2107** (Aoshi) and **FACT-6F82A** (Jyy), with `sendNotification=false`. The JSON response is committed here so historical assignment results are not lost when the function host recycles.

## What's in `results/`

| File | Purpose |
| --- | --- |
| `latest.json` | Full dry-run payload from the most recent successful fetch |
| `latest.summary.json` | Counts and `OrderRoutingSummary` only (safe to skim) |
| `routeorders-dry-run-<UTC timestamp>.json` | Dated full payload, kept so older runs remain available |

The Function host key is never stored in this repository.

## Latest snapshot (2026-09-05T21:45:42Z)

- ProcessId: `bc1cf6b8-5d67-4deb-b0ad-990e8f7d9381`
- Assigned orders: 341
- Unassigned (fabric not available): 161
- Assignment failures: 139
- Skipped: 0
- Order items: 1360 (Aoshi 427 / Jyy 226)
