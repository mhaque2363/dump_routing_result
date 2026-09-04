# dump_routing_result

Archive of production **order-routing dry-run** snapshots for factories Aoshi (`FACT-B2107`) and Jyy (`FACT-6F82A`).

A scheduled Cursor automation calls:

`GET /api/v1/routeorders-dry-run?factoryCodes=FACT-B2107&factoryCodes=FACT-6F82A&sendNotification=false`

on `order-routing-prd-af.azurewebsites.net` and writes the JSON response into this repository so the payload is not lost when the agent VM is recycled.

## Layout

| File | Purpose |
| --- | --- |
| `results/latest.json` | Most recent full dry-run response |
| `results/latest.summary.json` | Counts and `OrderRoutingSummary` for the latest run |
| `results/routeorders-dry-run-<UTC>.json` | Timestamped full snapshot |

The Function host key is never stored in git.

## Latest snapshot (2026-09-04T21:46:05Z)

- ProcessId: `24dc3d8a-339f-4fd3-93e1-417d6389c561`
- Assigned: 197 orders
- Unassigned (fabric not available): 135
- Assignment failures: 61
- Skipped: 0
- Order items: 808 (Aoshi 217 / Jyy 144)
