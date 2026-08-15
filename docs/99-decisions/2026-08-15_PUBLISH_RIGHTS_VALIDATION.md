# 2026-08-15 — Publish Rights / AI Disclosure Validation

## Decision

- Previous decision / assumption: Rights Governance, asset provenance and Release Gate were already part of the closed architecture, but destination-platform AI disclosure was not yet represented as an explicit asset→upload derivation contract.
- New decision: Keep the existing four-orchestra/seven-artifact architecture and add an asset-level synthetic-media classification in P6 plus upload-level AI disclosure/authenticity state in P7 through `PUBLISH_DISCLOSURE_CONTRACT_ADDENDUM_V1.md`.
- Trigger / evidence: Current YouTube Help requires disclosure for realistic AI-generated/meaningfully altered content and provides examples including AI-generated music and third-party voice cloning; YouTube monetization policy separately rejects repetitive/mass-produced inauthentic content regardless of how it was created.
- Why changed: Rights clearance, factual reconstruction labeling and platform AI disclosure are related but not identical. Without explicit state, a publish workflow could have complete provider provenance but still omit a required platform disclosure.
- Impact: future Release Gate, Production Pack media metadata, Review & Run Ledger release events, generated music/video/voice handling.
- Reversible?: Yes as field naming/implementation; the conceptual separation should remain while current platform rules require it.
- Rollback path: supersede this addendum if platform policy materially changes, preserving historical release records with their policy snapshot dates.
- Affected files/stages: `docs/09-validation/PUBLISH_RIGHTS_DISCLOSURE_VALIDATION_2026_08_15.md`, `docs/11-design-closure/PUBLISH_DISCLOSURE_CONTRACT_ADDENDUM_V1.md`, future P6/P7 implementation.
- Follow-up validation: refresh YouTube/provider terms immediately before release-automation implementation and test at least one release candidate with realistic generated historical footage, one with AI music only, and one with no disclosure-required media.

## Architecture verdict

- new orchestra: NO
- eighth core artifact: NO
- implementation code: NO
- existing Rights Governance: PASS with additive release metadata
