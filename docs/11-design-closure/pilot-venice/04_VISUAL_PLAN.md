# VX-PILOT-001 — Visual Plan

Artifact: P4 Visual Plan  
Version: v1  
Status: LOCKED_FOR_PAPER_RUN  
Inputs: Story Pack v1 + Evidence Pack v1  
Owner: Script–Visual Architect / Video Director  

Design target: 15 primary visual work orders. 32 narration units are intentionally compressed into fewer coherent explanatory sequences.

Legend:
- BL = Blender deterministic
- VE = Veo cinematic/generative
- 2D = diagram/motion graphics
- HY = hybrid
- RR = real/reference/context footage or still if rights-cleared

---

## SH01 — Venice Recognition
Units: N001
Claims: none
Objective: instantly establish recognizable Venice without spending explanation budget.
Proof question: viewer knows where we are.
Route: VE or RR
Camera: CX-CAM-12 CINEMATIC_CONTEXT
Entry: canal/building wide
Exit: stable building edge / waterline composition
Transition out: CX-TR-03 SCALE_MATCH to chosen representative building edge
Continuity: TEMPORAL/SPATIAL low-hardness
Reconstruction: R0 if real reference; R2 if generated
Scale: TRUE_SCALE intent
Duration: 6–10s
Fallback: licensed still + subtle parallax
Risk: generated façade may look like a real named building; avoid claiming exact identity unless reference-bound.

---

## SH02 — Surface to Hidden Section
Units: N002–N003
Claims: C001
Objective: shift question from “water” to “ground below.”
Proof question: viewer sees that the hidden problem is below water/ground.
Route: BL + 2D labels
Camera: CX-CAM-04 SURFACE_TO_SECTION
Entry: registered exterior/waterline
Exit: clean representative section showing wall, waterline, weak-ground zone without piles yet
Transition: CX-TR-02 LAYER_REVEAL
Continuity: SPATIAL hard
Reconstruction: R2 representative section, soil R1/R2 schematic
Scale: SCHEMATIC
Hard locks: vertical axis, waterline, wall axis, section direction
Duration: 10–14s
Fallback: 2D animated section

---

## SH03 — Wrong Intuition Illustration
Units: N004–N005
Claims: scope only
Objective: show the tempting “long piles to a hard layer” mental model, then mark it as not universal.
Route: 2D
Camera: ORTHO/DIAGRAMMATIC
Entry: simple icon section
Exit: model fades/question mark + “건물·시기별 차이”
Transition: CX-TR-04 REPRESENTATION_MATCH
Reconstruction: R3 illustrative
Scale: SCHEMATIC
Duration: 8–12s
Hard rule: never render this intuition as photoreal documented Venice.

---

## SH04 — First Pile-Field Reveal
Units: N006–N008
Claims: C002, C003
Objective: first signature X-Ray payoff; reveal representative short/closely spaced pile reinforcement and horizontal timber layer.
Route: BL
Camera: CX-CAM-08 XRAY_REGISTERED_REVEAL → CX-CAM-05 SECTION_INSPECTION
Entry: SH02 section without hidden foundation detail
Exit: pile field + timber horizontal layer + wall/base visible
Transition: CX-TR-02 LAYER_REVEAL
Continuity: OBJECT/SPATIAL hard
Reconstruction: R1/R2 representative documented technique
Scale: SCHEMATIC unless exact case dimensions later sourced
Labels: “대표 단면”, “건물/시기별 차이 있음”
Duration: 15–20s
Fallback: technical 2D cutaway

---

## SH05 — Isolate One Bearing-Wall Module
Units: N007–N009
Claims: C002, C003
Objective: reduce city complexity; define explanatory unit.
Route: BL
Camera: CX-CAM-02 TARGET_PUSH
Entry: broader section
Exit: one highlighted wall-foundation-pile module; neighbors dimmed
Continuity: OBJECT/SPATIAL
Reconstruction: R1/R2
Scale: SCHEMATIC
Duration: 10–15s

---

## SH06 — Load Path
Units: N010–N013
Claims: C001–C004 + R1 explanation
Objective: visualize load transfer order without pretending to provide measured stresses.
Route: BL + 2D overlay
Camera: CX-CAM-05 SECTION_INSPECTION / near lockoff
Visual action: LOAD_PATH arrows / pressure-area concept
Entry: isolated module
Exit: load tracer reaches pile/ground zone
Continuity: SEMANTIC hard (same load tracer)
Reconstruction: R1 explanatory inference
Scale: SCHEMATIC
Hard rule: no numeric stress values without source/calculation.
Duration: 25–40s across one or two edited beats
Fallback: 2D load-path diagram

---

## SH07 — Ground Reinforcement Concept
Units: N011–N013
Claims: C002, C004
Objective: distinguish ground/foundation system from “each pile is a column to bedrock.”
Route: 2D + BL hybrid
Camera: CX-CAM-10 STRESS_LOCKOFF
Visual action: same soft-soil block with representative dense inclusions; qualitative deformation/area concept
Reconstruction: R3 illustrative causal diagram
Scale: EXAGGERATED_FOR_EXPLANATION
Mandatory label: “개념도 / 실제 침하량 아님”
Duration: 15–20s

---

