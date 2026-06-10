# Boundary and Security Gates

These gates protect the project from becoming a messy MVP.

## Gate 1: Core language scan

Core repository must not contain forbidden vertical terms outside explicit documentation explaining forbidden terms.

Forbidden examples:

```text
campaign
dungeon
dm
gm
player
party
npc
quest
monster
spell
character sheet
facilitator
trainee
incident
debrief
```

Allowed Core replacements:

```text
workspace
host
participant
entity
entity_type
content_block
visibility_rule
reveal
session_event
recap
```

## Gate 2: Dependency direction

Allowed:

```text
arcanos-app -> livecore-platform contracts/sdk/ui
scenarioos-enterprise -> livecore-platform contracts/sdk/ui
livecore-deploy -> deployment artifacts from livecore-platform and verticals
```

Forbidden:

```text
livecore-platform -> arcanos-app
livecore-platform -> scenarioos-enterprise
arcanos-app -> scenarioos-enterprise
scenarioos-enterprise -> arcanos-app
```

## Gate 3: Server-side visibility

No hidden content may be sent to unauthorized clients.

Bad:

```text
API returns all content; UI hides private content.
```

Good:

```text
API returns only content visible to the authenticated principal.
WebSocket stream emits only events visible to the recipient.
```

## Gate 4: Asset authorization

Assets are private by default.

- no public bucket access
- no static direct URLs without signed URL flow
- signed URL issued only after permission check
- asset metadata filtered by visibility rules

## Gate 5: Realtime authorization

Every event has:

- emitter authorization
- recipient authorization
- persistence rule
- replay rule
- audit rule

## Gate 6: Tests required

Authorization tests are mandatory for:

- workspace access
- scene access
- content block access
- visibility rule updates
- reveal execution
- asset download
- session event replay
- participant reconnect

## Gate 7: Production-ready definition

A feature is not done until it has:

- domain model
- API contract
- server-side validation
- authorization
- persistence
- tests
- observability/logging where relevant
- documentation update
- migration if DB changes
- threat model update if security relevant
