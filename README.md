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

- Fetched at (UTC): `2026-09-12T21:56:44Z`
- HTTP status: `200`
- Process id: `672a23cc-d29f-45e2-9404-e7f4095a22b3`
- Assigned orders: `296`
- Unassigned (fabric not available): `159`
- Assignment failures: `112`
- Fabric move requirements: `0`
- Skipped orders: `0`
