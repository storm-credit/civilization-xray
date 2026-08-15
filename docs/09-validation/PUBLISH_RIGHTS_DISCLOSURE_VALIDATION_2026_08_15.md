# Publish Rights & AI Disclosure Validation — 2026-08-15

Status: **Empirical no-code policy validation**  
Scope: YouTube publishing/disclosure/monetization + generated-media provenance.  
Architecture effect: **no new orchestra, no eighth core artifact, no implementation code**.

This snapshot validates whether the existing Fact / Rights / Quality Governance and Release & Learning contracts are strong enough for current platform rules.

---

# 1. Source Policy

Checked current first-party sources on 2026-08-15:

- YouTube Help — GenAI / altered or synthetic content disclosure
- YouTube Help — channel monetization / inauthentic content
- YouTube Help — impersonation / privacy / likeness handling
- Gemini API Additional Terms of Service
- Google Generative AI Prohibited Use Policy
- Blender official licensing/manual guidance

Rules:
- platform policy is volatile; refresh before publish-system implementation and after material policy updates;
- legal/platform requirements are not inferred from community posts when first-party Help/Terms exist;
- this document is operational guidance, not legal advice;
- when rights are unclear, Release Gate blocks rather than guessing.

---

# 2. YouTube AI Disclosure — Current Operational Rule

YouTube currently requires creators to disclose AI-generated or meaningfully AI-altered content when it is realistic/photorealistic or meaningfully changes what viewers could believe happened.

Core trigger classes include:
- a real person appears to say/do something they did not;
- real event/place footage is meaningfully altered;
- a realistic scene is generated that did not actually occur.

YouTube also gives concrete examples that matter directly to Civilization X-Ray.

## Usually DOES require disclosure

### A. Realistic generative reconstruction of a real place/event
Examples for this project:
- photorealistic historical Venice reconstruction generated with Google video models;
- realistic generated workers constructing a real historical structure;
- realistic generated flood/disaster/mechanism event shown at a real named location when it did not occur as shown.

Default project rule:
**If a reasonable viewer could interpret a generated scene of a real place/person/event as camera-captured reality, disclose.**

### B. AI-generated music
YouTube's examples explicitly include AI-generated music as disclosure-required.

Project rule:
- generated Lyria/other GenAI score present in the uploaded video → `AI_DISCLOSURE_REQUIRED = YES` unless current policy has changed at publish time.

### C. Someone else's cloned/synthetic voice
YouTube examples treat cloning someone else's voice as disclosure-required, and impersonation/privacy policies create an additional consent/removal risk.

Project rule:
- do not use another identifiable person's cloned voice without documented permission and a specific editorial reason;
- disclosure does not substitute for consent/rights.

## Usually DOES NOT require disclosure by itself

Current YouTube examples include:
- AI used for outline/script/title/thumbnail/infographic assistance;
- caption generation;
- minor visual/audio repair;
- non-realistic/fantastical animation;
- cloning one's own voice for voice-over/dubbing.

Project interpretation:
- the fact that an LLM helped write the script does not alone trigger the upload disclosure;
- schematic/non-photorealistic Blender explanation is not treated as realistic synthetic event footage merely because software/AI assisted the workflow;
- however, if a thumbnail itself creates a realistic false event/person depiction, evaluate the realistic-content rule rather than relying on the generic thumbnail-assistance exception.

## Conservative ambiguity rule

If the scene is borderline between explanatory reconstruction and photorealistic reality:
1. classify the synthetic element;
2. record the ambiguity;
3. prefer disclosure rather than concealment when disclosure does not itself create a legal/factual problem;
4. never use disclosure as permission to publish an otherwise misleading or rights-violating asset.

---

# 3. Disclosure Does Not Equal Monetization Penalty

Current YouTube Help states that disclosing altered/AI content does not by itself limit audience reach or monetization eligibility.

However, persistent failure to disclose required AI content can lead to YouTube applying labels and can expose a creator to stronger enforcement, including YPP consequences.

Therefore:
- `AI disclosure = YES` is not a quality failure;
- `required disclosure omitted` is a Release Gate failure.

This avoids the bad incentive to hide AI usage in order to protect revenue.

---

# 4. Monetization Risk — Inauthentic / Mass-Produced Content

