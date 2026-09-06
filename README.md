# dump_routing_result

Archive of production **order-routing dry-run** results for Suitsupply factories Aoshi (`FACT-B2107`) and Jyy (`FACT-6F82A`).

A scheduled automation calls `GET /api/v1/routeorders-dry-run` on the production order-routing Azure Function with `sendNotification=false`, then writes the JSON payload into this repository so the snapshot is not lost when the agent VM is recycled.

## What is stored

Each successful run writes three files under `results/`:

| File | Contents |
| --- | --- |
| `routeorders-dry-run-<UTC timestamp>.json` | Full pretty-printed dry-run payload (assignments, fabric gaps, failures, routing summary) |
| `latest.json` | Same payload as the most recent dated file |
| `latest.summary.json` | Compact counts and `OrderRoutingSummary` for the latest run |

The Azure Function host key is never written to this repository.

## Factories

- `FACT-B2107` — Aoshi
- `FACT-6F82A` — Jyy
