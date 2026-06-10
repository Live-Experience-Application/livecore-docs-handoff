# LLM Delivery Process

## Agents

Use LLMs as role-based agents:

- Architect reviewer
- Backend implementer
- Frontend implementer
- Security reviewer
- Test writer
- Docs maintainer

Do not let one agent freely rewrite everything.

## Story flow

1. choose story
2. prepare prompt
3. run implementation agent
4. run test agent if needed
5. run security reviewer
6. run human review
7. merge

## Context limit rule

Provide only the repo docs and story relevant to the task. Too much context increases hallucination risk.