YouTube's monetization policy clarifies that repetitive or mass-produced content with insufficient original/authentic value can be ineligible for monetization. The policy applies regardless of whether AI was used.

This is highly relevant to an automated documentary channel.

## Civilization X-Ray anti-inauthenticity rule

Automation may repeat the **production system**, but episodes must not be interchangeable template output.

Each publish candidate should demonstrate episode-specific value through at least:
- a distinct central question/mechanism;
- episode-specific Evidence Pack and claim/source lineage;
- original explanatory ordering/interpretation;
- visual proof designed for those claims rather than generic B-roll;
- substantive narration/editorial choices;
- meaningful difference from adjacent uploads;
- final human/reviewer accountability for the release decision.

### Allowed repetition
Reusable channel language is expected:
- camera grammar
- visual style
- intro/outro identity
- shared Blender rigs
- audio motifs
- artifact/gate workflow

### High-risk repetition
- same script shell with nouns swapped;
- bulk episodes created from identical prompts with little factual/editorial differentiation;
- stock/AI montage + generic narration where visuals do not prove the claim;
- automatic rephrasing of other sources without substantial original explanation;
- automated upload volume being optimized ahead of episode quality.

Project conclusion:
The existing `Explain, not decorate`, evidence lineage, Script↔Visual grammar and human release gate are not merely quality preferences; they also reduce platform monetization risk.

---

# 5. Real Person / Voice / Likeness Safety

Current YouTube impersonation/privacy systems explicitly recognize AI copying of a person's likeness or voice as a potential policy/privacy problem.

Project rules:
- no unauthorized voice cloning of identifiable third parties;
- no generated real-person performance presented as authentic;
- public/historical figures do not receive an automatic exception from disclosure or editorial truth requirements;
- parody/satire/public-interest factors may affect platform review, but Civilization X-Ray should not rely on those exceptions as a baseline production route;
- consent/provenance records remain required even when platform upload disclosure is satisfied.

For a fictional/non-identifiable narrator voice:
- record provider/voice identity/license/terms;
- confirm commercial-use conditions at time of selection;
- avoid intentionally imitating a recognizable living person's voice without permission.

---

# 6. Google Generated Content Terms — Ownership Is Not the Whole Rights Story

Current Gemini API Additional Terms state that Google does not claim ownership over original content generated through covered services, while also noting that similar content may be generated for others and that the user remains responsible for lawful use of generated output.

Architecture implications:
- do not describe provider-generated output as exclusive merely because it was generated for this project;
- provider non-ownership does not prove that a generated asset is free of third-party rights issues;
- Rights Governance must still review prompts/references/voice likeness/music provenance and publishing use;
- output provenance should preserve provider/model/date/terms-review state.

## Data-handling implication

Google's current Gemini API terms distinguish unpaid services such as AI Studio/unpaid quota and explain that submitted/generated content can be used to improve Google products under those service conditions.

Project rule:
- do not send confidential/unreleased sensitive source material to unpaid provider routes by default;
- provider data-use mode becomes part of the implementation-time Provider Registry and security review;
- secrets/private credentials never belong in prompts or generation artifacts.

---

# 7. Blender Output / Asset Rights Boundary

Official Blender guidance states that Blender's GPL applies to Blender itself, not automatically to artwork created using Blender.

Therefore:
- a render does not become GPL merely because Blender generated it;
- BUT this says nothing about licenses of imported meshes, textures, fonts, maps, photos, scans or other source assets;
- every external asset remains subject to its own license/provenance rules.

Project rule:
`Blender-created` is a tool provenance label, not a rights-cleared verdict.

---

# 8. Publish Disclosure Decision Matrix

| Element | Default disclosure decision | Additional project gate |
|---|---|---|
| Research-driven schematic Blender cutaway | Usually NO solely for AI disclosure | sources + reconstruction/scale labels |
| Clearly non-realistic explanatory animation | Usually NO | visual truth / rights |
| Photorealistic generated reconstruction of real Venice/Rome/etc. | YES | reconstruction qualifier + provenance |
| Generated historical worker activity at a real site | YES if realistic | no false documentary implication |
| AI-generated music | YES | music terms/rights/provenance |
| Own voice clone for narration | YouTube example says disclosure not required solely for this | voice ownership/consent + provider terms |
| Third-party voice clone | YES | permission/identity/impersonation block |
| LLM-assisted script/title/outline | NO solely for assistance | fact QA / originality |
| AI-assisted thumbnail composition | NO solely for assistance | if realistic false event/person is depicted, reassess as YES |
| AI captions | NO solely for AI use | caption accuracy |
| Native audio from generated video | Depends on what it simulates | Sound Truth + rights + mix QA |

