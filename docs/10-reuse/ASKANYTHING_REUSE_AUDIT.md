# AskAnything → Civilization X-Ray Reuse Audit

Status: **Design-only reuse decision — no implementation code copied**

Source repository: `storm-credit/askanything_video_generator` (`main` inspected 2026-08-14)

## Executive Decision

Civilization X-Ray should reuse **operational patterns and selected provider infrastructure** from AskAnything rather than reimplementing Veo integration from zero.

However, it must **not copy the AskAnything Shorts-specific video policy wholesale**.

Selected rule:

> Reuse transport, authentication, polling, retry, quota, caching and media-normalization patterns. Rebuild shot routing, camera intent, continuity, provenance and QA around Civilization X-Ray's long-form artifact contracts.

---

# 1. Reuse Classification

## A — Strong reuse / adapt into provider layer

### A1. `modules/video/veo.py`
Useful patterns:
- `google-genai` video operation lifecycle
- image MIME handling
- AI Studio / Vertex client integration point
- asynchronous operation polling
- adaptive poll interval
- timeout handling
- quota/key failure handling
- model-chain fallback mechanism
- generated-video bytes/URI download handling
- atomic temp-file → final-file replacement
- post-download media normalization
- usage recording

Decision: **Reuse architecture and tested behavior; do not copy public interface unchanged.**

Why interface must change:
- current input is `image_path + prompt + cut index + topic_folder`
- output naming is cut-index based
- duration is fixed to 8 seconds
- aspect ratio is fixed to 9:16
- it assumes image-to-video as the primary shape

Civilization X-Ray needs a typed Shot/Generation Manifest contract instead.

---

### A2. `modules/utils/gemini_client.py`
Useful patterns:
- `GEMINI_BACKEND=ai_studio | vertex_ai`
- a single Gemini client factory
- API-key mode and Vertex service-account mode
- multiple service-account discovery
- blocked-SA cooldown
- thread-safe rotation
- runtime backend state

Decision: **High-value reuse candidate.**

Civilization rule:
- hide credentials behind a Google provider/client boundary
- specialist agents never manipulate raw credentials
- Project Orchestrator may observe provider health, not secret values

---

### A3. model-chain concept from `modules/utils/models.py`
Useful pattern:
- provider model IDs are centralized
- normal vs hero-quality model ordering can differ
- service/model labels are separated from business logic

Decision: **Reuse the registry pattern, replace the selection semantics.**

Civilization X-Ray model profiles should be capability-oriented, for example conceptually:
- `cinematic_fast`
- `cinematic_quality`
- `reference_consistency`
- `start_end_frame`
- `extension`

Exact profiles and model IDs are implementation-time decisions.

Do not treat AskAnything's 2026-03 rate-limit/price comments as current source of truth. Tool capability, pricing and quota metadata must be versioned and re-verified when implementation begins.

---

## B — Reuse ideas, rewrite policy

### B1. `modules/orchestrator/agents/video.py`
Very useful operational ideas:
- do not generate every cut with expensive video
- distinguish important cuts from normal cuts
- cache/reuse an existing output
- bounded video-generation concurrency
- graceful fallback when expensive generation is unavailable

Decision: **Reuse these principles, reject the Shorts-specific scoring algorithm.**

Do NOT carry over as primary policy:
- SHOCK/WONDER/REVEAL emotion-tag scoring
- WHO_WINS/IF/COUNTDOWN/SCALE format heuristics
- “hero-only = 1–2 generated clips” as a hard rule
- Ken Burns as universal fallback

Replacement routing authority:

`Script ↔ Visual Map → Video Director → Shot Spec → Render Router`

The Video Director selects Blender / Veo / 2D / still-composite by explanatory objective and spatial truth requirements.

---

### B2. `modules/video/engines.py`
Useful patterns:
- provider adapter boundary
- availability preflight
- preferred engine vs fallback providers
- provider-specific retry isolation
- recording which engine actually produced an output

