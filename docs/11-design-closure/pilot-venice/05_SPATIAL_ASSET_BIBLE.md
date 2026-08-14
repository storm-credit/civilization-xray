# VX-PILOT-001 — Spatial / Asset Bible

Artifact: P5 Spatial / Asset Bible  
Version: v1  
Status: LOCKED_FOR_PAPER_RUN  
Inputs: Evidence Pack v1 + Visual Plan v1  
Owner: Spatial / Asset Architect  

## Hero Scope
`representative_section`

This is **not** an exact measured reconstruction of one whole Venetian building and not a universal city foundation.

Primary explanatory section represents the documented relationship among:
- load-bearing wall / masonry mass
- upper foundation/base
- horizontal timber layer/deck concept where supported by the selected documented technique
- closely spaced timber piles
- weak lagoon sediment zone
- canal/waterline context

Primary evidence anchor: Santa Maria Maggiore research + broader Venice foundation studies.
Secondary case context: Rialto Bridge.

---

# Coordinate / Orientation Convention

Paper convention only; exact coordinates deferred.

- +Z = up
- +X = section horizontal direction from canal/outside toward building interior
- +Y = along wall / out of section plane
- canonical section plane = X/Z
- camera for section proof is primarily aligned along ±Y toward the X/Z plane
- waterline is a stable horizontal semantic reference

All deterministic section shots must preserve this convention unless the Visual Plan explicitly declares a reorientation transition.

---

# Component Registry

## CMP-01 WATERLINE
Type: spatial reference
Hardness: HARD semantic/orientation lock
Purpose: separates visible Venice context from hidden foundation zone

## CMP-02 MASONRY_WALL
Type: load-bearing representative wall mass
Hardness: HARD relative-position lock
Rule: wall vertical axis must remain registered with foundation zone below.

## CMP-03 UPPER_FOUNDATION_BASE
Type: simplified structural/base zone
Hardness: HARD relationship, SOFT exact material/shape unless sourced
Rule: receives wall load and transfers it to lower foundation assembly.

## CMP-04 TIMBER_HORIZONTAL_LAYER
Type: representative horizontal timber/plank/deck layer
Hardness: HARD presence for selected documented technique; SOFT exact plank count/thickness
Evidence: S02/S03
Rule: do not claim exact zatterone construction for every building.

## CMP-05 TIMBER_PILE_FIELD
Type: closely spaced vertical timber piles
Hardness: HARD topology concept; SOFT exact count/spacing/diameter/length
Evidence: S01–S03
Rule: must appear as a group/system, not one heroic pile.

## CMP-06 REPRESENTATIVE_SOFT_SEDIMENT
Type: lagoon soil zone
Hardness: HARD concept, SOFT exact layer geometry
Evidence: C001
Rule: use semantic textures/labels for mixed sand/silt/clay/peat context; do not make a universal exact stratigraphy.

## CMP-07 CANAL_WATER
Type: context
Hardness: HARD relationship to waterline; SOFT visual detail

## CMP-08 LOAD_TRACER
Type: semantic overlay
Hardness: HARD semantic continuity across SH06/SH12/SH13
Rule: illustrative; not numeric stress field.

## CMP-09 REPRESENTATIVE_BUILDING_SHELL
Type: context shell
Hardness: SOFT geometry unless a named reference building is selected
Rule: shell may be generic enough not to impersonate a specific landmark.

---

# Component Relationship Graph

Conceptual order:

`CMP-09 building shell`
→ `CMP-02 masonry wall`
→ `CMP-03 upper foundation/base`
→ `CMP-04 horizontal timber layer`
→ `CMP-05 dense timber pile field`
↔ `CMP-06 surrounding soft sediment`

`CMP-07 canal water` defines context/waterline but is not represented as “supporting” the building.

`CMP-08 load tracer` follows the same order for explanation.

---

# Hard Locks

1. Wall axis remains registered above its foundation/pile zone.
2. Pile field remains below the selected load-bearing portion, not randomly under all visible scenery.
3. Horizontal timber layer, when shown, remains above pile heads and below the masonry/base zone in the selected representative technique.
4. Waterline remains consistent across surface→section→reassembly shots.
5. +Z/up and canonical section orientation remain consistent through SH02–SH08 and SH13.
6. Same component IDs must return to original positions during reassembly.
7. Piles terminate within representative sediment in this pilot; no universal labeled bedrock/hard-stratum endpoint.
8. Load tracer is qualitative only.

