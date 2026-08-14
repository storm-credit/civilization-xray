# VX-PILOT-001 — Review & Run Ledger

Artifact: P7 Review & Run Ledger  
Version: v1  
Status: PAPER_RUN_COMPLETE  
Covers: Editorial → Research → Visual → Production → Audio/Post → Release  

Purpose: 한 편을 끝까지 흘려보며 gate, rollback, stale propagation, independent QA, release packaging이 7-core-artifact 구조에서 실제로 닫히는지 검증한다.

---

# 1. Stage Run

## E001 — Episode Brief Gate
Input: Episode Brief v1
Verdict: PASS
Evidence:
- central question clear
- explanatory unit = representative_section
- primary case anchor declared
- explicit scope-out prevents citywide universal claim

Next: Research

---

## E002 — Research / Claim Gate
Input: Evidence Pack v1
Reviewer: Claim Verifier
Verdict: PASS WITH SCOPE LOCKS
Evidence:
- C001–C009 linked to institutional/peer-reviewed sources
- short-pile technique is scoped to documented practice/cases
- preservation myth corrected
- “all Venice identical” explicitly prohibited

Hard retained qualifiers:
- representative
- documented technique
- named-case wording where needed

Next: Story

---

## E003 — Story Gate
Input: Story Pack v1
Reviewer: Script Editor / Fact Reviewer
Verdict: PASS
Evidence:
- N006/N008/N018/N024/N027/N031 carry critical scope/truth qualifiers
- mechanism completes before preservation side-question
- final payoff matches central question

Next: Visual

---

## E004 — Visual Map Gate
Input: Visual Plan v1
Verdict: PASS
Evidence:
- 32 narration units compressed to 15 work orders
- central mechanism coverage is Blender/2D, not Veo
- all high-risk shots have truth/scale labels
- camera entry/exit states exist

Next: Spatial

---

## E005 — Spatial Readiness Gate
Input: Spatial Bible v1
Reviewer: Visual QA
Verdict: PASS
Evidence:
- canonical section axes defined
- hard/soft/free locks distinct
- no universal bedrock endpoint
- unknown zones documented
- human modeler not required

Next: Previs/Paper Production

---

## E006 — Previs Paper Review
Inputs: Visual Plan v1 + Spatial Bible v1 + Production Pack v1
Verdict: PASS WITH TWO NOTES

Note A:
SH07 and SH12 both explain qualitative ground/load effect; risk of repetition.
Decision:
- SH07 = mechanism explanation
- SH12 = short counterfactual recap only
- if rough cut feels repetitive, SH12 collapses to 6–8s or is removed

Note B:
SH09 historical Veo shot may be expendable.
Decision:
- treat as optional atmosphere, never a gate dependency

Next: Audio/Post Paper Assembly

---

# 2. Audio/Post Paper Run

Audio Beat Map derived from `AUDIO_TIMELINE_CONTRACT_V1.md`.

## Segment mapping

### A01 0:00–0:25 Cold Open
Narration: LIGHT→FULL
Music: CURIOSITY / SPARSE
Ambience: modern Venice context
Picture: SH01→SH02
Audio bridge: ambience L-cut into section descent
Risk: too much “mystery” sound makes science feel sensational

### A02 0:25–1:10 Wrong Intuition
Narration: FULL
Music: INVESTIGATION low
Picture: SH03→SH04
Silence window: 0.5–1.0s around first pile reveal candidate

### A03 1:10–3:30 Core Mechanism
Narration: FULL
Music: MECHANISM / SPARSE
Picture: SH04→SH07
SFX: load tracer = S3 only
Rule: camera and audio both reduce movement/density during N010–N013

### A04 3:30–4:40 Relationship Payoff
Narration: FULL→LIGHT
Music: MECHANISM→small PAYOFF
Picture: SH08
No mandatory impact hit

### A05 4:40–6:05 Wood Question
Narration: FULL
Music: INVESTIGATION / low density
Picture: SH09 optional → SH10
Historical work ambience: S1/S2 if generated

