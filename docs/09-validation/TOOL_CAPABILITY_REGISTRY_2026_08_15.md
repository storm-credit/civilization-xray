# Tool Capability Registry — 2026-08-15

Status: **Empirical no-code validation snapshot**  
Scope: implementation-facing capability facts only; **not a provider lock or implementation plan**.

This document records current official capabilities that affect the already-closed Civilization X-Ray architecture. It exists to prevent stale assumptions from being promoted into Phase 1 code.

## 1. Snapshot Rules

- Snapshot date: 2026-08-15 (Asia/Seoul).
- Prefer official/primary documentation.
- Model IDs, prices, quotas, preview/stable status and SDK interfaces are volatile.
- Refresh this registry immediately before implementation and whenever a provider release/deprecation materially affects a route.
- A tool capability may refine routing thresholds, but does **not** reopen the four-orchestra / seven-artifact architecture by itself.
- Provider/model names belong in a versioned capability registry and Generation Manifest, not in semantic Shot Specs as permanent truth.

Evidence labels:
- `OFFICIAL_CURRENT` — current official documentation checked.
- `PREVIEW` — official but explicitly preview/subject to change.
- `DEPRECATED` — official deprecation/shutdown notice.
- `LOCAL_UNVERIFIED` — must be tested in the actual project environment before relying on it.

---

# 2. Blender — Deterministic Spatial Backbone

## Verified capabilities

### Python animation control — `OFFICIAL_CURRENT`
Blender's Python API supports direct animation/keyframe authoring (`keyframe_insert`) as well as lower-level animation curve/action construction.

Implication:
- deterministic camera/object transforms are technically compatible with the planned Blender Specialist contract;
- C01–C12 / closure camera grammar does not require a paid camera SaaS to exist;
- exact spatial motion remains a Blender-owned capability when topology/orientation is explanatory evidence.

### Headless/background execution — `OFFICIAL_CURRENT`
Blender's command-line manual documents background/UI-less execution and render commands.

Implication:
- the AskAnything headless subprocess pattern remains a valid implementation reference;
- future runtime can execute scene build/previs/render jobs without assuming an interactive Blender desktop session.

## Intentionally NOT locked

- exact Blender version / LTS line
- render engine defaults
- scene Python package/module layout
- geometry-node vs direct mesh API default
- Eevee vs Cycles production policy
- render farm/cloud strategy

These require actual prototype timing/readability measurements.

## Phase 1 verification needed

1. installed Blender version and Python API compatibility
2. one G1 Venetian foundation procedural scene
3. deterministic camera replay across repeated runs
4. background render exit codes/log capture
5. render/previs duration and memory footprint

Verdict: **Architecture supported; runtime performance unverified.**

---

# 3. Google Video Generation — Capability Router, Not Veo Lock

## Gemini Omni Flash — `PREVIEW`

Official Gemini video documentation currently recommends Gemini Omni Flash as the default video-generation model for general workflows.

Current documented profile:
- model: `gemini-omni-flash-preview`
- input: text, image and short video for editing
- output: video
- output duration: approximately 3–10 seconds
- output: 720p / 24 FPS in the current model card
- supports conversational/natural-language editing through the Interactions API
- designed for fast generation/editing and multimodal continuity

### Civilization X-Ray fit
Candidate for:
- cinematic context shots
- atmosphere/humans/activity
- fast visual iteration
- natural-language refinement where exact topology is not evidence

Not factual authority for:
- exact foundation topology
- engineering dimensions
- deterministic camera transforms
- exact component placement

## Veo 3.1 — `PREVIEW`

Current official docs reserve Veo 3.1 for specific advanced controls such as:
- scene/video extension
- first/last-frame control
- frame-specific generation
- image-based direction/reference guidance
- native audio
- higher-resolution generation depending on model variant

Current documented variants include Standard / Fast / Lite preview model IDs.

### Civilization X-Ray fit
Prefer Veo 3.1 when a Shot Spec genuinely benefits from:
- explicit end-frame continuity bridge
- extension of an existing generated clip
- first→last state control
- reference-guided cinematic reconstruction

Do not select Veo merely because the role is historically named `Veo Cinematic Camera Specialist`.
The role is a **capability responsibility**, while the Google Video Adapter selects the current suitable model.

## Current cost snapshot — volatile

Official Gemini API pricing checked on 2026-08-15 shows materially different video-generation costs by model/variant. This validates the existing budget router and makes model choice a per-shot capability/cost decision.

Do not copy these prices into permanent business logic. Store them in a dated provider registry and refresh before each implementation/release cycle.

## Deprecated assumptions

- Veo 2 and Veo 3.0 must not be introduced as new default dependencies; official docs report shutdown/deprecation in 2026.
- AskAnything's stored model chains/prices are implementation references, **not current truth**.

## Phase 1 verification needed

Run the same non-factual cinematic test shot through available candidates and measure:
- prompt adherence
- continuity drift
- first/last frame adherence where supported
- generation latency
- retry/failure rate
- usable-output ratio
- effective selected-output cost, including rejected attempts

Verdict: **Keep capability adapter. Do not lock Veo as universal default.**

---

# 4. TTS / Narration

## Google Cloud Text-to-Speech — `OFFICIAL_CURRENT`

Official Cloud TTS supports:
- text or SSML input
- common audio outputs
- configurable voice selection and speech parameters
- Korean (`ko-KR`) voices across multiple voice families, including current premium/HD options in the supported-voices registry

