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

- Fetched at (UTC): `2026-09-11T21:55:10Z`
- HTTP status: `200`
- Process id: `d76be808-ca2b-4816-9999-913b61a3b4ec`
- Assigned orders: `228`
- Unassigned (fabric not available): `104`
- Assignment failures: `74`
- Fabric move requirements: `0`
- Skipped orders: `0`
- Order items: `826` (Aoshi `234` / Jyy `213`)