### A06 6:05–7:15 Variability
Narration: FULL
Music: minimal
Picture: SH11
Goal: evidence reading, not spectacle

### A07 7:15–8:20 Counterfactual
Narration: FULL
Music: low TENSION or none
Picture: SH12
SFX: S3 explanatory only

### A08 8:20–End Reassembly
Narration: LIGHT→PAYOFF
Music: PAYOFF→RESOLUTION
Picture: SH13→SH15
Silence window: brief near-silence before N030 final answer candidate

Audio/Post paper verdict: PASS

---

# 3. Fault Injection A — Factual Scope Tightening

Test purpose:
upstream factual scope가 바뀌었을 때 전체 episode를 무조건 폐기하지 않고 정확히 필요한 downstream만 stale/review 처리하는가?

## Injected event
`C003` wording is tightened:

Before hypothetical wording:
- “Venetian foundations used a timber deck over piles.”

Corrected locked wording:
- “In a documented Venetian technique / selected important or load-bearing contexts, short dense piles with horizontal timber layers/deck are described; do not universalize to every building.”

This correction matches Evidence Pack v1 and simulates discovering the scope problem after a draft had already progressed.

## Required stale propagation

### Story Pack
STALE/REVIEW:
- N008
- N015
- N016
- N024
- N031

Reason:
wording may visually/narratively universalize the technique.

### Visual Plan
REVIEW:
- SH04 label
- SH08 exploded relationship
- SH14 city-scale mental overlay

Not automatically invalidated:
- SH06 qualitative load path inside the selected representative module
- SH10 preservation evidence

### Spatial Bible
CMP-04 geometry: REVIEW, not delete
Reason:
geometry remains valid for selected representative technique but its **scope label becomes a hard lock**.

New hard lock:
`REPRESENTATIVE_TECHNIQUE_LABEL` must survive SH04/SH08/SH14 and captions.

### Production Pack
- PROD-BL-01 existing render candidates: STALE until updated label/manifest verifies representative scope
- PROD-VE-01 SH09: NOT STALE, because it does not prove CMP-04 topology
- 2D evidence graphics unrelated to C003: not stale

### Audio/Post
- TTS segments for affected narration: STALE
- captions: STALE
- music cue itself: timing REVIEW only
- SFX: unaffected unless synced to changed edit timing

### Release Package
- title candidates A/D: REVIEW because they may promote overbroad “secret foundation” framing
- selected C remains acceptable

Fault A result: **PASS**
The dependency model produces selective invalidation rather than whole-project reset.

---

# 4. Fault Injection B — Wording-Only Script Revision

Test event:
N020 changes from a longer sentence to a shorter sentence without changing C007 meaning or certainty.

Expected propagation:
- Evidence Pack: unchanged
- Visual SH10: remains valid
- Spatial Bible: unchanged
- scratch/final voice segment: STALE
- captions: STALE
- picture timing: REVIEW
- music cue timing: REVIEW
- no Blender/Veo regeneration required solely due to wording length

Fault B result: **PASS**

This validates that “script changed” is not a binary trigger for redoing all media.

---

# 5. Independent QA Matrix

## Fact / Provenance
Score: 4.5/5
Verdict: PASS
Reason:
major claims sourced; scope conflicts explicitly handled.
Remaining actual-production task: rights/source review for any figures/media.

## Explanation / Clarity
Score: 4.4/5
Verdict: PASS
Risk:
preservation section can become a second episode inside the episode.
Mitigation: keep B5 tight.

## Script ↔ Visual Alignment
Score: 4.7/5
Verdict: PASS
Central claims all have explanatory visual actions.

## Spatial Continuity
Score: 4.6/5
Verdict: PASS ON PAPER
Must be tested with actual Blender previs in Phase 1.

## Visual Truth
Score: 4.6/5
Verdict: PASS
Representative/scematic/exaggerated states explicitly labeled.

