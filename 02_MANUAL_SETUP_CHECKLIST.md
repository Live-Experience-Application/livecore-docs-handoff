# Manual Setup Checklist

These tasks should be completed by you, not by an LLM.

## GitHub organization and repositories

- [ ] Confirm GitHub organization: `Live-Experience-Application`
- [ ] Create `livecore-docs-handoff`
- [ ] Create `livecore-platform`
- [ ] Create `livecore-deploy`
- [ ] Create `arcanos-app`
- [ ] Create `arcanos-mobile`
- [ ] Create `scenarioos-enterprise` as private or postpone until needed
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
.editorconfig
```

The handoff provides README, AGENTS, docs and CSV files. You add LICENSE, `.gitignore` and `.editorconfig` based on your final choices.

## Copy instructions

Use `08_REPO_COPY_UPDATE_INSTRUCTIONS.md` for exact copy steps.

Every folder under:

```text
repos/<repo-name>/
```

is intended to be copied into the root of the matching GitHub repository.

## Secrets and accounts

Prepare later, not before needed:

- [ ] GitHub Packages or another package registry
- [ ] Container registry
- [ ] Railway account/project
- [ ] optional: domain
- [ ] optional: object storage provider
- [ ] optional: error tracking provider
- [ ] Apple Developer account
- [ ] App Store Connect app record
- [ ] Google Play Console account
- [ ] Google Play app record
- [ ] Google Cloud Pub/Sub project for Google Play RTDN later
- [ ] Ad provider account only after ad policy and privacy requirements are clear

For local development, start with Docker Compose and self-hosted dependencies.

## Security decisions before coding

- [ ] OIDC-first authentication, not custom password auth
- [ ] Server-side authorization for every resource access
- [ ] signed asset URLs only after permission check
- [ ] no secret data sent to unauthorized clients
- [ ] WebSocket streams filtered server-side
- [ ] audit logs append-only
- [ ] all IDs treated as untrusted
- [ ] premium/entitlement state comes from server, never from client
- [ ] ad eligibility comes from server, while ad rendering stays in mobile

## License decisions before public release

- [ ] Decide AGPL or dual-license model for `livecore-platform`
- [ ] Decide whether ArcanOS Web is open source or owner-controlled
- [ ] Decide whether ArcanOS Mobile remains proprietary/owner-controlled due to app store distribution
- [ ] Decide whether ScenarioOS Enterprise remains private
- [ ] Decide contribution policy
- [ ] Review dependencies for license compatibility
- [ ] Get legal review before accepting external contributions

## Store compliance decisions before mobile release

- [ ] Decide final product naming: avoid implying official Dungeons & Dragons or Wizards endorsement
- [ ] Decide whether to market as "5e-compatible" / "tabletop RPG companion"
- [ ] Prepare privacy policy URL
- [ ] Prepare terms of service URL
- [ ] Prepare support URL
- [ ] Prepare test account for App Review / Play review
- [ ] Prepare Apple privacy details
- [ ] Prepare Google Play Data Safety section
- [ ] Prepare in-app purchase products
- [ ] Prepare ad SDK disclosure and consent flow

## Design artifact decision

The Claude Design HTML files are not implementation source. Use them as visual reference only for `arcanos-app` and `arcanos-mobile`.

Do not copy generated HTML directly into production code.
Do not place generated design HTML in `livecore-platform`.
