# AniJam Capability Validation — 2026-08-22

Status: **EMPIRICAL NO-CODE TOOL VALIDATION**  
Architecture effect: **no new orchestra / no new core artifact / no implementation code**  
Candidate role: **optional generative cinematic workbench**

## 1. Why This Validation Exists

AniJam was identified as a possible production tool for AI-assisted animation/video creation. The question is not whether it is generally useful, but whether it fits the already-closed Civilization X-Ray architecture without creating a second director, second story system, or vendor lock.

This document therefore asks:

1. What does AniJam currently claim to do?
2. Which capabilities are useful to Civilization X-Ray?
3. Which capabilities would conflict with existing authority boundaries?
4. Can AniJam be a runtime dependency today?
5. What evidence would be required before promotion from optional workbench to automated route?

## 2. Source Policy

Primary sources checked on 2026-08-22:

- AniJam official home / product pages
- AniJam official AI Animation Agent page
- AniJam official Script-to-Animation page
- AniJam official Text-to-Animation / animation-generator pages
- AniJam official pricing page
- AniJam official terms page

Evidence labels:

- `OFFICIAL_CLAIM` — capability described by AniJam on its own current site.
- `COMMERCIAL_CURRENT` — current pricing/plan information visible on AniJam official pages.
- `NOT_VERIFIED` — not established from public official documentation reviewed in this pass.
- `LOCAL_AUDITION_REQUIRED` — must be tested with Civilization X-Ray benchmark inputs.

Vendor self-description is not the same as independent quality evidence. Claims such as consistency, precision or output quality remain `LOCAL_AUDITION_REQUIRED` until measured.

---

# 3. Current Official Capability Snapshot

## A. Script / Idea / Image / Audio → animation

AniJam officially presents workflows that can begin from:
- text / idea;
- a full script;
- images / characters;
- audio.

Verdict: `OFFICIAL_CLAIM`.

Civilization X-Ray relevance:
- useful for rapid cinematic candidate generation;
- especially useful for historical activity, people, atmosphere and non-factual explanatory interludes;
- not a replacement for Evidence Pack, Story Pack or Visual Plan.

## B. Automatic scene / shot breakdown

AniJam officially describes automatic breakdown of a script into scenes/shots, with character placement, action description and camera direction.

Verdict: `OFFICIAL_CLAIM`, but **authority-conflict risk**.

Civilization X-Ray rule:
> AniJam must not become the canonical shot planner.

The canonical chain remains:

`Evidence Pack → Story Pack → Visual Plan → Production Pack`

AniJam may receive an already-approved Visual Work Order and create one or more candidate executions. If a whole script is supplied for exploration, AniJam's breakdown is `NON-CANON / IDEA ONLY` until manually mapped back to approved Visual Plan rows.

## C. Character / style consistency

AniJam advertises character consistency, style preservation/custom style workflows and multi-scene continuity.

Verdict: `OFFICIAL_CLAIM / LOCAL_AUDITION_REQUIRED`.

Potential fit:
- recurring historical worker silhouettes;
- a recurring guide/mascot if the channel later uses one;
- consistent reconstruction aesthetic across several cinematic shots;
- consistent non-authoritative people/costume/atmosphere layer.

Do not infer:
- factual costume accuracy;
- factual machinery geometry;
- structural correctness;
- deterministic cross-shot identity without testing.

## D. Motion / camera direction

AniJam advertises prompt-directed motion, camera angles and reference-video-based motion control.

Verdict: `OFFICIAL_CLAIM / LOCAL_AUDITION_REQUIRED`.

Project boundary:
- valid for cinematic movement;
- invalid as spatial-truth authority where camera motion teaches exact geometry;
- Blender remains owner of registered deterministic camera paths and topology-sensitive explanatory movement.

## E. Lip sync / voice / timeline editor

AniJam advertises built-in lip sync, multilingual voice generation/uploaded audio and a timeline/scene editor.

Verdict: `OFFICIAL_CLAIM`.

Project boundary:
- useful as shot-local production convenience;
- does not replace the Audio/Post Orchestra;
- does not replace Voice Bible / pronunciation QA;
- does not own final narration timing, music, SFX truth, captions or final mix.

## F. Multi-model ecosystem

