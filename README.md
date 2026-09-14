# dump_routing_result

Archive of production order-routing dry-run snapshots for factories **Aoshi** (`FACT-B2107`) and **Jyy** (`FACT-6F82A`).

Each run calls `GET /api/v1/routeorders-dry-run` on the production order-routing Azure Function with `sendNotification=false` (no factory notifications) and writes the JSON response into this repository so the payload is not lost when the function host recycles.

## Stored files

| Path | Purpose |
| --- | --- |
| `results/routeorders-dry-run-<UTC timestamp>.json` | Immutable snapshot of one dry-run response |
| `results/latest.json` | Same payload as the most recent snapshot |
| `results/latest.summary.json` | Counts and `OrderRoutingSummary` for the latest run |

The Function host key is never written to git.

## Latest snapshot (2026-09-14T21:46:53Z)

- Process id: `0f0ee10c-f403-4d4f-b5a1-b79c03171a02`
- HTTP 200
- Assigned orders: 174
- Unassigned (fabric not available): 67
- Assignment failures: 63
- Skipped: 0
- Order items: 633 (Jyy 172 / Aoshi 159)