## Narrative / Retention
Score: 4.1/5
Verdict: PASS WITH REVIEW
Potential repetition SH07/SH12 noted.

## Audio / Post Design
Score: 4.3/5
Verdict: PASS ON PAPER
Actual voice/music fatigue cannot be proven without timed prototype.

## Rights / Provenance
Score: 4.0/5 design-level
Verdict: PASS FOR DESIGN, NOT PUBLISH
No actual third-party media has been selected yet.

## Cost / Operational Simplicity
Score: 4.7/5
Verdict: PASS
One Blender explanatory module + 2D + optional 1–3 Veo context clips.

Hard fails: 0

---

# 6. Release & Packaging Paper Run

## Four Title/Thumbnail Routes

### R-A — “베네치아는 왜 가라앉지 않을까?”
Thumbnail: city + huge pile forest
Decision: REJECT
Why:
- sinking/flooding conflation
- universal pile forest visual overclaim

### R-B — “물 위의 도시를 떠받치는 나무의 비밀”
Thumbnail: one dramatic timber pile
Decision: REVISE
Why:
- pile-only mechanism distortion

### R-C — “진흙 위에 도시를 세운 방법”
Thumbnail: Venice exterior split into clean X-Ray representative section; wall + horizontal base + dense piles + soil; small label “대표 단면”
Decision: **SELECTED PAPER ROUTE**
Why:
- central mechanism aligned
- visual promise fulfilled by episode
- does not require false “never rots” hook

### R-D — “수백 년 된 나무 기초가 썩지 않는 이유”
Thumbnail: old timber closeup
Decision: REJECT AS MAIN EPISODE
Why:
- Evidence Pack says “never rots” is wrong
- shifts episode from foundation mechanism to material preservation

## Description/Metadata Rule
No claim stronger than Evidence Pack.
Historical reconstruction disclosure included if generative historical clip is used.

## Publish Gate
Current status: **NOT ELIGIBLE — PAPER RUN ONLY**
Reasons:
- no actual media
- no final source/rights manifest
- no real factual visual verification on renders
- no mix/caption master

This is expected and is not a design failure.

---

# 7. Blind-Spot Sweep After Full Run

## BS-01 Universal-representative confusion
Found: YES
Fix: representative label promoted to hard lock.

## BS-02 Preservation tangent overtakes main mechanism
Found: MEDIUM
Fix: cap B5 and keep mechanism payoff before it.

## BS-03 Duplicate stress explanation
Found: YES
Fix: SH12 optional/short.

## BS-04 Veo becomes unnecessary dependency
Found: design originally could imply more usage
Fix: explicitly optional context only for pilot.

## BS-05 Too many narration units → too many shots
Found: YES
Fix: 32 units → 15 visual work orders. Unit count does not equal generation count.

## BS-06 Late factual correction causes total regeneration
Tested: NO, if dependency graph is field-aware.

## BS-07 Audio considered too late
Tested: Audio Beat Map can derive after Story/Visual locks and before final generation; no new artifact required.

## BS-08 Release title overclaims evidence
Found in R-A/R-D
Fix: release Fact Governance works; rejected.

---

# 8. Run Verdict

**DESIGN CLOSURE PILOT: PASS**

What this run proved:
1. 7 physical core artifacts are sufficient.
2. No fifth top-level creative orchestra is needed.
3. Blender-first + 2D + optional Veo is sufficient for the pilot.
4. Camera grammar is expressive enough without adding stylistic rig sprawl.
5. Audio/Post can be represented as timeline rows inside Production/Run structures; no extra core artifact required.
6. Field-aware stale propagation prevents unnecessary regeneration.
7. Release packaging must remain under Fact Governance.
8. Human modeler is not a default dependency.

What remains empirical rather than design-solvable:
- actual Blender camera readability
- actual TTS/narration voice quality
- actual music density/fatigue
- real Veo continuity and cost
- real render time
- actual 10-video benchmark frame DNA

Those belong to benchmark work and Phase 1 supervised prototype, not another architecture layer.
