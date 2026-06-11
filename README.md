# FINAL COMPLETE HANDOFF - Live Experience Core, ArcanOS Web, ArcanOS Mobile, ScenarioOS

This folder is the final pre-implementation handoff for the complete repository set.
It is designed to be copied into real GitHub repositories before any coding agent starts implementation.

This is not an MVP package. It is a production-oriented handoff for a self-hostable, maintainable, secure product family built from a reusable Core Platform.

## Product family

```text
Live Experience Core
  -> generic product-neutral platform for live sessions, scenes, participants, visibility, reveals, assets, audit, templates, entitlements, quotas and recaps

ArcanOS Web
  -> Pen-and-Paper / 5e-compatible / tabletop roleplaying web vertical built on Core
  -> best for desktop, laptop, tablet, preparation and full host control

ArcanOS Mobile
  -> native iOS/Android app for the ArcanOS vertical
  -> best for player/participant companion, session join, mobile reading, mobile ads, premium and store distribution

ScenarioOS
  -> Enterprise training, simulation and workshop vertical built on Core
  -> later phase, after Core and ArcanOS prove the vertical boundary

LiveCore Deploy
  -> deployment, Docker Compose, Kubernetes/Helm, Railway, backup/restore, operations and mobile store backend operations

LiveCore Docs Handoff
  -> governance, implementation process, LLM delivery rules and cross-repo coordination
```

## Repository order

Start in this order:

1. `livecore-docs-handoff`
2. `livecore-platform`
3. `livecore-deploy`
4. `arcanos-app`
5. `arcanos-mobile`
6. `scenarioos-enterprise` later, only after the Core boundary, authorization and audit foundations are stable

Do not start ArcanOS Web before the Core has stable contracts for Workspace, Session, Scene, Participant, ContentBlock, Entity, VisibilityRule, SessionEvent and Asset.

Do not start ArcanOS Mobile before the Core also has stable contracts for Auth, Entitlements, Quota Status and Ad Eligibility.

Do not start ScenarioOS before ArcanOS has validated that the Core can support a real vertical without leaking vertical language into Core.

## Repository packaging in this handoff

Each folder under `repos/` is intended to become the root of a separate GitHub repository. Copy the contents of each folder into the matching repository.

```text
repos/livecore-docs-handoff/
repos/livecore-platform/
repos/livecore-deploy/
repos/arcanos-app/
repos/arcanos-mobile/
repos/scenarioos-enterprise/
```

## Critical Core rule

The Core Platform must never depend on ArcanOS, Pen-and-Paper, DnD, Enterprise, Mobile App Store UI, or ScenarioOS language.

Allowed Core language:

```text
Organization, Workspace, WorkspaceMember, Session, Participant, Scene, ContentBlock, Entity, EntityType, Asset, VisibilityRule, Reveal, SessionEvent, Template, AuditLog, Recap, PlanDefinition, EntitlementDefinition, SubjectEntitlement, QuotaDefinition, QuotaUsage, PurchaseProvider, PurchaseTransaction
```

Forbidden Core language includes:

```text
Campaign, Dungeon Master, DM, GM, Player, Party, NPC, Quest, Monster, Spell, Encounter, Character Sheet, Facilitator, Trainee, Training, Incident, Debrief, Department, AdMob UI, App Store copy, Google Play copy, paywall screen copy
```

Provider names such as Apple, Google, OIDC, S3, PostgreSQL, Valkey and Railway may appear in infrastructure/provider modules and deployment docs. They must not become product-domain concepts.

## Root files to read first

Before giving anything to an LLM, read these root files in this order:

1. `00_BEFORE_LLM_CHECKLIST.md`
2. `01_REPO_CREATION_ORDER.md`
3. `02_MANUAL_SETUP_CHECKLIST.md`
4. `03_LLM_WORKFLOW.md`
5. `04_BOUNDARY_AND_SECURITY_GATES.md`
6. `05_HUMAN_REVIEW_CHECKLIST.md`
7. `07_MOBILE_APPSTORE_DECISION_RECORD.md`
8. `08_REPO_COPY_UPDATE_INSTRUCTIONS.md`

Then copy the repo-specific folders into their repositories.
Only after that, give one repository and one story at a time to an LLM agent.

## Important note about design artifacts

The Claude Design HTML files are visual references for ArcanOS only. They are not Core specifications and must not be copied into `livecore-platform`.

Do not paste generated HTML directly into production code. If you keep the raw HTML files, place them only under an ArcanOS reference-designs folder and mark them as non-source material.