AniJam's official site lists partnerships/integrations with multiple generative providers including Kling, Wan, Hailuo, Luma, PixVerse, Runway, Google Veo, Sora, Vidu and others.

Verdict: `OFFICIAL_CLAIM`.

This is strategically useful because it may reduce manual app switching during early auditions. However:

- availability can change;
- a listed partner does not prove every model/variant is available for every workflow;
- exact underlying model/version used for each output must be inspected during local audition;
- model provenance must never be guessed.

## G. Pricing / export

Current official pricing shows paid tiers with monthly credits, concurrent-task limits and export capability. Paid-plan features include watermark removal and higher-resolution output depending on plan.

Verdict: `COMMERCIAL_CURRENT / VOLATILE`.

Project rule:
- pricing belongs in dated provider/tool registry state;
- never hard-code current prices or plan names into project constitution;
- effective selected-output cost must include failed/rejected attempts.

---

# 4. Critical Unknowns

## U1 — Public automation API

A stable public developer API suitable for Civilization X-Ray runtime automation was **not verified** from the public official pages reviewed in this pass.

Status: `NOT_VERIFIED`.

Consequence:
AniJam cannot currently be promoted to a required automated harness dependency.

Allowed status:
`MANUAL_OR_ASSISTED_WORKBENCH`.

## U2 — Underlying model/version provenance per output

The reviewed public pages do not establish that every exported shot exposes a machine-readable underlying provider/model/version identity.

Status: `NOT_VERIFIED`.

Consequence:
A selected output must record whatever AniJam exposes. If the underlying model is unavailable, record `NOT_EXPOSED`; do not invent it.

## U3 — Deterministic regeneration

AniJam does not establish deterministic shot regeneration for our use case.

Status: `NOT_VERIFIED`.

Consequence:
Treat generated candidates as immutable attempt artifacts. Preserve inputs and selected output rather than assuming exact regeneration.

## U4 — Rights / data-use details for each underlying model

AniJam terms govern use of AniJam, but an aggregator route can complicate the provenance chain when underlying models/providers differ.

Status: `REVIEW_REQUIRED`.

Consequence:
Commercial-use approval must include:
- AniJam plan/terms review;
- input/reference rights;
- any exposed underlying-provider conditions relevant to the chosen workflow;
- YouTube synthetic-content disclosure review where applicable.

---

# 5. Four Integration Alternatives

| Option | Description | Strength | Risk | Verdict |
|---|---|---|---|---|
| A. Direct providers only | Civilization X-Ray calls Google/other video providers directly | strongest provenance/automation/control | more integration work, more provider switching | KEEP as core automated path |
| B. AniJam-first | Most generative cinematic production happens in AniJam | fast creative workflow, multi-model convenience | shadow director, weak automation/provenance unknowns, tool lock | REJECT as core architecture |
| C. AniJam only for exploration | Use AniJam only for visual ideation, never final assets | very safe authority boundary | loses much of workbench value | KEEP as fallback-low-risk mode |
| D. Hybrid Workbench | Direct-provider path remains core; AniJam may create final candidate cinematic assets under strict work-order/provenance gates | speed + multi-model audition without architecture lock | dual-route management | **SELECTED** |

Selected:
> **D. Hybrid Workbench**

Reason:
It preserves the existing provider-adapter architecture while allowing AniJam to reduce manual creative overhead during the no-code / supervised-production stage.

---

# 6. Selected Role in Civilization X-Ray

AniJam is classified as:

> **Optional Generative Cinematic Workbench**

It lives under the existing `Generative Cinematic Video` responsibility.

It is NOT:
- Project Orchestrator;
- Video Director;
- Narrative Architect;
- Script↔Visual Architect;
- Spatial authority;
- factual reviewer;
- final post editor;
- provider registry source of truth.

Conceptual placement:

```text
Project Orchestrator
      ↓
Video Director
      ├─ Blender Spatial & Camera Specialist
      ├─ 2D Motion / Compositing
      └─ Generative Cinematic Video capability
             ├─ Direct Provider Adapter(s)
             └─ AniJam Assisted Workbench [optional]
                    └─ underlying model(s), if exposed
      ↓
Independent Visual QA
      ↓
Audio/Post final timeline
```

No fifth orchestra, no new agent and no eighth artifact are created.

---

# 7. Authority Firewall

