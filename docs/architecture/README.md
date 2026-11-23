# Deployment Map convention

Every deployable app or service repository owns exactly one \`docs/architecture/DEPLOYMENT-MAP.md\` using [the template](DEPLOYMENT-MAP.template.md).

**What this solves:** a new engineer can answer where an app runs, what belongs to which provider/account/project, which version is live, how to deploy/rollback, where data persists, where auth is enforced, who operates it, and how to recover it. A clear **NOT DEPLOYED** is better than a made-up hostname.

**No alternative source of truth:** this map indexes architecture evidence in code and live providers; it never replaces detailed operator runbooks, database contracts or migration histories. GitHub documents the intended/current topology, provider APIs document live state, and the established issue tracker owns work/approvals.

**Adoption:** start with active products and verified workloads, not every content/sandbox repository. Place rollout PRs on existing repositories; use docs-only Draft PRs and leave default branches untouched until authorized. Do not place an internal catalog in an organization's public profile repository. If an index is needed, use an existing authorized *private* engineering tracker containing links only—no second copy of provider metadata.

**Review checklist:** branch / PR identity; exact provider account/team and stable IDs; readback timestamp; production vs staging; verified/authored vs planned; entrypoints and dependencies; data/backup/restore; CI/deploy/rollback; IAM and secret references only; owner and next check. Report stale or inaccessible provider records as UNVERIFIED. Every new infrastructure change must update the map in the same PR.

**Sensitive data:** never add password values, key contents, auth headers, private URLs carrying tokens, full environment exports, user/customer/supplier data, internal IP topology that is not operationally necessary, or logs with possible secrets. A public template contains *no private application inventory*.