Decision: **Reuse adapter/router concept, not silent cross-provider substitution.**

Civilization rule:
- fallback cannot silently change visual truth or camera contract
- if Veo fails, another generator may be tried only when the Shot Spec allows a compatible capability fallback
- otherwise route back to Video Director / Project Orchestrator
- actual provider/model/prompt version must be written to persistent Generation Manifest metadata, not only an in-memory path map

---

### B3. media normalization from `_reencode_for_remotion`
Useful pattern:
- normalize generated media before assembly
- avoid discovering codec incompatibility at final edit

Decision: **Reuse as a generic Media Normalization Gate.**

Do not bind the design permanently to Remotion. If Remotion is selected for Phase 1 assembly, preserve its compatibility profile; otherwise define the selected post pipeline's canonical mezzanine/delivery format.

---

## C — Do not copy directly

### C1. `build_video_generation_prompt()` Shorts camera grammar
Current AskAnything prompt construction is based on:
- emotion tags
- format tags
- generic `dynamic/gentle/static/cinematic` modifiers
- “one memorable motion beat”

This is useful for Shorts, but too weak for Civilization X-Ray's explanatory camera language.

Replacement input must come from Shot Spec fields such as:
- shot purpose
- subject/component ID
- entry state
- exit state
- camera intent
- framing/lens intent
- movement path
- allowed subject motion
- forbidden geometry drift
- continuity anchors
- reconstruction level
- scale treatment
- transition relationship

The phrase-level principle “preserve the exact subject and scene from the source image” is still useful when reference preservation is required.

---

### C2. fixed `durationSeconds=8` and `aspectRatio=9:16`
Reject as Civilization defaults.

Long-form requires:
- 16:9 baseline
- per-shot duration intent
- possible still/2D/Blender shots that last longer than a generated clip
- generated clip extension/assembly when supported and justified

Provider limits must not leak upward into Story Pack structure.

---

### C3. current BlenderAgent implementation
AskAnything already contains a Blender Agent, which proves the subprocess execution pattern works, but the implementation is preset-driven for planet/star comparisons.

Useful:
- locate Blender binary
- run background Python scripts
- capture return code/stdout/stderr
- timeout/fallback handling

Not reusable as Civilization modeling logic:
- keyword matching topic → preset
- solar-system / giant-star preset map
- one fixed script family

Civilization's Blender Specialist must consume a Spatial / Asset Bible + Shot Spec and eventually produce deterministic geometry/camera manifests.

---

# 2. Critical New Contract for Civilization X-Ray

Future implementation should place an adapter between the Veo Specialist and Google SDK.

Conceptual request contract (`Veo Shot Request`):
- episode_id
- shot_id
- shot_spec_version
- narrative purpose
- source frame / source asset IDs
- optional end-frame target
- optional approved reference asset IDs
- prompt payload
- camera intent
- duration intent
- aspect ratio
- continuity hard locks
- reconstruction level
- scale treatment
- model/capability profile
- retry budget
- cost ceiling
- fallback policy

Conceptual response (`Generation Manifest`):
- episode_id / shot_id
- provider
- model ID
- backend mode
- operation/run ID if available
- prompt version
- input asset versions
- generated asset path/ID
- attempt count
- elapsed time
- normalized-media status
- failure signatures encountered
- estimated/recorded cost
- provenance metadata
- QA state: `UNREVIEWED | PASS | REVISE | REJECT`

---

# 3. Quota / Credential Blind Spot

AskAnything currently contains more than one quota/key-management layer:
- key rotation and exhaustion handling used by Veo generation
- Gemini/Vertex client SA rotation
- a project-level quota manager

Do **not** copy all of them into Civilization X-Ray as independent competing managers.

Phase 1 should define one authoritative `Provider Health / Quota Service` with adapters for:
- AI Studio API keys
- Vertex projects/service accounts
- provider/model availability
- cooldown / rate-limit state
- budget ceilings