## Story authority
AniJam may not change:
- central question;
- claim order;
- qualifier language;
- reveal timing that changes factual meaning;
- narration truth.

Owner: `Story Pack`.

## Visual-plan authority
AniJam's automatic scene breakdown is not canonical.

Owner: `Visual Plan`.

AniJam receives:
- `shot/work_order_id`;
- visual objective;
- approved action;
- start/end semantic state;
- continuity anchors;
- truth/reconstruction class;
- allowed variation;
- forbidden changes.

## Spatial authority
AniJam may not invent canonical:
- topology;
- dimensions;
- component position;
- structural path;
- map route;
- section relationships.

Owner: `Spatial / Asset Bible`.

## Audio authority
AniJam-generated voice/lip sync is a candidate layer only.

Owner: `Audio & Post`.

## Final timeline authority
AniJam's editor can prepare/select candidates, but the canonical final timeline remains the Post system.

---

# 8. Production Pack Provenance Contract for Workbench Outputs

For an AniJam-created production attempt, record conceptually:

- `execution_route = WORKBENCH_ASSISTED`
- `workbench = ANIJAM`
- `workbench_project_ref`
- `workbench_scene_ref` if available
- `workbench_version_or_snapshot_date`
- `underlying_provider` if exposed, else `NOT_EXPOSED`
- `underlying_model_version` if exposed, else `NOT_EXPOSED`
- `input_prompt_or_instruction_hash`
- `input_reference_binding_ids[]`
- `input_asset_versions[]`
- `export_timestamp`
- `export_settings`
- `selected_output_asset_id`
- `reproducibility_level = FULL | PARTIAL_WORKBENCH | INSUFFICIENT`
- `rights_review_state`
- `synthetic_media_disclosure_class`
- `qa_verdict_ref`

### Selection rule

`PARTIAL_WORKBENCH` provenance may be acceptable only for non-factual cinematic/reconstruction layers when:
- tool identity is known;
- inputs and output are preserved;
- rights/disclosure review passes;
- Visual QA passes;
- output does not claim canonical spatial truth.

`INSUFFICIENT` provenance is not selectable for final publication.

This is a workbench-specific interpretation of the existing P6 provenance requirement, not a new physical artifact.

---

# 9. Routing Rules

## Prefer Blender / 2D when
- topology is evidence;
- exact orientation matters;
- cutaway/explode/reassembly proves the mechanism;
- dimensions/route/forces are explanatory truth;
- repeated camera registration matters.

## Prefer Direct Provider Adapter when
- programmatic automation is required;
- exact provider/model selection matters;
- retry/cost metrics must be machine-captured;
- first/last-frame or provider-specific controls are essential;
- high provenance/reproducibility is required.

## Consider AniJam Workbench when
- multiple cinematic candidates need rapid audition;
- multi-scene character/style consistency is valuable;
- historical activity/people/atmosphere is central to the sequence but not factual topology;
- a reference image/style needs to carry across several shots;
- manual supervision is acceptable;
- reducing app-switching has real value.

## Reject AniJam route when
- exact engineering geometry is the proof;
- a proprietary/unknown model would make provenance insufficient for the intended truth claim;
- the workbench attempts to rewrite the approved Story/Visual Plan;
- output terms/rights cannot be resolved;
- cost cannot be measured well enough to satisfy the episode budget gate.

---

# 10. Input Compiler Rule

Do NOT default to sending the full Story Pack or full narration script into AniJam.

Default context packet:

1. approved visual work order;
2. linked claim summary/qualifier only as needed;
3. reconstruction/truth class;
4. hard continuity locks and reference bindings;
5. start/end visual state;
6. camera intent, not uncontrolled restaging authority;
7. forbidden changes;
8. output format/duration intent.

Principle:
> **Deep Blackboard, small Workbench Prompt.**

Whole-script mode is allowed only for non-canonical exploration and must be clearly labeled `EXPLORATORY / NON-CANON`.

---

# 11. Retry / Failure Rules

No blind retry.

When an AniJam attempt fails, classify:
- character/style drift;
- geometry hallucination;
- action failure;
- camera failure;
- temporal continuity failure;
- text/lip-sync failure;
- output artifact failure;
- cost/credit failure;
- rights/provenance failure.

Before retry, change at least one causal input:
- prompt/action constraint;
- reference image;
- scene segmentation;
- underlying model selection if exposed;
- duration;
- camera request;
- execution route.

