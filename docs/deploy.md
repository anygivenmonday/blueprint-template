## Deploy

How to take this blueprint from a working local environment to a
live deployment. Only populate this file once a real deployment
flow is in place — for description-only or "local only" blueprints,
delete the file.

This section is rendered as the **Deploy** block on the
AnyGivenMonday detail page.

### Target environment

Where this blueprint expects to run in production. One paragraph:
provider, region recommendation, machine shape, the gist of what
sits in front (load balancer, CDN, none).

### Provisioning

The infrastructure-as-code or click-ops sequence needed before the
first deploy. Prefer IaC (Terraform, Pulumi, raw cloud CLI) over
"go to the dashboard and click...". If IaC, link to the files;
keep this section to the high-level shape.

```bash
cd infra/terraform
terraform init
terraform apply
```

### Secrets

The set of secrets the deployment expects. **Never** check them
into the repo. List the names + a sentence on how to obtain each:

- `PROVIDER_API_TOKEN` — generated in the provider's dashboard.
- `DATABASE_URL` — output by the IaC provisioning step.

### First deploy

```bash
# whatever your deploy script is — Makefile target, Github Action, etc.
./deploy.sh
```

### Ongoing deploys

How updates land:

- Automatic on push to `main` (when a workflow is wired up), or
- Manual via the same `./deploy.sh`, or
- Document the actual choice.

### Rollback

How to undo a bad deploy:

- The one-liner to roll back to the previous release.
- Where to find the deploy history.

### Observability

Where logs / metrics / errors land. One line each:

- Logs: ...
- Metrics: ...
- Errors / alerts: ...

---

This file is optional. If the blueprint has no deploy story yet,
leave the file out.
