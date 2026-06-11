# Mobile Story Prompt Template

Use this when giving `arcanos-mobile` work to an LLM.

```text
Repository:
arcanos-mobile

Story ID:
<from csv/mobile_epics_stories.csv>

Story title:
<title>

Files to read first:
- AGENTS.md
- README.md
- docs/00_START_HERE.md
- docs/01_MOBILE_PRODUCT_SCOPE.md
- docs/02_ARCHITECTURE.md
- docs/03_MONETIZATION_AND_ENTITLEMENTS.md
- docs/04_ADS_POLICY.md
- docs/05_STORE_COMPLIANCE.md
- docs/06_SECURITY_AND_PRIVACY.md
- docs/07_DND_IP_AND_CONTENT.md
- docs/08_OFFLINE_AND_SYNC.md
- docs/09_RELEASE_PROCESS.md
- csv/mobile_epics_stories.csv

Allowed scope:
<exact scope>

Forbidden scope:
- Do not implement unrelated stories.
- Do not add real ad SDK unless this story is explicitly about ad SDK integration.
- Do not add real billing SDK unless this story is explicitly about billing integration.
- Do not unlock premium features from client state alone.
- Do not cache unauthorized content.
- Do not use official DnD/Wizards branding.

Acceptance criteria:
<copy from CSV and expand>

Required tests:
- Unit tests where possible.
- Component tests for UI states.
- Security/privacy regression test if cache/auth/entitlements are touched.

Output format:
- Summary
- Changed files
- Commands run
- Tests added/updated
- Store compliance considerations
- Privacy/security considerations
- Risks
- Follow-up tasks not implemented
```
