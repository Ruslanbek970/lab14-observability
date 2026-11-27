# lab14-observability
Practice 14 (Observability), Track B — Docker Compose.

Flask app with RED metrics and JSON logs; Prometheus (recording + alert rules), Alertmanager (webhook, inhibition), Grafana (provisioned data sources and dashboard as code), Loki + Alloy for logs.

## Run
    echo "GRAFANA_PASSWORD=$(openssl rand -hex 12)" > .env
    docker compose up -d --build

Prometheus :9090 · Alertmanager :9093 · Grafana :3000 (admin / password from .env)

## Layout
- `app/` — the app and Dockerfile
- `monitoring/` — Prometheus, rules, Alertmanager, Loki, Alloy, Grafana provisioning, webhook receiver
- `dashboards/lab14.json` — RED dashboard
- `runbooks/` — AppDown, HighErrorRate, HighLatencyP95
