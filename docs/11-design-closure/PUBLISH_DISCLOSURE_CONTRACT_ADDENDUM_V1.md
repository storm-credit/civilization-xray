# Publish Disclosure Contract Addendum v1

Status: **Additive contract refinement after Design Closure 0.6**  
Reason: current YouTube AI disclosure / monetization policy validation.  
Does not create an eighth core artifact.

This addendum augments the existing P6 Production Pack and P7 Review & Run Ledger semantics in `CORE_ARTIFACT_CONTRACTS_V1.md`.

---

# 1. Principle

There are three separate questions:

1. **Was AI/generative tooling used?** — provenance question.
2. **Could the output mislead viewers about what was real?** — truth/reconstruction question.
3. **Does the destination platform require an AI/synthetic-content disclosure?** — platform release question.

They must not be collapsed into one boolean.

A generated asset can be:
- permitted but disclosure-required;
- permitted and disclosure-not-required;
- disclosure-required but still rights-blocked;
- non-AI but still rights-blocked.

---

# 2. P6 Production Pack Addendum — Asset-Level Synthetic Media State

For every publish-bound visual/audio asset, Production Pack should be able to represent:

- `synthetic_media_class`
  - NONE
  - NONREALISTIC_GENERATED
  - REALISTIC_GENERATED
  - ALTERED_REAL
  - AI_MUSIC
  - VOICE_CLONE
  - OTHER
- `real_person_or_place_refs[]`
- `reconstruction_level`
- `voice_identity_type`
  - NONE
  - OWN
  - LICENSED_OTHER
  - FICTIONAL_PROVIDER_VOICE
- `voice_consent_or_license_ref`
- `ai_disclosure_candidate`
  - YES
  - NO
  - REVIEW
- `ai_disclosure_reason`
- `provider_provenance_ref`
- `terms_review_ref`
- `content_credentials_or_provider_marker` when available
- `rights_status`

## P6 selection gate addition

A publish-bound asset cannot become final `SELECTED` when:
- synthetic class is unknown for an obviously generated/altered asset;
- identifiable third-party voice/likeness permission is unresolved;
- provider/source commercial-use terms are unresolved;
- realistic reconstruction has no appropriate truth/reconstruction classification;
- required provenance needed for release disclosure has been lost.

---

# 3. P7 Review & Run Ledger Addendum — Upload-Level Disclosure State

For each release decision, Ledger should record:

- `destination_platform`
- `platform_policy_snapshot_date`
- `ai_disclosure_required`
  - YES
  - NO
  - REVIEW
- `ai_disclosure_reason`
- `platform_ai_setting`
  - YES
  - NO
  - NOT_APPLICABLE
  - NOT_PUBLISHED
- `rights_verdict`
- `monetization_authenticity_review`
  - PASS
  - REVISE
  - BLOCK
- `human_release_approval_ref`

## Derivation rule

P7 derives the upload disclosure from all selected P6 assets plus final edit context.

Example:
- deterministic Blender cutaways only → likely NO disclosure solely for AI use;
- same episode adds realistic AI historical footage → likely YES;
- visuals remain deterministic but AI-generated music is used → current YouTube examples imply YES.

Do not determine upload disclosure by looking only at the hero shot.

---

# 4. Release Gate Additions

Final release is BLOCKED when any is true:

1. `ai_disclosure_required = REVIEW` and the ambiguity is consequential.
2. platform requires disclosure but final upload setting is not recorded as compliant.
3. third-party voice/likeness permission remains unresolved.
4. rights status of generated music or external media remains unresolved.
5. realistic reconstruction is likely to be interpreted as documentary footage without the required platform/editorial transparency.
6. final episode fails authenticity review because it is materially repetitive/mass-produced/template-substitution rather than an episode-specific explanation.
7. current policy snapshot is stale enough that a consequential decision cannot be trusted.

---

# 5. Separation from Editorial Reconstruction Labels

Platform disclosure and in-video historical/factual qualifier are different controls.

Example:
- YouTube label: tells viewers AI-generated/altered media was used.
- Civilization X-Ray qualifier: tells viewers a specific pile arrangement, worker action, historical scene or internal geometry is representative/reconstructed rather than directly documented.

One never replaces the other.

---

# 6. No Architecture Expansion

Do not create:
- AI Disclosure Orchestra
- Policy Agent as a new top-level orchestra
- eighth `Disclosure Manifest` core artifact

Use:
- existing Rights Governance for policy interpretation/blocking;
- P6 for asset-level provenance/classification;
- P7 for final platform disclosure and human release decision.

If implementation later needs a machine-readable policy cache, it is a shared service/config concern, not a new creative responsibility domain.

---

# 7. Refresh Rule

Platform/provider policy is volatile state.

Before release automation is implemented or materially changed:
- refresh YouTube AI disclosure rules;
- refresh YPP authenticity/monetization rules;
- refresh selected video/TTS/music provider terms;
- record snapshot date/version/source in policy registry or Ledger.

No stale policy snapshot may silently authorize publication.
