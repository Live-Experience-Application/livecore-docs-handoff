# Repo Copy and Update Instructions

This package is complete. It is not an addendum.

Use it to update the existing repositories and to create the new `arcanos-mobile` repository.

## Target organization

```text
Live-Experience-Application
```

## Target repositories

```text
livecore-docs-handoff
livecore-platform
livecore-deploy
arcanos-app
arcanos-mobile
scenarioos-enterprise
```

## Copy rule

For each repository, copy the contents of:

```text
repos/<repo-name>/
```

into the root of the matching GitHub repository.

Do not copy the `repos/<repo-name>` folder itself. Copy its contents.

## Root governance files

Copy the root files of this handoff into `livecore-docs-handoff` as governance material, or keep them in your local operations folder. Recommended location in `livecore-docs-handoff`:

```text
README.md
00_BEFORE_LLM_CHECKLIST.md
01_REPO_CREATION_ORDER.md
02_MANUAL_SETUP_CHECKLIST.md
03_LLM_WORKFLOW.md
04_BOUNDARY_AND_SECURITY_GATES.md
05_HUMAN_REVIEW_CHECKLIST.md
06_REFERENCES.md
07_MOBILE_APPSTORE_DECISION_RECORD.md
08_REPO_COPY_UPDATE_INSTRUCTIONS.md
09_FIRST_LLM_TASKS.md
PACKAGE_CONTENTS.md
templates/
```

## Existing repos

Update these existing repos by copying their folder contents:

```text
repos/livecore-docs-handoff/*   -> livecore-docs-handoff/
repos/livecore-platform/*       -> livecore-platform/
repos/livecore-deploy/*         -> livecore-deploy/
repos/arcanos-app/*             -> arcanos-app/
repos/scenarioos-enterprise/*   -> scenarioos-enterprise/
```

## New repo

Create this new repo:

```text
arcanos-mobile
```

Then copy:

```text
repos/arcanos-mobile/* -> arcanos-mobile/
```

## Do not overwrite manually chosen files blindly

Review before overwriting:

```text
LICENSE
.gitignore
.editorconfig
README.md if you already customized it
```

## Do not start coding immediately

After copying docs:

1. Commit docs-only changes.
2. Enable branch protection.
3. Create/refresh project board labels.
4. Pick exactly one story from `livecore-platform/csv/core_epics_stories.csv`.
5. Use `templates/STORY_PROMPT_TEMPLATE.md`.

Do not start `arcanos-mobile` until Core Entitlements, Quota Status and Ad Eligibility contracts exist.
Do not start `scenarioos-enterprise` until Core authorization, audit and export/report foundations exist.
