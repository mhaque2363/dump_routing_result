# dump_routing_result

Daily snapshots of the production **order-routing dry-run** for factories Aoshi (`FACT-B2107`) and Jyy (`FACT-6F82A`).

The automation calls `GET /api/v1/routeorders-dry-run` with `sendNotification=false` and stores the JSON so results are not lost between runs.

## Stored files

| File | Purpose |
| --- | --- |
| `results/latest.json` | Most recent full dry-run payload |
| `results/latest.summary.json` | Counts and `OrderRoutingSummary` for the latest run |
| `results/routeorders-dry-run-<UTC timestamp>.json` | Timestamped full payload |

The Function host key is never written to this repository.

## Latest snapshot

- Fetched at: `2026-09-17T21:45:57Z`
- ProcessId: `1b1a5e17-589a-47e6-989a-7ca038f66eaa`
- Assigned orders: 184
- Unassigned (fabric not available): 61
- Assignment failures: 63
- Skipped: 0
