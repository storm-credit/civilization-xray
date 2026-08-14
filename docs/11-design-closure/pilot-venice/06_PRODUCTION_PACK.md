# VX-PILOT-001 — Production Pack

Artifact: P6 Production Pack  
Version: v1  
Status: PAPER_PRODUCTION_READY  
Inputs: Visual Plan v1 + Spatial / Asset Bible v1  
Owner: Video Director / Post Director coordination  

No media is generated in Closure 0.6. This pack tests whether approved specs are sufficient to dispatch work without hidden interpretation.

---

# Production Strategy

Principle: cheap reasoning first, expensive pixels last.

Paper route:
1. 2D storyboard/blockout for all 15 shots
2. one reusable Blender foundation module
3. deterministic camera/previs for spatial sequence
4. only 1–3 generative cinematic clips if they add value
5. rough assembly with scratch narration
6. audio beat map / temp music
7. QA before any high-cost reruns

---

# Asset/Scene Build Orders

## PROD-BL-01 — Venice Representative Foundation Scene
Covers: SH02, SH04, SH05, SH06, SH07, SH08, SH12, SH13, part SH14
Inputs:
- Spatial Bible v1 components CMP-01–CMP-09
- canonical section
- hard locks
- CX-CAM rigs

Deliverable concept:
- one `.blend` scene asset later
- G0 blockout first
- G1 explanatory geometry second
- named component collections/IDs
- registered camera rigs
- section/explode/reassembly states
- no decorative hero polish before previs PASS

Gate before G2:
- all hard spatial QA passes at G1

---

## PROD-2D-01 — Wrong Intuition Diagram
Covers: SH03
Deliverable:
- simple non-photoreal “deep pile to hard layer?” mental model
- clearly marked as intuition, not Venice evidence

---

## PROD-2D-02 — Preservation / Evidence Graphics
Covers: SH10, SH11
Deliverable:
- waterlogged wood preservation variability concept
- named-case depth note for Santa Maria Maggiore
- multiple-species evidence card
- Rialto case card

Rule:
- no source figure copied unless rights cleared
- redraw concepts from facts, not copyrighted figure styling

---

## PROD-VE-01 — Historical Atmosphere Clip
Covers: SH09
Purpose:
- human/historical context only

Veo Specialist work order:
- reconstruction level: R2
- primary event: workers handling/working around timber in a historic Venetian construction context
- one visual action only
- no exact pile spacing/dimension claims
- avoid impossible modern machinery
- avoid text/signage
- architecture must not be presented as exact Santa Maria Maggiore reconstruction unless reference-bound

### Continuity Bridge
Previous end state:
- SH08 representative foundation module partially reassembled / timber layer highlighted

Intended start state:
- historical context begins on timber material/action motif, not a hard geometry match

Intended end state:
- close/medium timber handling detail suitable for semantic match into SH10 wood material explanation

Next start target:
- SH10 diagrammatic timber/material close-up

Compatibility note:
- bridge is SEMANTIC/TEMPORAL, not exact spatial continuation

Continuity risk:
MEDIUM — AI may invent foundation topology; crop/frame so topology is not offered as evidence.

### Reference Binding
Possible reference: approved mood/wardrobe/era references
Bound role: atmosphere/era visual language
Must preserve: no modern objects, broad historical tone
May reinterpret: extras, texture, weather
Must not affect: canonical foundation geometry

Fallback:
- licensed historical illustration/detail + 2.5D parallax
- no Veo generation required for episode validity

---

## PROD-CTX-01 — Modern Venice Context
Covers: SH01, SH15
Preferred route order:
1. rights-cleared real/reference footage
2. approved still + parallax
3. Veo contextual generation if identity need is generic

Rule:
A generated “Venice-like” façade cannot be captioned as a named real building.

---

# Camera Previs Orders

## PREVIS-A — Surface→Section Chain
Shots: SH02→SH04→SH05
PASS if:
- waterline remains stable
- viewer understands section direction
- first pile reveal occurs without camera flip
- representative label visible at reveal