---

# Soft Locks

- exact façade style
- exact canal width
- exact pile count
- exact pile spacing
- exact pile length/diameter
- exact soil-layer thickness
- exact plank count
- color/material palette

If any soft field becomes a spoken numeric claim in production, it becomes a HARD evidence-backed field for that version.

---

# Free Fields

- background boats
- distant architecture silhouettes
- atmospheric water reflections
- non-explanatory props
- historic worker clothing details within era/rights/reconstruction constraints

Free fields may not alter hard spatial truth.

---

# Unknown / Reconstructed Zones

## U01 — exact representative building façade
Treatment: generic/abstract context or separately sourced reference.

## U02 — exact subsurface stratigraphy for citywide Venice
Treatment: SCHEMATIC representative sediment, explicit label.

## U03 — exact pile geometry for a generic Venice section
Treatment: show relational density, not fake measured dimensions.

## U04 — historical construction choreography
Treatment: R2 generative reconstruction; not evidence for exact procedure.

## U05 — exact load/stress distribution
Treatment: R1/R3 illustrative load-path/tracer; no numeric field without calculation/source.

---

# Scale Policy

- Surface city/building context: TRUE_SCALE intent where reference based
- Representative foundation section: SCHEMATIC
- Soil deformation/stress comparison: EXAGGERATED_FOR_EXPLANATION
- Material decay graphic: SCHEMATIC

Every exaggerated shot carries explanatory labeling.

---

# Asset Acquisition Routes

## A01 Representative foundation module
Route: M1 procedural/parametric Blender
Target fidelity: G1 explanatory, selective G2 presentation
Reason: primitive geometry, strong spatial locks, repeated use

## A02 Soil/water section
Route: M1 + 2D overlays
Target: G1

## A03 Building exterior/context
Route: M2 approved asset / simplified Blender / real reference / generated contextual shot depending rights and claim identity
Target: G0–G1 if not hero exterior

## A04 Historical workers/context
Route: Veo cinematic generation candidate
Target: atmosphere only

## A05 Material decay macro
Route: 2D scientific-style illustration + approved reference if rights allow
Target: explanatory

Human modeler gate: **NOT TRIGGERED** for this pilot.

---

# Reference Binding Rules

## RB-01 Research figure/section reference
Bound role: structural relationship evidence
Must preserve: relative ordering/relationship supported by source
May reinterpret: visual materials, simplification, labels
Must not affect: unsupported façade/interior geometry

## RB-02 Venice exterior image
Bound role: context/identity
Must preserve: visible location identity if claimed real
May reinterpret: grade/crop if rights permit
Must not affect: hidden foundation truth

## RB-03 Blender first-frame anchor for Veo bridge
Bound role: geometry boundary at transition
Must preserve: silhouette/orientation of visible structural anchor
May reinterpret: atmosphere/people/water movement
Must not affect: hidden topology or add invented structural members presented as evidence

---

# Continuity Anchors

## Object continuity
CMP-02 through CMP-06 preserve identity and ordering.

## Spatial continuity
Waterline + canonical section + wall axis.

## Semantic continuity
CMP-08 load tracer; selected wall module highlight.

## Temporal continuity
Modern Venice exterior and historical reconstruction are explicitly separated by CX-TR-05 TEMPORAL_MATCH.

---

# Blender Build Intent — No Code

The future Blender Specialist should be able to build the explanatory module from:
- primitives for pile cylinders/rough timber forms
- layered planes/volumes for soil/water
- simple masonry/base volumes
- collection/component IDs matching registry
- section plane control
- explode axes
- load-tracer curve/overlay
- camera rigs CX-CAM-04/05/07/08/10/11

No Blender Python is written during Closure 0.6.

---

# Spatial QA Checklist

- [ ] wall/pile relationship remains stable across all deterministic shots
- [ ] section never silently flips left/right
- [ ] piles are not shown as a universal bedrock-bearing forest
- [ ] pile count/spacing does not look measured unless labeled representative
- [ ] reassembly returns every component to original registered state
- [ ] soil layers do not imply universal geological precision
- [ ] Veo output cannot become source of truth for hidden geometry
- [ ] selected representative label survives edit/caption

## Spatial Gate Verdict
**PASS FOR PAPER PRODUCTION**

No human modeler or new 3D technology is required to explain this pilot mechanism.