Escalation:
- repeated topology drift → Blender/2D;
- repeated character consistency failure → stronger reference lock / direct provider / manual composite;
- provenance failure → direct provider route;
- credit/cost ceiling → cheaper valid route or stop;
- scene-breakdown conflict → restore approved Visual Plan, never accept workbench structure silently.

---

# 12. Paper Test — Venice Historical Activity

Candidate work order:
`historical pile-driving activity / atmosphere`

Truth role:
- R2/R3 reconstruction;
- not foundation geometry authority.

### Inputs
- approved historical-activity objective;
- representative costume/activity references with rights/provenance;
- spatial anchor still from Blender if useful;
- camera intent;
- explicit prohibition on changing foundation topology.

### AniJam may control
- human motion;
- atmospheric detail;
- cinematic framing variation;
- scene-local timing;
- style/character continuity between reconstruction shots.

### AniJam may not control
- pile geometry as factual truth;
- exact foundation section;
- structural relationship;
- claim wording;
- final timeline.

### Fallback
`AniJam → direct generative provider → controlled still/composite → omit cinematic layer`

The episode remains explainable without AniJam.

Paper verdict: **PASS as optional workbench route**.

---

# 13. Blind-Spot / Pre-Mortem

Assume the AniJam integration failed after three months. Likely causes:

## F1 — Shadow Director
AniJam reinterprets the full script and the team starts accepting its scene breakdown because it is convenient.

Prevention:
- work-order input by default;
- non-canon label for whole-script exploration;
- Visual Plan owns shot authority.

## F2 — Aggregator opacity
A visually good shot cannot be traced to an underlying model/version.

Prevention:
- record `NOT_EXPOSED`, never guess;
- restrict opaque output to non-factual cinematic role;
- direct-provider route for high-provenance requirements.

## F3 — Double editor problem
AniJam timeline and Post timeline diverge, creating version confusion.

Prevention:
- AniJam timeline = candidate/preassembly only;
- Production Pack records selected exports;
- Post owns canonical final timeline.

## F4 — Credit sink
Multi-model experimentation consumes credits without improving usable-output ratio.

Prevention:
- attempt budget;
- selected-output cost metric;
- fixed audition benchmark;
- stop after ceiling.

## F5 — Factual visual drift hidden by cinematic quality
Historical scenes look convincing enough that viewers interpret invented details as documentary truth.

Prevention:
- reconstruction class carried into Production Pack and release disclosure;
- no canonical geometry from workbench output;
- Fact/Rights/Visual QA remain independent.

## F6 — Tool lock-in
Scene assets become trapped inside AniJam project state.

Prevention:
- export selected outputs and reference assets into project-controlled storage;
- preserve prompts/instructions outside tool where possible;
- episode must remain producible through direct-provider/still fallback.

---

# 14. Promotion Gates

## Current level
`W0 — OPTIONAL MANUAL/ASSISTED WORKBENCH`

## Promote to W1 — STANDARD SUPERVISED WORKBENCH only if audition proves
- usable-output ratio meets quality bar;
- continuity benefit is measurable;
- cost is acceptable;
- export/provenance workflow is reliable;
- rights/disclosure handling is clear;
- no authority confusion.

## Promote to W2 — AUTOMATABLE ROUTE only if additionally verified
- supported automation/API contract;
- authentication/security model;
- stable job lifecycle;
- machine-readable output identity;
- sufficient model/tool provenance;
- retry/error semantics;
- quotas/cost observability.

Until then, do not write AniJam runtime integration code.

---

# 15. Final Verdict

- AniJam as fifth orchestra: **REJECT**
- AniJam as new physical agent: **REJECT**
- AniJam as Blender replacement: **REJECT**
- AniJam as final post/timeline authority: **REJECT**
- AniJam as optional generative cinematic workbench: **PASS FOR SUPERVISED AUDITION**
- direct-provider adapters remain necessary: **YES**
- public runtime API: **NOT VERIFIED**
- architecture reopening required: **NO**
- implementation authorized: **NO**

Selected design:
> **Direct-provider-capable Hybrid Workbench: Blender/2D own explanatory truth; AniJam may accelerate supervised cinematic generation without owning story, spatial truth, provenance authority or final edit.**
