# AppDown
**What it means:** Prometheus cannot scrape lab14-app (`up == 0`) or there is no target, for 30 s.
**Impact:** the service is unavailable; HighErrorRate and HighLatencyP95 are inhibited.
**Check:** 1) Prometheus → Status → Target health. 2) `docker compose ps lab14-app`. 3) `docker compose logs --tail=50 lab14-app`. 4) `curl -s localhost:8000/healthz`.
**Fix:** `docker compose start lab14-app`; if it crashes again, roll back the image.
**Escalate:** the app owner (Ruslanbek Tolametov) right away — this alert pages.
