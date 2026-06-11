# Decision Record: Native Mobile ArcanOS App

## Decision

Create a separate `arcanos-mobile` repository for the native iOS/Android app.

## Why

The mobile app introduces concerns that do not belong in the web vertical or generic Core:

- App Store / Google Play release pipelines
- StoreKit / Play Billing integration
- mobile ads SDKs
- ATT / advertising consent flows
- native push notifications
- deep links / universal links
- app icons, screenshots, age rating and store metadata
- mobile offline cache constraints
- platform-specific QA

## Dependency direction

Allowed:

```text
arcanos-mobile -> livecore-platform API/contracts/sdk
arcanos-mobile -> arcanos domain labels/templates package, if extracted
arcanos-mobile -> shared design tokens
```

Forbidden:

```text
livecore-platform -> arcanos-mobile
arcanos-app -> arcanos-mobile implementation internals
arcanos-mobile -> scenarioos-enterprise
scenarioos-enterprise -> arcanos-mobile
```

## Product scope

The mobile app is primarily:

- Player Companion
- Join Session
- Current Scene
- Private Messages
- Quest Log
- Character Quick View
- Handout Viewer
- Ad / premium experience
- DM quick-control mode on tablet/phone later

The full Scene Builder and heavy campaign prep remain better on web/tablet/desktop via `arcanos-app`.

## Business model scope

Mobile adds:

- free use with ads
- free host/table limit: one active session with up to four players
- paid host license: unlimited personal sessions/campaigns/participants subject to fair-use terms
- optional player premium: ad-free across sessions
- optional table pass: host removes ads for all participants in hosted sessions

## Store rule

Digital purchases initiated inside the native apps must use the relevant store billing system unless an explicit regional/platform exception applies.
