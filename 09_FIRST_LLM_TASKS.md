# First LLM Tasks

Use this file after all repos contain their documentation.

## Task 0: No code yet

Before running a coding agent:

- read `00_BEFORE_LLM_CHECKLIST.md`
- confirm repo docs are committed
- confirm branch protection is active
- confirm you will use one story per PR

## First implementation repo

Start with:

```text
livecore-platform
```

Do not start with:

```text
arcanos-app
arcanos-mobile
scenarioos-enterprise
```

## First story

Use the first foundation story from:

```text
repos/livecore-platform/csv/core_epics_stories.csv
```

Expected first scope:

```text
repository skeleton
CI baseline
formatting baseline
test baseline
Dockerfile
health endpoint
boundary check script
```

## Prompt skeleton

Use:

```text
templates/STORY_PROMPT_TEMPLATE.md
```

The prompt must include:

```text
Repository: livecore-platform
Story ID: <exact CSV row>
Files to read first:
- AGENTS.md
- README.md
- docs/00_START_HERE.md
- docs/02_ARCHITECTURE.md
- docs/03_DOMAIN_LANGUAGE.md
- docs/04_PRODUCT_BOUNDARIES.md
- docs/05_MODULE_CONTRACTS.md
- docs/07_SECURITY_THREAT_MODEL.md
- docs/17_DEFINITION_OF_DONE.md
- csv/forbidden_core_terms.csv
- csv/core_epics_stories.csv

Allowed scope:
- exactly this one story

Forbidden scope:
- no ArcanOS
- no mobile app
- no ScenarioOS
- no unrelated refactor
- no unapproved dependencies
```

## Mobile first task later

When Core contracts are ready, the first mobile task is:

```text
MOB-001 Mobile repo skeleton
```

Use:

```text
templates/MOBILE_STORY_PROMPT_TEMPLATE.md
```

But do this only after Core foundation and contracts exist.
