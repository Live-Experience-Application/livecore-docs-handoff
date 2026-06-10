# LLM Development Workflow

## Principle

LLMs are implementation assistants, not product owners.

A coding agent may implement one story at a time. It may not redesign architecture, add features, change scope or introduce vertical language into Core.

## Every task starts with a story

Use the CSV files:

```text
repos/livecore-platform/csv/core_epics_stories.csv
repos/arcanos-app/csv/arcanos_epics_stories.csv
repos/scenarioos-enterprise/csv/scenarioos_epics_stories.csv
repos/livecore-deploy/csv/deploy_epics_stories.csv
```

One row becomes one LLM task.

## Prompt shape

Use `templates/STORY_PROMPT_TEMPLATE.md`.

Must include:

```text
Repository:
Story ID:
Story title:
Files to read first:
Allowed scope:
Forbidden scope:
Acceptance criteria:
Required tests:
Required docs updates:
Output format:
```

## LLM output must include

Every LLM response/PR must include:

- summary
- changed files
- tests added/updated
- commands run
- boundary/security considerations
- risks
- follow-up tasks not implemented

## Stop conditions

Stop the LLM if it:

- adds Pen-and-Paper or Enterprise terms to Core
- adds a dependency without explanation
- writes large unrelated refactors
- creates code without tests for authorization or visibility
- stores secrets in code
- exposes private content to clients and hides it only in UI
- changes public contracts without versioning
- ignores AGENTS.md

## Review loop

1. LLM implements story
2. Run tests
3. Run boundary scan
4. Run format/lint
5. Human reviews architecture and naming
6. Human reviews security implications
7. Merge only if Definition of Done is satisfied

## Never ask an LLM to build everything

Forbidden prompt:

```text
Here are all docs. Build the full product.
```

Correct prompt:

```text
Implement story CORE-001 only. Read AGENTS.md and the specified docs. Do not implement any other story.
```
