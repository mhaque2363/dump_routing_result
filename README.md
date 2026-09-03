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

## Latest snapshot (2026-09-03T22:01:06Z)

- ProcessId: `c5f732ed-de4c-4aa2-96ac-696f90c60a1c`
- Assigned: 58 orders
- Unassigned (fabric not available): 33
- Assignment failures: 33
- Skipped: 0
- Order items: 268 (Aoshi 74 / Jyy 37)
