# dump_routing_result

Archive of production **order-routing dry-run** results from the Suitsupply Order Routing Azure Function.

Each run calls `GET /api/v1/routeorders-dry-run` for factories **FACT-B2107** (Aoshi) and **FACT-6F82A** (Jyy) with `sendNotification=false`, then stores the JSON so the payload is not lost when an ephemeral agent workspace is wiped.

## Result files

| Path | Purpose |
| --- | --- |
| `results/latest.json` | Full dry-run payload from the most recent successful fetch |
| `results/latest.summary.json` | Counts, process id, fetch timestamp, and `OrderRoutingSummary` |
| `results/routeorders-dry-run-<UTC>.json` | Timestamped copy of that same full payload |

The function access key is never written to this repository.

## Latest dump

- Fetched at (UTC): `2026-09-02T17:40:29Z`
- HTTP status: `200`
- Process id: `a82f25ad-e2aa-4f83-b13f-796a81267fe4`
- Assigned orders: `127`
- Unassigned (fabric not available): `81`
- Assignment failures: `58`
- Fabric move requirements: `0`
- Skipped orders: `0`
