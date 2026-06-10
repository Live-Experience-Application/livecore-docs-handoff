# Manual Setup Checklist

These tasks should be completed by you, not by an LLM.

## GitHub organization and repositories

- [ ] Create GitHub organization or decide personal namespace
- [ ] Create `livecore-docs-handoff`
- [ ] Create `livecore-platform`
- [ ] Create `livecore-deploy`
- [ ] Create `arcanos-app`
- [ ] Create `scenarioos-enterprise` as private or postpone
- [ ] Add repository descriptions
- [ ] Add branch protection
- [ ] Add default labels
- [ ] Add CODEOWNERS later when team grows

## Repository root files to add manually

Each repository should have at least:

```text
README.md
AGENTS.md
docs/
csv/
LICENSE
.gitignore
```

The handoff provides README, AGENTS, docs and CSV files. You add LICENSE and `.gitignore` based on your final choices.

## Secrets and accounts

Prepare later, not before needed:

- [ ] GitHub Packages or another package registry
- [ ] Container registry
- [ ] Railway account/project
- [ ] optional: domain
- [ ] optional: object storage provider
- [ ] optional: error tracking provider

For local development, start with Docker Compose and self-hosted dependencies.

## Security decisions before coding

- [ ] OIDC-first authentication, not custom password auth
- [ ] Server-side authorization for every resource access
- [ ] signed asset URLs only after permission check
- [ ] no secret data sent to unauthorized clients
- [ ] WebSocket streams filtered server-side
- [ ] audit logs append-only
- [ ] all IDs treated as untrusted

## License decisions before public release

- [ ] Decide AGPL or dual-license model
- [ ] Decide whether enterprise vertical remains private
- [ ] Decide contribution policy
- [ ] Review dependencies for license compatibility
- [ ] Get legal review before accepting external contributions

## Design artifact decision

The Claude Design HTML files are not implementation source. Use them as visual reference only for `arcanos-app`.

Do not copy generated HTML directly into production code.