## SH08 — Exploded Relationship
Units: N014–N016
Claims: C003
Objective: show why wall, base, horizontal timber, piles and ground must be read together.
Route: BL
Camera: CX-CAM-07 EXPLODED_INSPECTION
Entry: assembled module
Exit: controlled exploded state along defined vertical axes
Continuity: OBJECT hard
Reconstruction: R1/R2
Scale: SCHEMATIC
Duration: 14–18s
Transition out: reassemble partially before material question

---

## SH09 — Historical Construction Atmosphere
Units: N017
Claims: no exact construction-sequence claim
Objective: humanize transition to wood/material question.
Route: VE
Camera: CX-CAM-12 CINEMATIC_CONTEXT
Prompt intent: historical Venetian labor context, handling/timber/pile work without specifying unsupported exact machine/sequence
Entry/Exit anchors: approved representative foundation-era mood frames, not topology proof
Reconstruction: R2
Continuity: TEMPORAL
Duration: 6–8s
Hard rule: no generative shot used as evidence for exact pile dimensions/layout.
Fallback: archival art/reference still if licensed + label

---

## SH10 — Waterlogged Wood: Myth vs Evidence
Units: N018–N021
Claims: C006, C007
Objective: correct “never rots” myth.
Route: 2D macro illustration + source-derived text callouts; optional BL material close-up
Camera: CX-CAM-09 SCALE_BRIDGE / DETAIL_INSPECTION intent
Visual action: preserved interior vs degraded zones concept; depth comparison from named case as diagram
Reconstruction: R1/R3 depending depiction
Scale: SCHEMATIC
Mandatory qualifier: Santa Maria Maggiore case for depth finding
Duration: 25–35s
Hard rule: do not show wood petrifying into stone.

---

## SH11 — Species / Site Variation
Units: N022–N025
Claims: C005, C008, C009
Objective: use evidence diversity to prove why one universal model is wrong.
Route: 2D evidence cards + map/simple case markers
Camera: static/diagrammatic
Visuals:
- “multiple species found in Venice samples”
- Santa Maria Maggiore case
- Rialto Bridge case
- decay ≠ automatic whole-building instability
Reconstruction: R0/R1 text/diagram
Duration: 20–30s

---

## SH12 — Counterfactual Stress Comparison
Units: N026–N028
Claims: C001–C004; explicitly illustrative
Objective: causal proof of “system changes how load/ground is handled,” not numerical prediction.
Route: BL/2D
Camera: CX-CAM-10 STRESS_LOCKOFF
Entry: two side-by-side schematic ground blocks
Action: same symbolic load applied
Exit: qualitative difference highlighted
Reconstruction: R3
Scale: EXAGGERATED_FOR_EXPLANATION
Mandatory on-screen label: “설명용 개념도 — 실제 침하량 계산 아님”
Duration: 15–20s

---

## SH13 — Reassembly to Building
Units: N029–N030
Claims: C001–C004
Objective: connect hidden system back to visible building.
Route: BL
Camera: CX-CAM-11 REASSEMBLY_RETURN + CX-CAM-03 CONTEXT_PULLBACK
Entry: exploded/section module
Exit: assembled building-edge context with optional ghosted below-ground section
Transition: CX-TR-03 SCALE_MATCH
Continuity: OBJECT/SPATIAL/SEMANTIC hard
Duration: 15–20s

---

## SH14 — City-Scale Mental Overlay
Units: N030–N031
Claims: scope synthesis
Objective: viewer mentally extends the principle without claiming every building is identical.
Route: HY (Blender/2D city context + multiple non-identical foundation icons)
Camera: CX-CAM-03 CONTEXT_PULLBACK
Visual action: selected building module → several varied foundation-case silhouettes; never repeat one identical pile grid under entire city
Reconstruction: R2/R3
Scale: SCHEMATIC
Duration: 10–15s

---

## SH15 — Final Venice Return
Units: N032
Claims: none new
Objective: residual wonder; same visible city now read with hidden-section knowledge.
Route: RR or VE
Camera: same/similar hero angle as SH01 if possible
Transition: CX-TR-04 REPRESENTATION_MATCH or edit match
Audio: near-silence before final line candidate
Duration: 8–12s

---

# Route Summary

- Blender/HY deterministic explanatory: SH02, SH04, SH05, SH06, SH07, SH08, SH12, SH13, SH14
- Veo cinematic: SH01 optional, SH09, SH15 optional
- 2D first-class: SH03, SH07, SH10, SH11, SH12

Veo is **not** central mechanism proof.

Estimated expensive generative shot need for paper plan: 1–3 clips, not every narration unit.

---

# Previs Gate Questions

1. SH02→SH04에서 viewer가 section 방향을 잃지 않는가?
2. SH04 pile reveal이 “베네치아 전체 공식”처럼 보이지 않는가?
3. SH06 load tracer가 same semantic anchor로 유지되는가?
4. SH07/SH12 개념도가 실제 계산처럼 오해되지 않는가?
5. SH09 historical Veo shot이 exact construction evidence처럼 보이지 않는가?
6. SH10 preservation correction이 foundation mechanism보다 더 큰 비중을 먹지 않는가?
7. SH13 reassembly가 SH04/SH08의 component를 정확히 원위치로 돌려놓는가?
8. SH14에서 다양성을 시각적으로 보여주는가?

## Visual Plan Verdict
**PASS FOR SPATIAL BIBLE + PRODUCTION PAPER RUN**

No new top-level production capability is required.