This state belongs to infrastructure/shared services, not the Veo Camera Specialist prompt.

---

# 4. Cost Tracking Reuse

AskAnything already has a substantial cost tracker.

Reuse concepts:
- per-provider/model accounting
- daily/episode aggregation
- currency display
- threshold alerting
- cost metadata connected to selected model

Do not reuse hard-coded price tables as current truth.

Civilization X-Ray should additionally track cost by:
- episode
- orchestra/stage
- shot
- retry cause
- accepted vs rejected output
- reusable asset vs one-off asset

The key metric is not only total spend but **wasted expensive generation discovered after a missing upstream gate**.

---

# 5. Cache / Idempotency Reuse

AskAnything's existing-video reuse is worth preserving, but Civilization requires stronger cache keys.

Do not decide reuse only from `veo3_cut_XX.mp4` existence.

A generated asset is reusable only if its manifest matches at least:
- shot_spec_version
- provider/model capability profile
- input asset versions
- prompt version
- relevant continuity locks

If any upstream hard dependency changes, mark the output stale rather than silently reusing it.

---

# 6. Failure Handling Reuse

Keep:
- bounded retries
- adaptive polling
- rate-limit-specific handling
- transient failure distinction
- model/provider fallback boundary
- timeout
- failure logging

Add:
- causal retry requirement
- failure signature memory
- retry budget per shot
- `REVISE_UPSTREAM` outcome when generation cannot satisfy the Shot Spec
- Visual QA verdict before clip acceptance

A repeated generation call with unchanged causal inputs is not considered a valid recovery strategy.

---

# 7. Recommended Phase 1 Extraction Boundary

When implementation is explicitly authorized, do **not** import the whole AskAnything package.

Preferred extraction sequence:

1. Google client/provider boundary
2. Veo operation lifecycle
3. provider health/quota abstraction
4. model capability registry
5. media normalization
6. persistent Generation Manifest
7. bounded concurrency/cache
8. Video Director + Veo Specialist adapter
9. QA acceptance loop

Only then connect it to the full episode orchestration.

---

# 8. Reuse Matrix

| Existing asset | Reuse level | Civilization treatment |
|---|---|---|
| `modules/video/veo.py` | HIGH | Extract SDK/poll/download/retry core behind adapter |
| `gemini_client.py` | HIGH | Adapt as Google client/provider factory |
| `models.py` model chain | MED-HIGH | Replace hero/fast semantics with capability profiles |
| `video.py` agent | MEDIUM | Keep cache/concurrency/cost discipline; replace selection logic |
| `engines.py` | MEDIUM | Keep adapter pattern; prohibit uncontrolled silent fallback |
| `constants.py` video prompt | LOW | Replace Shorts grammar with Shot Spec grammar |
| `_reencode_for_remotion` | MEDIUM | Generalize into media normalization gate |
| `cost_tracker.py` | MED-HIGH | Reuse accounting pattern; refresh pricing source + add shot/retry attribution |
| `project_quota.py` | MEDIUM | Consolidate with other key/quota layers; do not duplicate managers |
| existing BlenderAgent | LOW-MED | Reuse subprocess execution pattern only; replace preset modeling logic |

---

# 9. Decision

**Yes: AskAnything materially reduces Phase 1 implementation risk.**

It already proves several hard operational pieces:
- Google video generation request lifecycle
- credential/backend switching
- quota/retry behavior
- output download/normalization
- selective expensive generation
- provider routing
- Blender headless execution pattern
- cost accounting

But Civilization X-Ray's differentiator is not these transport mechanics.

Its differentiator remains:

> `Evidence → Script → Spatial Truth → Shot Contract → Blender/Veo Route → Independent QA → Long-form Post`

Therefore the reuse strategy is **extract infrastructure, not inherit Shorts editorial policy**.
