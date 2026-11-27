# HighErrorRate
**What it means:** more than 2% of lab14-app requests return 5xx for 1 minute (traffic above 0.5 req/s).
**Impact:** users get errors on /api/orders.
**Check:** 1) Grafana "lab14 — RED", panel "Errors — 5xx ratio". 2) Loki: `{service="lab14-app"} | json | status >= 500`, then search one request_id. 3) `docker compose ps`, `docker compose logs --tail=50 lab14-app`.
**Fix:** roll back the last change; in the practice: `curl -X POST "localhost:8000/chaos?error_rate=0"`.
**Escalate:** the app owner (Ruslanbek Tolametov) if it lasts 15 minutes after the rollback.
