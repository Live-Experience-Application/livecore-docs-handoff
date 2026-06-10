# Before You Give This Project to an LLM

This is the mandatory preparation checklist. Do not skip it.

## 1. Decide final repository names

Recommended names:

```text
livecore-docs-handoff
livecore-platform
livecore-deploy
arcanos-app
scenarioos-enterprise
```

Use an organization namespace if possible, for example:

```text
github.com/your-org/livecore-platform
github.com/your-org/arcanos-app
```

## 2. Create repositories manually

Create empty repositories first. Do not let an LLM create repository structure before the docs are in place.

For each repository:

- initialize with no generated template, or with only `.gitignore` if you prefer
- add the matching contents from `repos/<repo-name>/`
- commit the documentation first
- protect the `main` branch fehlt
- require PR reviews, even if you review yourself fehlt
- require status checks once CI exists fehlt

## 3. Add license files manually

Recommended initial approach:

- `livecore-platform`: AGPL-3.0-or-later, with a note that commercial dual licensing may be offered later
- `arcanos-app`: same owner-controlled license strategy; AGPL if open source, commercial license if you want proprietary distribution later
- `scenarioos-enterprise`: do not publish as AGPL unless you intentionally want the enterprise vertical to be open source; keep private until legal review
- `livecore-deploy`: same as Core or permissive internal deployment license, depending on strategy
- `livecore-docs-handoff`: documentation license of your choice

This is not legal advice. Get legal review before public launch, dual licensing or accepting external contributions.

## 4. Decide contribution model before external contributors

Before accepting outside code:

- decide whether you need a Contributor License Agreement
- decide whether you allow copied code from LLMs or external snippets
- require signed-off commits if desired
- require dependency license review

## 5. Do not paste Claude Design HTML into Core

The uploaded design artifacts are ArcanOS visual references, not Core specifications.

They contain Pen-and-Paper language such as DM Only, Visible to Party, Whispered, Quest, NPC, Monster Stats and Dungeon Master OS. These are valid in `arcanos-app`, not in `livecore-platform`.

## 6. Choose local development baseline

Minimum local tools:

```text
Git
Docker Desktop or compatible Docker Engine
Node.js LTS / current stable pinned by the repo
pnpm
.NET SDK 10 LTS or the chosen LTS version pinned in global.json
PostgreSQL client tools
```

Do not let an LLM silently choose unpinned tool versions.

## 7. Create a project board

Create a project board with columns:

```text
Backlog
Ready for LLM
In Progress
Human Review
Security Review
Done
Blocked
```

One story = one PR. No giant PRs.

## 8. Prepare LLM usage rules

Every LLM task must include:

- repository name
- story ID
- exact files to read first
- exact output expectations
- no unrelated refactoring
- no new dependencies without approval
- tests required
- boundary scan required
- human review required

Use `templates/STORY_PROMPT_TEMPLATE.md`.
