# dump_routing_result

Daily snapshots of the production order-routing dry-run for factories **FACT-B2107** (Aoshi) and **FACT-6F82A** (Jyy).

The DumpRouting automation calls `GET /api/v1/routeorders-dry-run` with `sendNotification=false` and writes the JSON response into this repository so the assignment result is not lost when the cloud agent VM is recycled.

## What is stored

Each successful run writes three files under `results/`:

| File | Purpose |
| --- | --- |
| `results/routeorders-dry-run-<UTC timestamp>.json` | Full dry-run payload for that fetch |
| `results/latest.json` | Same payload, always overwritten to the newest run |
| `results/latest.summary.json` | Counts and `OrderRoutingSummary` only (no function key) |

The function authorization `code` is used only to call the API. It is never written to git.

## Latest snapshot

See `results/latest.summary.json` for process id, fetch time, assigned/unassigned/failure counts, and the factory routing summary.
