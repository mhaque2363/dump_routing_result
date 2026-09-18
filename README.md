# dump_routing_result

Stores snapshots of the production order-routing dry-run so daily assignment results are not lost.

The DumpRouting automation calls `GET /api/v1/routeorders-dry-run` for factories `FACT-B2107` (Aoshi) and `FACT-6F82A` (Jyy) with `sendNotification=false`, then writes the JSON response into this repository.

## Result files

Each successful run writes:

- `results/latest.json` — full dry-run payload from the most recent fetch
- `results/latest.summary.json` — counts and `OrderRoutingSummary` for that fetch
- `results/routeorders-dry-run-<UTC timestamp>.json` — timestamped copy of the same payload

The payload includes assigned orders, unassigned orders (fabric unavailable), assignment failures, skipped orders, and the routing summary. The Function host key is never stored in this repository.

## Latest snapshot

See `results/latest.summary.json` for process id, fetch time, HTTP status, and assignment counts.
