# Next.js Infrastructure

A containerized infrastructure stack for a Next.js application with monitoring, observability, and secrets management capabilities.

## Project Structure

```text
nextjs-infrastructure/
├── .env.example
├── docker-compose.yml
├── README.md
├── package.json
│
├── services/
│   └── nextjs/
│       ├── Dockerfile
│       ├── app/
│       ├── lib/
│       ├── public/
│       └── ...
│
├── config/
│   ├── monitoring/
│   │   └── prometheus.yml
│   ├── nextjs/
│   └── vault/
```

## Services & Ports

| Service       | Host Port | Container Port |
| ------------- | --------- | -------------- |
| Next.js       | 3000      | 3000           |
| Uptime Kuma   | 3001      | 3001           |
| Grafana       | 3002      | 3000           |
| Prometheus    | 9090      | 9090           |
| Vault         | 8200      | 8200           |
| Node Exporter | 9100      | 9100           |

## Getting Started

### Build Images

```bash
docker compose build --no-cache
```

### Start Services

```bash
docker compose up -d
```

### Stop Services

```bash
docker compose down
```

### Cleanup Docker Resources

```bash
docker system prune -a --volumes -f
```

## Monitoring

* Prometheus collects infrastructure and application metrics.
* Node Exporter provides host-level metrics.
* Grafana visualizes collected metrics through dashboards.
* Uptime Kuma monitors service availability and health checks.

## Metrics Endpoint

The Next.js application exposes Prometheus metrics through:

```text
/api/metrics
```

using the `prom-client` package.

## Infrastructure Management

All services are orchestrated using Docker Compose and communicate through a shared Docker network.
