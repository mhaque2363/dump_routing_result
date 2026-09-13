# dump_routing_result

Daily snapshots of the production **order-routing dry-run** for factories Aoshi (`FACT-B2107`) and Jyy (`FACT-6F82A`).

The automation calls `GET /api/v1/routeorders-dry-run` with `sendNotification=false` and stores the JSON so results are not lost when the run environment is recycled.

## Files

| Path | Description |
| --- | --- |
| `results/latest.json` | Full dry-run payload from the most recent successful fetch |
| `results/latest.summary.json` | Counts and `OrderRoutingSummary` for the latest fetch |
| `results/routeorders-dry-run-<UTC timestamp>.json` | Timestamped copy of that same full payload |

The function authorization key is never written to this repository.

## Latest dump (2026-09-13)

- Fetched at: `2026-09-13T21:49:52Z`
- ProcessId: `def0c909-c929-4584-b1f3-9a72c0941e5f`
- Assigned orders: 237
- Unassigned (fabric not available): 115
- Assignment failures: 112
- Skipped: 0
- Order items: 912 (Aoshi 250 / Jyy 187)
