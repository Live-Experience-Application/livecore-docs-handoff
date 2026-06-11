# Before You Give This Project to an LLM

This is the mandatory preparation checklist. Do not skip it.

## 1. Confirm final repository names

Use the organization `Live-Experience-Application` and these repositories:

```text
livecore-docs-handoff
livecore-platform
livecore-deploy
arcanos-app
arcanos-mobile
scenarioos-enterprise
```

Recommended visibility:

```text
livecore-docs-handoff      private during early implementation
livecore-platform          private first; later AGPL/dual-license decision
livecore-deploy            private first
arcanos-app                private first
arcanos-mobile             private until App Store / Google Play compliance review
scenarioos-enterprise      private; do not publish until licensing and enterprise strategy are reviewed
```

## 2. Create repositories manually

Create empty repositories first. Do not let an LLM create repository structure before the docs are in place.

For each repository:

- initialize with no generated template, or with only `.gitignore` if you prefer
- add the matching contents from `repos/<repo-name>/`
- commit the documentation first
- protect the `main` branch
- require PR reviews, even if you review yourself
- require status checks once CI exists

## 3. Add license files manually

Recommended initial approach:

- `livecore-platform`: AGPL-3.0-or-later, with a note that commercial dual licensing may be offered later
- `arcanos-app`: owner-controlled license strategy; AGPL only if you intentionally want the vertical open source
- `arcanos-mobile`: keep private initially; do not publish as AGPL without legal review because App Store distribution and strong copyleft licensing can be complicated
- `scenarioos-enterprise`: keep private unless you intentionally want the enterprise vertical to be open source
- `livecore-deploy`: same as Core or owner-controlled internal deployment license
- `livecore-docs-handoff`: documentation license of your choice

This is not legal advice. Get legal review before public launch, dual licensing, App Store/Google Play release, or accepting external contributions.

## 4. Decide contribution model before external contributors

Before accepting outside code:

- decide whether you need a Contributor License Agreement
- decide whether you allow copied code from LLMs or external snippets
- require signed-off commits if desired
- require dependency license review
- define what generated code is acceptable and how it is reviewed

## 5. Do not paste Claude Design HTML into Core

The uploaded design artifacts are ArcanOS visual references, not Core specifications.

They contain Pen-and-Paper language such as DM Only, Visible to Party, Whispered, Quest, NPC, Monster Stats and Dungeon Master OS. These are valid in `arcanos-app` or `arcanos-mobile` documentation/reference material, not in `livecore-platform`.

## 6. Choose local development baseline

Minimum local tools:

```text
Git
Docker Desktop or compatible Docker Engine
Node.js LTS / current stable pinned by the repo
pnpm
.NET SDK LTS version pinned in global.json
PostgreSQL client tools
```

Do not let an LLM silently choose unpinned tool versions.

## 7. Create a project board

Create a GitHub project board with columns:

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

Use:

```text
templates/STORY_PROMPT_TEMPLATE.md
templates/MOBILE_STORY_PROMPT_TEMPLATE.md for arcanos-mobile tasks
```

## 9. Do not start mobile billing too early

Do not implement App Store or Google Play Billing SDKs before the Core has:

- authenticated accounts
- Entitlements API
- Quota Status API
- purchase verification contracts
- purchase event audit trail
- refund/cancellation downgrade behavior

## 10. Do not start ads too early

Do not integrate ad SDKs before the mobile repo has:

- consent/privacy flow design
- server-side ad eligibility API
- forbidden ad placement policy
- privacy label/data-safety checklist
- test-only placeholder ad slots
