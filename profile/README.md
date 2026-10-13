# dooservice

**Every Odoo you run, in one panel. On servers that stay yours.**

dooservice is a control panel for Odoo 16.0 to 20.0. Connect a server (a VPS, a machine
in your office, or one we create for you at Hetzner, DigitalOcean or Vultr) and run your
Odoo projects on it: environments, deployments from GitHub, backups, domains, logs and
alerts, from [dooservice.sh](https://dooservice.sh). Your databases never leave your
server unless you choose a remote backup.

## What it does

- **Environments in minutes**: production and development, each with its own database,
  configuration and domain. Clone production to test, from now or from any full backup.
- **Deploy from GitHub**: by push, submodules included; every deployment records its
  commit and author, with a way back.
- **Backups**: daily on your server, off it on a paid plan, plus a weekly immutable copy.
  Restore in one click; a restore test runs every week.
- **AI in the console**: Claude Code or opencode inside each environment, aware of its Odoo
  version. Code leaves as a pull request; on production the AI changes data only through
  Odoo and asks before each change.
- **Alerts**: server down, backup failed, disk full or production stopped, when it
  happens and when it clears.
- **A team with permissions**: owner, admin, developer or viewer, each in their own
  projects.
- **Updates without surprises**: signed releases, rolled out in stages, inside each
  server's maintenance window.

## Open source

| Repository | What it is | License |
|---|---|---|
| [docker-images](https://github.com/dooservice/docker-images) | The images every server runs: Odoo, the environment console, PostgreSQL | AGPL-3.0 |
| [odoo-skills](https://github.com/dooservice/odoo-skills) | Agent skills for Odoo 16.0 to 20.0: Odoo's own skills, adapted and checked per version | LGPL-3.0 |
| [gitd](https://github.com/dooservice/gitd) | Keeps the git repositories of a server: one copy per repository that every environment borrows from, over ConnectRPC | AGPL-3.0 |

Issues and pull requests are welcome in each repository; read its `CONTRIBUTING.md` first.

## Get started

Create an account at **[dooservice.sh](https://dooservice.sh)**, connect a server with one
command, and create your first project.

## Security and contact

Report vulnerabilities privately from the *Security* tab of the affected repository, or by
email to [soporte@apiservicesac.com](mailto:soporte@apiservicesac.com) with «Security» in
the subject. For anything else, write to the same address.

---

Made by **[API SERVICE SAC](https://apiservicesac.com)**, a software company in Peru that
builds on Odoo. Odoo is a trademark of Odoo S.A.; dooservice is not affiliated with or
endorsed by Odoo S.A.
