# `<Application name>` — Deployment Map

**Document owner:** `<team / named operator or UNASSIGNED>`  
**Evidence checked:** `<YYYY-MM-DD, timezone; separate source, control-plane and runtime checks>`  
**Application lifecycle:** PROTOTYPE | STAGING | PRODUCTION | DECOMMISSIONED  
**Document status:** DRAFT | APPROVED  
**Canonical code:** `<owner/repo, default branch, links>`

> This is the app's **one canonical documented resource map**. The provider APIs and their readback remain authoritative for **live** runtime state. Never claim that source configuration or a successful build alone proves deployment. Never put secrets, passwords, bearer tokens, recovery codes or sensitive runtime payloads here.

## 30-second answer

`<Where users access the app; provider/account/project/region, backend, data storage, edge, auth, deploy pipeline. If not deployed, say NOT DEPLOYED. Every statement must have a source or be marked unverified.>`

## Pieces and ownership

| Layer / job | Provider + account/team | Exact resource name and stable ID | Environment | Verified status + time | Evidence / operator |
| --- | --- | --- | --- | --- | --- |
| Code | GitHub | `<repo, branch>` | all | VERIFIED / UNVERIFIED | `<PR/source>` |
| Frontend | `<provider>` | `<project ID / hostname>` | prod / staging | `<status>` | `<dashboard readback>` |
| API / workers | `<provider>` | `<service ID / region>` | … | … | … |
| Database | `<provider>` | `<project/database reference, no credentials>` | … | … | … |
| Storage / backups | `<provider>` | `<bucket/volume and policy>` | … | … | … |
| DNS, CDN, Access | `<provider>` | `<zone / route / app ID>` | … | … | … |
| MCP / agents | `<provider>` | `<service / endpoint / scope>` | … | … | … |
| CI, monitoring, alerts | `<provider>` | `<workflow / monitor ID>` | … | … | … |

**Not deployed or not verified:** `<explicit gaps>`. State production and nonproduction separately; a protected prototype is still a hosted deployment. A planned service is not an existing resource. Distinguish service account names from operational users; names alone do not prove authorization.

## Connections and trust boundaries

`<Add a compact Mermaid diagram only when it clarifies branching, dependencies or trust boundaries; otherwise use a dependency table. Label each edge with its evidence status. A diagram is not deployment evidence.>`

For each connection describe **the actual trust boundary** and which party owns authorization, source-of-truth data and writes. Distinguish authorized identity assertion from browser-provided identity. Record unverified edges as dotted/labelled.

## Environment matrix

| Environment | URL / target | Git branch/ref | Provider resource | Data source / writer | Auth model | Status |
| --- | --- | --- | --- | --- | --- | --- |
| local | `<loopback only>` | dev | developer machine | test only | local | … |
| staging | `<URL or NOT PROVISIONED>` | … | … | … | … | … |
| production | `<URL or NOT DEPLOYED>` | … | … | … | … | … |

## Deployment and rollback

- CI entrypoint and **exact gates**: `<workflow links / required checks>`.
- Trigger: `<push, branch creation, PR, manual approval, tag>`. Record GitHub Actions and native provider Git integration separately, including branch/path filters. **Do not guess auto-deploy or assume Draft/docs-only changes are exempt.**
- Documentation publication: `<verified no-deployment path, provider-supported skip mechanism, or BLOCKED pending a specific authorization>`. Do not change provider settings or bypass required gates merely to publish a map.
- Deployment identity: `<service, branch, image/revision, immutable evidence>`.
- Operator-run rollback and health verification: `<linked runbook>` — or NOT DOCUMENTED.
- Migration ordering and changes requiring human approval: `<runbook>`.
- Production modifications are NEVER authorized by this documentation alone.

## Data durability, security and cost

- **Writer of record / database and service schema:** `<owner and links>`.
- **Persistent volume / bucket / RPO/RTO / tested restore:** `<verified values or UNVERIFIED>`.
- **Secret manager and names of env vars only:** `<no values; avoid personal secrets>`. Access owner and rotation runbook: `<reference or UNVERIFIED>`.
- **DNS owner / SSO / IAM / MCP permissions:** `<provider readback or UNVERIFIED>`.
- **Monitoring, alerts, response owner and incident runbook:** `<links or UNVERIFIED>`.
- **Costs:** `<verified bill/project/timestamp, or NOT VERIFIED>`. Do not extrapolate from list prices as measured actuals.

## Outstanding decisions and drift

| Finding | Severity | Exact verification gap / observed inconsistency | Owner + existing issue |
| --- | --- | --- | --- |
| `<item>` | High / Medium / Low | `<evidence>` | `<Linear issue / no owner assigned>` |

## Evidence and linked documents

- Source and deployment configs: `<repo files pinned to the inspected branch and commit SHA>`. State when the default branch differs from the deployed branch; do not attribute one branch's workflow to another.
- Service/control-plane readback: `<provider dash/CLI and exact timestamp>`.
- Current operational runbook: `<link>`. **This map indexes existing detailed runbooks, it does not rewrite them.**
- Release and work tracker: `<Linear project and issues>`.

## Update invariant

Every GitHub PR that changes hosting, DNS, CI/CD deployment triggers, runtime, storage, database, edge routing, secret-manager references, access controls, monitoring or ownership **must update this file in the same PR**, or explicitly explain why topology is unchanged. A separate live-provider readback is needed after deployment before moving PLANNED → VERIFIED. The review must check consistency with the deployment manifests and real applications. Link an existing work-tracking item; do not create a duplicate inventory in Linear. Preserve historical architecture decisions in their existing ADR/runbook, not here.

Statuses must be explicit: **VERIFIED** (readback + date), **SOURCE-REPORTED** (repo/config only), **UNVERIFIED**, **PLANNED**, **BLOCKED**, **RETIRED**. Do not call an unreachable resource “offline” without observing its runtime.
