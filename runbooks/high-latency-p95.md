# HighLatencyP95
**What it means:** p95 latency of lab14-app is above 0.5 s for 1 minute (ticket, no page).
**Check:** Grafana panel "p95 by route"; Loki `{service="lab14-app"} | json | duration_ms > 500`.
**Fix:** remove the cause; in the practice: `curl -X POST "localhost:8000/chaos?slow_ms=0"`.
