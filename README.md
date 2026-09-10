# dump_routing_result

This repository stores snapshots of the production order-routing dry-run for Suitsupply factories Aoshi (`FACT-B2107`) and Jyy (`FACT-6F82A`).

Each run calls `GET /api/v1/routeorders-dry-run` with `sendNotification=false` and writes the JSON response here so the assignment result is not lost when the Cloud Agent VM is recycled.

## Files

| File | Contents |
| --- | --- |
| `results/latest.json` | Full dry-run response from the most recent successful fetch |
| `results/latest.summary.json` | Counts and `OrderRoutingSummary` for the latest fetch |
| `results/routeorders-dry-run-<UTC timestamp>.json` | Timestamped copy of that full response |

The Function key used to call the API is never stored in this repository.

## Latest snapshot

See `results/latest.summary.json` for process id, fetch time, assigned/unassigned counts, and per-factory order-item totals.
