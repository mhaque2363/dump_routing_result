# dump_routing_result

Archive of production order-routing dry-run snapshots for Aoshi (`FACT-B2107`) and Jyy (`FACT-6F82A`).

A scheduled automation calls `GET /api/v1/routeorders-dry-run` on the production Order Routing function with `sendNotification=false` and stores the JSON here so assignment results are not lost.

## Result files

| File | Purpose |
| --- | --- |
| `results/latest.json` | Full payload from the most recent successful fetch |
| `results/latest.summary.json` | Counts, process id, and `OrderRoutingSummary` for the latest fetch |
| `results/routeorders-dry-run-<UTC>.json` | Timestamped copy of that same full payload |

The Function host key is never written to this repository.