### Fit
Strong baseline candidate for:
- stable Korean narration
- explicit pronunciation/SSML control
- repeatable production where provider stability matters more than generative performance variation

## Gemini TTS — `PREVIEW`

Official Gemini TTS documentation positions it for exact text recitation with natural-language control over:
- style
- accent
- pace
- tone
- single-speaker and multi-speaker performance

Google explicitly describes podcast/audiobook-style workflows as a target class.

### Fit
Strong audition candidate for:
- expressive documentary narration
- director-style performance instructions
- nuanced pace/emphasis control

### Caveat
Current Gemini TTS documentation/model listings are preview-oriented and can change. Do not bind the Voice Bible to one preview model ID.

## Selected validation policy

Do **not** choose the final TTS provider on documentation alone.
Before implementation lock, A/B at least:
- one stable Cloud TTS Korean voice
- one Gemini TTS candidate

Use the same 60–90 second narration sample and score:
1. Korean pronunciation
2. technical terms / foreign names
3. long-sentence prosody
4. calm authority vs trailer-like overacting
5. controllability
6. consistency across regeneration
7. editability / segment regeneration
8. cost and latency

Verdict: **TTS contract complete; provider remains intentionally open.**

---

# 5. Music Generation — Lyria 3 as Candidate, Not Timeline Authority

## Lyria 3 — `PREVIEW`

Current official Gemini docs expose:
- `lyria-3-clip-preview` — fixed 30-second clip generation
- `lyria-3-pro-preview` — longer song generation, duration influenced by prompt
- text/image-conditioned generation
- instrumental-only prompting
- musical structure/energy/timing instructions in prompts

Important official limitations:
- generation is single-turn; iterative multi-turn editing of an existing generated track is not currently supported
- repeated calls may produce different results even with the same prompt
- generated audio includes SynthID watermarking

### Documentation discrepancy
Official current Google pages are not fully consistent about advertised output sample rate (guide/model pages differ). Therefore Civilization X-Ray must **not** make source sample rate a semantic contract.

Post must normalize accepted music assets to the project delivery format.

## Architecture implication

This reinforces the existing Audio/Post design:

`Audio Beat Map → cue request → candidate generation → human/QA selection → edit/trim/loop/duck in Post`

Lyria or any other generator must **not** own the final timeline.

Because generation is non-deterministic and single-turn:
- store exact prompt/version and provider/model version;
- treat each candidate as immutable provenance;
- retry only with a recorded causal prompt/constraint change;
- track rejected-generation cost;
- use the editor/post system for exact timing rather than expecting deterministic regenerated music.

## Phase 1 validation needed

Compare at least three cue strategies on one pilot segment:
- sparse
- balanced
- dense

For generated music, test:
- instrumental-only compliance
- narration masking risk
- loop/edit seam quality
- cue-to-beat usefulness
- regeneration consistency
- rights/terms/provenance handling

Verdict: **Viable candidate. No provider lock.**

---

# 6. Capability Decisions Locked by This Validation

## Keep
1. Blender remains deterministic spatial/camera backbone.
2. Google video stays behind a capability adapter.
3. `Veo Specialist` is a responsibility label, not a permanent model selection.
4. TTS provider stays swappable behind the Voice Pack contract.
5. Music provider stays swappable behind Audio Beat Map / cue contracts.
6. Provider/version/cost data is dated registry state, not project constitution.
7. Final timeline authority stays with Post, not TTS/music/video generators.

## Do not add
- provider-specific fifth orchestra
- Veo-only pipeline
- Lyria-only music architecture
- Gemini-only TTS architecture
- provider model IDs in core artifact semantics

---

# 7. New Blind Spots Found

## B1 — Role naming can accidentally create model lock-in
`Veo Cinematic Camera Specialist` can be misread as “always call Veo”.

Mitigation:
- preserve the existing role for continuity, but explicitly define it as generative cinematic-video capability;
- actual model selection belongs to Google Video Adapter / capability registry.

## B2 — Preview-to-GA churn is now a major operational variable
Current Google video, TTS and music options include preview models.

Mitigation:
- model/version must be recorded per generation;
- registry refreshed before implementation;
- no core artifact depends on preview-only semantics unless a fallback exists.

## B3 — Provider docs can disagree with each other
Example: Lyria output-format/sample-rate descriptions can differ between current official pages.

Mitigation:
- semantic contracts describe what the pipeline needs, not undocumented provider assumptions;
- normalize technical media properties during ingestion/post;
- conflicting provider documentation is marked `REVIEW`, not silently resolved.

## B4 — Generated native audio is not automatically useful audio
Video models can generate native sound, but the episode Audio/Post system already has narration/music/SFX truth and rights responsibilities.

Mitigation:
- native generated audio is a candidate asset layer;
- it does not bypass Sound Truth / rights / mix gates.

---

# 8. Final Verdict

- Blender deterministic route: **SUPPORTED BY OFFICIAL CAPABILITIES**
- Google video adapter strategy: **SUPPORTED / strengthened**
- Veo universal-default assumption: **REJECTED**
- Korean TTS feasibility: **SUPPORTED**
- final TTS provider: **OPEN — A/B REQUIRED**
- generated music feasibility: **SUPPORTED AS CANDIDATE**
- final music provider: **OPEN — PILOT REQUIRED**
- architecture change required: **NO**
- implementation code authorized: **NO**

Next empirical work:
1. actual reference frame+transcript corpus when direct media access is available;
2. implementation-time tool auditions using fixed benchmark inputs;
3. refresh this registry immediately before Phase 1 implementation planning.