## PREVIS-B — Mechanism Chain
Shots: SH06→SH08
PASS if:
- load tracer remains same semantic object
- camera motion decreases during dense explanation
- explode axes preserve component relationship

## PREVIS-C — Return Chain
Shots: SH12→SH14
PASS if:
- stress comparison clearly labeled illustrative
- reassembly returns to same registered state
- city-scale expansion shows variation rather than identical repeated foundation

---

# Generation Manifest — Paper Records

## GM-SH09-v1
Provider family: Google video / Veo adapter candidate
Model: UNLOCKED until runtime capability verification
Prompt artifact: `PROMPT-SH09-v1` conceptual
Input assets: approved era/mood refs only
Shot spec: Visual Plan v1 / SH09
Spatial Bible: v1
Attempt budget: pilot default TBD
Cost ceiling: project/runtime decision TBD
Output: NOT_GENERATED
QA state: UNREVIEWED

No provider-specific version is hardcoded by architecture.

---

# Veo Model-Ready Prompt Contract — SH09 Draft

This is a design test, not a generation request.

Subject/action:
- small group of historical Venetian construction workers handling timber near a waterside building site; one clear action focused on moving/positioning timber

Environment:
- pre-modern Venetian waterside construction atmosphere; damp wood, masonry, muted daylight

Camera intent:
- restrained medium tracking or stable observational move; cinematic context, not explanatory orbit

First frame:
- timber enters frame as dominant semantic anchor; workers visible; no hidden foundation topology shown

Last frame:
- closer timber/worker-hand detail suitable for match into material explanation

Invariants:
- no modern safety gear/machinery/electric lighting
- no readable modern signage
- no exact engineered pile grid shown as documentary truth

Avoid:
- fantasy Renaissance spectacle
- impossible tools
- dramatic collapsing structures
- hyper-fast camera
- multiple scene changes

Audio intent:
- optional plausible work ambience only; if generated, treat as reconstructed S1/S2 pending review

---

# Post / Timeline Paper Plan

## Rough timing bands
- B0/B1: ~1:10
- B2/B3: ~2:20
- B4: ~1:10
- B5: ~1:25
- B6: ~1:10
- B7: ~1:05
- B8: ~1:10+

Total target after breathing room: 9–11 min

## Narration route
- scratch TTS/voice only after Story Pack lock
- final voice prohibited before picture timing stabilizes

## Music route
- temp cues from Audio Timeline Contract
- final source/provider undecided
- no rights-unclear cue can reach final publish state

## SFX route
- S0 real modern ambience if licensed/recorded
- S1/S2 historical work reconstruction if used
- S3 load-path/reveal semantic cues

---

# Budget / Cost Design

No hard prices are frozen in design.
Cost attribution must later track:
- Blender scene setup
- Blender render/previs
- Veo attempts by shot
- accepted vs rejected attempts
- TTS
- music
- external licensed assets
- human modeler (expected 0 for pilot)

Critical metric:
`wasted_expensive_generation_due_to_upstream_change`

Goal for pilot:
- central explanatory sequence survives with Blender/2D even if Veo unavailable.

---

# Failure / Retry Routes

## Blender geometry mismatch
Do not cosmetic-fix render.
→ Spatial Bible or scene spec correction.

## Veo historical topology drift
If topology not needed:
→ crop/reframe/re-prompt with less structural visibility.
If shot accidentally became explanatory:
→ reroute to Blender/2D.

## Camera orientation fail
→ revise camera rig/transition; do not add narration to explain a confusing camera unless unavoidable.

## Music masks explanation
→ lower density/remove cue before changing narration.

## Unsupported visual detail discovered
→ Evidence Pack/Spatial Bible upstream review.

---

# Production Gate Verdict

**PASS AS PAPER WORK ORDER**

The current contracts are sufficient to dispatch Blender, 2D, Veo-context and Post responsibilities without adding a new orchestra or a full-time modeler.
