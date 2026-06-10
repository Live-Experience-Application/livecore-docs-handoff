# Human Review Checklist

Use this before merging any LLM-generated PR.

## Scope

- [ ] Implements exactly one story
- [ ] No unrelated refactor
- [ ] No hidden feature expansion
- [ ] No new architecture decision without ADR

## Core boundary

- [ ] No vertical terms in Core source
- [ ] No ArcanOS imports in Core
- [ ] No ScenarioOS imports in Core
- [ ] Domain names follow approved language
- [ ] Public contracts remain generic

## Security

- [ ] Every read endpoint checks authorization
- [ ] Every write endpoint checks authorization
- [ ] Object-level authorization is present
- [ ] WebSocket events are recipient-filtered
- [ ] Assets require signed URL after permission check
- [ ] No secrets in code or docs examples
- [ ] Logs do not contain sensitive content

## Clean code

- [ ] Small cohesive modules
- [ ] No God service
- [ ] No duplicated domain rules
- [ ] No over-engineered abstraction
- [ ] No generated code dumps without structure
- [ ] Naming is clear and stable

## Tests

- [ ] Unit tests for domain rules
- [ ] Integration tests for API and database behavior
- [ ] Authorization tests for negative cases
- [ ] Realtime tests when relevant
- [ ] Migration tests when database changes

## Documentation

- [ ] Docs updated if behavior changed
- [ ] API contract updated if endpoint changed
- [ ] Event catalog updated if event changed
- [ ] DB schema docs updated if migration changed
- [ ] ADR added if architectural decision changed

## Merge decision

Merge only if all critical checks pass. If unsure, do not merge.