This matrix is a **default triage**, not a substitute for checking current YouTube policy at upload time.

---

# 9. Artifact Contract Addition — No New Physical Artifact

The existing seven-artifact model is sufficient.

## P6 Production Pack — per media item
Add/retain structured metadata conceptually equivalent to:
- `synthetic_media_class`: NONE | NONREALISTIC_GENERATED | REALISTIC_GENERATED | ALTERED_REAL | AI_MUSIC | VOICE_CLONE | OTHER
- `real_person_or_place_refs[]`
- `voice_identity_type`: NONE | OWN | LICENSED_OTHER | FICTIONAL_PROVIDER_VOICE
- `voice_consent_or_license_ref`
- `ai_disclosure_candidate`: YES | NO | REVIEW
- `ai_disclosure_reason`
- `content_credentials_or_provider_markers` when known
- `terms_review_ref`

## P7 Review & Run Ledger — release decision
Record:
- `platform_policy_snapshot_date`
- `ai_disclosure_required`: YES | NO | REVIEW
- `ai_disclosure_reason`
- `youtube_ai_use_setting`: YES | NO | NOT_APPLICABLE | NOT_PUBLISHED
- `rights_verdict`
- `monetization_authenticity_review`: PASS | REVISE | BLOCK
- `human_release_approval_ref`

## Release Gate hard fails
- required AI disclosure unresolved/omitted;
- third-party voice/likeness permission unresolved;
- generated music/source terms unresolved;
- realistic historical reconstruction lacks appropriate truth/reconstruction handling;
- content is materially templated/mass-produced such that originality/authenticity review fails;
- current platform-policy snapshot is too stale for a consequential ambiguous case.

---

# 10. Blind-Spot Sweep Findings

## B1 — Disclosure and factual qualifier are different controls
A YouTube AI label says content used AI; it does not explain which historical details are reconstructed.

Therefore both may be needed:
- platform AI disclosure;
- in-video/caption/editorial reconstruction qualifier.

## B2 — Disclosure is episode-level, provenance is asset-level
One upload setting cannot replace per-asset provenance.

Therefore:
- P6 tracks synthetic status for every asset;
- P7 derives the final upload disclosure decision.

## B3 — AI music can trigger disclosure even when visuals are fully deterministic
Do not compute disclosure based only on video shots.

## B4 — Native video-model audio can silently cross governance boundaries
A realistic generated scene may contain generated voices/environment audio.

Therefore native audio must be inspected/classified separately; muting/replacing it is allowed and often preferable.

## B5 — Automation can create YPP risk even with fully original source material
High-volume templated execution can look mass-produced despite valid research.

Therefore Release QA evaluates substantive episode differentiation, not just copyright ownership.

## B6 — Provider ownership language is not commercial-clearance proof
No provider ownership claim ≠ guaranteed uniqueness, trademark clearance, likeness permission, music clearance, or factual accuracy.

---

# 11. Final Verdict

- existing Rights Governance: **VALID, needs explicit disclosure metadata**
- seven core artifacts: **SUFFICIENT**
- new physical artifact required: **NO**
- YouTube AI disclosure field needed: **YES**
- realistic generated historical/place footage: **DEFAULT DISCLOSE**
- AI-generated music: **DISCLOSE under current YouTube examples**
- own-voice clone: **no automatic YouTube disclosure requirement in current examples, but provenance still required**
- third-party voice clone: **high-risk / permission + disclosure required**
- disclosure harms monetization by itself: **NO according to current YouTube Help**
- mass-produced/repetitive automation risk: **YES; prevent via episode-specific research/explanation and release QA**
- architecture change: **NO**
- implementation authorized: **NO**

Next refresh points:
1. immediately before publish automation implementation;
2. whenever YouTube changes AI disclosure/YPP policy;
3. whenever a voice/music/video provider changes commercial-use or data-use terms.
