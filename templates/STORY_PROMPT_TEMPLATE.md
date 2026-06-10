# Story Prompt Template for LLM Coding Agents

Use this exact structure for each implementation task.

```text
You are working in repository: <repo-name>

Story ID: <story-id>
Story title: <story-title>

Read first:
- AGENTS.md
- README.md
- docs/00_START_HERE.md
- <relevant docs>

Goal:
<one paragraph>

Allowed scope:
- <files/modules allowed>

Forbidden scope:
- Do not implement any other story.
- Do not add new dependencies without explicit justification.
- Do not change public contracts unless the story requires it.
- Do not use vertical-specific language in Core.
- Do not store secrets in code.

Acceptance criteria:
- <copy from story CSV>

Required tests:
- <unit/integration/security tests>

Required docs update:
- <docs to update or say none>

Output format:
1. Summary
2. Changed files
3. Tests added/updated
4. Commands run
5. Boundary/security considerations
6. Risks or follow-up tasks not implemented
```
