# dump_routing_result

Archive of production order-routing dry-run results.

Each scheduled run calls the order-routing dry-run API for factories **Aoshi** (`FACT-B2107`) and **Jyy** (`FACT-6F82A`) with notifications disabled, then stores the JSON so the assignment snapshot is not lost.

## Stored files

Results live under `results/`:

| File | Purpose |
| --- | --- |
| `routeorders-dry-run-<UTC timestamp>.json` | Full dry-run payload for that run |
| `latest.json` | Same payload as the most recent run |
| `latest.summary.json` | Counts, process id, and `OrderRoutingSummary` for the most recent run |

The payload includes assigned orders, orders unassigned because fabric is unavailable, assignment failures, skipped orders, and the factory routing summary.

## API

- Endpoint: `GET /api/v1/routeorders-dry-run`
- Host: `order-routing-prd-af.azurewebsites.net`
- Query: `factoryCodes=FACT-B2107`, `factoryCodes=FACT-6F82A`, `sendNotification=false`

The function key is supplied at request time and is never written into this repository.
