# Repository Creation and Development Order

## Final repository split

Separate repositories are required for this project because they enforce clearer ownership and reduce the chance that vertical language leaks into the Core.

```text
livecore-docs-handoff
livecore-platform
livecore-deploy
arcanos-app
arcanos-mobile
scenarioos-enterprise
```

## Why separate repos

Benefits:

- Core stays product-neutral
- ArcanOS Web can move fast without polluting Core
- ArcanOS Mobile can handle App Store / Google Play topics without polluting the web app or Core
- ScenarioOS can remain private or commercially licensed
- deployment logic is reusable across products
- LLMs receive smaller context windows
- versioned contracts become necessary, which improves maintainability

Risks:

- cross-repo versioning must be disciplined
- contracts need semantic versioning
- local development is slightly more complex
- you need a clear release process

The risks are acceptable because this is intended to become production-grade, not a quick MVP.

## Development order

### 1. livecore-docs-handoff

Purpose:

- stores cross-repo governance
- defines LLM process
- defines architecture decision records
- stores global product boundaries
- stores mobile App Store governance

First action:

- copy `repos/livecore-docs-handoff/` into the repo
- copy root templates into the repo if you want one central governance source
- commit docs only
- do not implement product code here

### 2. livecore-platform

Purpose:

- owns the generic Core Platform
- owns API, database, realtime, permission engine, audit, assets, SDK contracts, generic UI primitives, entitlements, quotas and purchase verification contracts

First implementation milestone:

- repository skeleton
- CI
- formatting
- tests
- Dockerfile
- health endpoint
- boundary check script

No ArcanOS, mobile UI or ScenarioOS code is allowed here.

### 3. livecore-deploy

Purpose:

- owns Docker Compose
- owns Kubernetes/Helm
- owns Railway deployment references
- owns backup/restore scripts
- owns production operations docs
- owns mobile store backend operations docs

Start after `livecore-platform` has a bootable API container.

### 4. arcanos-app

Purpose:

- Pen-and-Paper / 5e-compatible / tabletop web vertical
- consumes Core API, Core SDK and Core UI primitives
- owns ArcanOS domain labels, templates, theme, Player Companion web/PWA and DM/GM experience

Start after Core has stable contracts for:

```text
Workspace
Session
Participant
Scene
ContentBlock
Entity
VisibilityRule
SessionEvent
Asset
```

### 5. arcanos-mobile

Purpose:

- native iOS/Android app for ArcanOS
- consumes Core API, Core SDK/contracts and ArcanOS labels/templates
- owns mobile UX, player companion, join session, push notifications later, ads, premium/paywall UI and store release workflow

Start after Core has stable contracts for:

```text
Auth
Workspace
Session
Participant
Scene
ContentBlock
Entity
VisibilityRule
SessionEvent
Asset
Entitlements
Quota Status
Ad Eligibility
```

Start with mobile shell and mocked billing/ads. Do not integrate real store SDKs until backend purchase verification exists.

### 6. scenarioos-enterprise

Purpose:

- enterprise training/simulation/workshop vertical
- consumes Core API and SDK
- owns enterprise-specific templates, reports, role terminology and compliance UX

Start only after:

- Core boundary is proven by ArcanOS Web and/or ArcanOS Mobile
- authorization matrix is implemented
- audit log is implemented
- export/report foundations exist
- licensing is reviewed

## Versioning rule

Core contracts must use semantic versioning:

```text
@livecore/contracts v0.1.0
@livecore/sdk v0.1.0
@livecore/ui-core v0.1.0
livecore-api Docker image v0.1.0
```

Verticals must declare compatible Core versions explicitly.
