# dump_routing_result

Archive of production order-routing dry-run results for Suitsupply custom-made factories **Aoshi** (`FACT-B2107`) and **Jyy** (`FACT-6F82A`).

A scheduled Cursor automation calls the production `routeorders-dry-run` endpoint with `sendNotification=false` and writes the JSON payload into this repository so the snapshot is not lost when the agent VM is recycled.

## What is stored

Each successful fetch writes three files under `results/`:

| File | Purpose |
| --- | --- |
| `results/routeorders-dry-run-<UTC timestamp>.json` | Full pretty-printed dry-run payload for that run |
| `results/latest.json` | Same payload, always overwritten to the newest fetch |
| `results/latest.summary.json` | Counts and `OrderRoutingSummary` only (quick glance) |

The Azure Function host key is never written to this repository.

## Latest snapshot

- Fetched at: **2026-09-02T20:45:56Z**
- HTTP status: **200**
- Process id: `dacd9d79-3520-4907-8c98-f9bc1b2f2301`
- Assigned orders: **157**
- Unassigned (fabric not available): **104**
- Assignment failures: **71**
- Skipped: **0**
- Order items: **687** (Aoshi 198 / Jyy 89)

See `results/latest.summary.json` for the full routing breakdown.

## Endpoint (no secrets)

`GET /api/v1/routeorders-dry-run`

Query parameters used by the automation:

- `factoryCodes=FACT-B2107`
- `factoryCodes=FACT-6F82A`
- `sendNotification=false`

Host: `order-routing-prd-af.azurewebsites.net`
