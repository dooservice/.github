# dooservice

**Managed Odoo infrastructure — from development to production.**

dooservice is an open-source platform for teams building on Odoo. It handles provisioning, environment management, deployments, backups, and scaling so engineers can focus on building, not on infrastructure.

Built and operated by **[API SERVICE SAC](https://apiservicesac.com)** — a software company based in Peru specializing in Odoo development and cloud infrastructure.

---

## What it does

dooservice treats every Odoo project as a first-class deployment target. Each project gets:

- A **production environment** with 2 Odoo workers, its own PostgreSQL database, and a dedicated domain
- Unlimited **development environments** — isolated, neutralized clones ready for testing and staging
- **One-click deployments** triggered manually or automatically from GitHub pull request merges
- **Backup and restore** — full database and filestore snapshots with point-in-time restore
- **Worker scaling** — adjust production compute resources without downtime
- **Custom domains** — bring your own domain with automatic SSL

All environments are provisioned in real time through an agent-based architecture that runs close to the data.

---

## Architecture

The platform is composed of four open-source components:

| Repository | Role |
|---|---|
| [`core`](https://github.com/dooservice/core) | Shared SDK, domain models, transport layer, and agent–orchestrator protocol |
| [`orchestrator`](https://github.com/dooservice/orchestrator) | Central API server — manages projects, users, jobs, and agent coordination |
| [`agent`](https://github.com/dooservice/agent) | Daemon deployed on tenant servers — executes provisioning, deployment, and backup jobs |
| [`app-dooservice`](https://github.com/dooservice/app-dooservice) | Web UI for managing projects and environments |

The orchestrator and agents communicate over [NATS](https://nats.io) using an encrypted, authenticated protocol. Jobs are dispatched asynchronously via JetStream and stream progress back to the dashboard in real time.

---

## Key integrations

- **GitHub** — link a repository to a project, enable auto-deploy on push, and create isolated environment branches per PR
- **Traefik** — automatic reverse proxy configuration and SSL for every environment
- **Cloudflare** — DNS record management for custom and primary domains

---

## Self-hosted

dooservice is fully open source. You can run the entire stack on your own infrastructure:

```
orchestrator  →  your VPS or cloud VM
agent(s)      →  one per region or tenant server
app-dooservice →  static hosting or your own server
```

Documentation and deployment guides are available at **[dooservice.sh](https://dooservice.sh)**.

---

## Hosted platform

Don't want to operate it yourself? **[dooservice.sh](https://dooservice.sh)** is the managed version — sign up, create a project, and have a live Odoo environment running in minutes. Operated by API SERVICE SAC.

---

## About API SERVICE SAC

**API SERVICE SAC** is a Peruvian software company focused on Odoo development, integrations, and cloud infrastructure. dooservice is our internal tooling for managing Odoo environments at scale, now open to the community.

- Website: [apiservicesac.com](https://apiservicesac.com)
- Email: soporte@apiservicesac.com
