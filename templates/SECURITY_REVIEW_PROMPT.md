# Security Review Prompt

```text
Perform a security review for story <story-id> in repository <repo-name>.

Check specifically:
- broken object-level authorization
- broken function-level authorization
- visibility leaks
- asset URL leaks
- WebSocket event leaks
- tenant isolation
- input validation
- audit log completeness
- sensitive data in logs
- secret handling

Use the repository docs as source of truth.
Do not suggest broad rewrites. Return concrete issues and required fixes.
```
