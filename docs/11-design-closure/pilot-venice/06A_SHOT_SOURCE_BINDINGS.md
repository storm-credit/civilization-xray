# VX-PILOT-001 — P6 Child Appendix: Shot / Source / Execution Bindings v0

Parent artifact: **P6 Production Pack**  
Status: **PREPRODUCTION BINDING READY / NO MEDIA GENERATED**  
Inputs: Visual Plan v1 + Evidence Pack v1 + Spatial / Asset Bible v1 + Production Pack v1.1  
Authority: P6 child record; **not an eighth core artifact**

Purpose: map every approved visual work order to the smallest sufficient execution route and source/reference set before any real media assembly.

---

# 1. Binding Law

1. **Evidence authority and visual-license status are separate.**
   - A rights-cleared image does not become factual authority.
   - Evidence Pack remains the claim authority.
2. **Use external media only when it adds identity, historical context, or a named-case reference that Blender/2D should not fake.**
3. **Core mechanism shots default to project-authored Blender/2D.**
4. **Historical maps/illustrations are depictions, not survey-grade geometry.**
5. **Generated historical footage is reconstruction, never documentary evidence.**
6. **Bookend continuity is preferred over decorative variety.** If one modern Venice view works for SH01, reuse the same source/angle family for SH15 when possible.
7. **No source padding.** A shot may intentionally have `external_reference = NONE`.

Binding classes:
- `B0 PROJECT-AUTHORED` — Evidence/Spatial/Story → Blender/2D; no third-party visual needed.
- `B1 REAL-CONTEXT` — rights-cleared modern identity/context source.
- `B2 NAMED-CASE-REFERENCE` — historical/technical visual tied to one named case; scope-limited.
- `B3 HISTORICAL-CONTEXT` — map/cityscape/era image for temporal context only.
- `B4 GENERATIVE-RECONSTRUCTION` — cinematic reconstruction candidate; non-factual authority.

No current Venice shot requires a third-party `B2` or figure to establish the central mechanism.

---

# 2. Fifteen-Shot Binding Matrix

## SH01 — Venice Recognition
Primary execution: `RR / still+parallax`  
Binding class: `B1 REAL-CONTEXT`

Primary candidate:
- `VR-06` Grand Canal modern context view — CC BY 4.0, attribution required.

Fallback:
- `VR-07` Canal Grande alternative — CC BY 4.0.
- generative Venice-like context only if a real source cannot satisfy the edit; generated identity must remain generic.

Allowed use:
- establish modern Venice identity;
- water/building/waterline visual motif;
- potential bookend anchor for SH15.

Forbidden use:
- no implication that the visible building uses the representative foundation module shown later;
- no foundation claim from the image.

Preproduction verdict: **BOUND / FINAL FILE NOT YET SELECTED**.

---

## SH02 — Surface to Hidden Section
Primary execution: `BL + 2D labels`  
Binding class: `B0 PROJECT-AUTHORED`

Authority inputs:
- Evidence Pack `C001`;
- Spatial Bible canonical representative section;
- Visual Plan hard waterline/wall/section locks.

External visual reference: `NONE REQUIRED`.

Reason:
A historical drawing would increase false precision and make one named case look universal. Build the representative section from sourced relationships instead.

Preproduction verdict: **BOUND**.

---

## SH03 — Wrong Intuition Illustration
Primary execution: `2D original diagram`  
Binding class: `B0 PROJECT-AUTHORED`

Authority inputs:
- Evidence Pack conflict note around short ground-improvement piles vs deeper/stronger-layer descriptions;
- Visual Plan rule that the mental model is illustrative, not documented Venice.

External visual reference: `NONE`.

Forbidden:
- do not use a photoreal or historical-looking source image to represent the deliberately wrong intuition;
- `VR-REJECT-01` is not eligible as factual support.

Preproduction verdict: **BOUND**.

---

## SH04 — First Pile-Field Reveal
Primary execution: `BL`  
Binding class: `B0 PROJECT-AUTHORED`

Authority inputs:
- `C002`, `C003`;
- Spatial Bible representative technique/hard locks;
- mandatory `대표 단면 / 건물·시기별 차이` labeling.

External visual reference: `NONE REQUIRED`.

`VR-01` Campanile drawing is **not** used to define this hero geometry because the episode section is representative, while VR-01 is a named case.

Preproduction verdict: **BOUND**.

---

## SH05 — Isolate One Bearing-Wall Module
Primary execution: `BL`  
Binding class: `B0 PROJECT-AUTHORED`

Authority inputs:
- same canonical Blender module as SH04;
- no new factual visual data introduced.

External visual reference: `NONE`.

Preproduction verdict: **BOUND**.

---

## SH06 — Load Path
Primary execution: `BL + project-authored 2D overlay`  
Binding class: `B0 PROJECT-AUTHORED`

Authority inputs:
- `C001–C004`;
- qualitative R1 explanation only;
- no numeric stress claim.

External visual reference: `NONE`.

Hard rule:
Do not import a textbook stress plot or engineering figure merely because it looks scientific; the episode is not claiming measured/calculated stress values.

Preproduction verdict: **BOUND**.

---

## SH07 — Ground Reinforcement Concept
Primary execution: `2D + BL hybrid`  
Binding class: `B0 PROJECT-AUTHORED`

Authority inputs:
- `C002`, `C004`;
- explanatory causal model;
- mandatory `개념도 / 실제 침하량 아님` label.

External visual reference: `NONE`.

Preproduction verdict: **BOUND**.

---

## SH08 — Exploded Relationship
Primary execution: `BL`  
Binding class: `B0 PROJECT-AUTHORED`

Authority inputs:
- `C003`;
- Spatial Bible component relationships and axes.

External visual reference: `NONE`.

Reason:
The explanatory value comes from preserving the same canonical module across assembly/explode/reassembly, not from historical-image variety.

Preproduction verdict: **BOUND**.

---

## SH09 — Historical Construction Atmosphere
Primary execution: `R-GENERATIVE-VIDEO candidate` or rights-cleared still/parallax  
Binding classes: `B4 GENERATIVE-RECONSTRUCTION` + optional `B3 HISTORICAL-CONTEXT`

Optional historical context candidates:
- `VR-08` 1493 Venice cityscape — CC BY 4.0; setting/cityscape context only.
- `VR-03` 1534 Bordone map — Public Domain; optional transition/context only.

Reference gap intentionally remains:
- no rights-cleared source has yet been promoted as factual evidence for exact worker clothing, tools, pile-driving machine, or construction sequence.

Therefore generative work order must stay generic:
- workers handling timber in a pre-modern Venetian waterside context;
- no unsupported exact machine;
- no exact pile grid offered as evidence.

Allowed AniJam role:
- W0 supervised candidate execution only;
- whole-script/scene-breakdown output remains non-canonical.

Fallback order:
1. direct generative provider candidate;
2. AniJam supervised candidate;
3. VR-08 or another rights-cleared historical still with restrained parallax;
4. omit SH09 if it adds no explanatory value.

Preproduction verdict: **BOUND WITH REFERENCE GAP / NON-BLOCKING**.

---

## SH10 — Waterlogged Wood: Myth vs Evidence
Primary execution: `2D original evidence graphic + optional BL material close-up`  
Binding class: `B0 PROJECT-AUTHORED`

Authority inputs:
- `C006`, `C007`;
- Santa Maria Maggiore named-case qualifier;
- source-derived facts, not copied paper figure styling.

External visual reference: `NONE REQUIRED`.

`VR-01` is not used here because it is a Campanile foundation drawing and does not establish the Santa Maria depth/preservation finding.

Preproduction verdict: **BOUND**.

---

## SH11 — Species / Site Variation
Primary execution: `2D evidence cards + project-authored schematic case map`  
Binding class: `B0 PROJECT-AUTHORED`

Authority inputs:
- `C005`, `C008`, `C009`;
- named-case wording for Santa Maria Maggiore and Rialto;
- multiple-species finding.

Optional named-case reference:
- `VR-01` may appear only as a clearly labeled **Campanile visual reference sidebar** if editorially useful.
- It may not be presented as evidence for C005/C008/C009 and must not replace the Santa Maria/Rialto source lineage.

Default decision: **do not use VR-01 unless the rough storyboard proves the extra case image improves comprehension**.

Preproduction verdict: **BOUND / OPTIONAL CASE REFERENCE HELD BACK**.

---

## SH12 — Counterfactual Stress Comparison
Primary execution: `BL / 2D original diagram`  
Binding class: `B0 PROJECT-AUTHORED`

Authority inputs:
- C001–C004;
- explicit R3 counterfactual/illustrative treatment.

External visual reference: `NONE`.

Hard rule:
No disaster footage or real collapse image is needed; that would add spectacle without strengthening the causal explanation.

Preproduction verdict: **BOUND**.

---

## SH13 — Reassembly to Building
Primary execution: `BL`  
Binding class: `B0 PROJECT-AUTHORED`

Authority inputs:
- same canonical module from SH04–SH08;
- registered camera/reassembly state.

External visual reference: `NONE REQUIRED`.

Reason:
The payoff depends on proving the components return to the same system, not on switching to a new real-building image.

Preproduction verdict: **BOUND**.

---

## SH14 — City-Scale Mental Overlay
Primary execution: `BL/2D hybrid`  
Binding classes: `B0 PROJECT-AUTHORED` + optional `B3 HISTORICAL-CONTEXT`

Primary visual authority:
- project-authored varied foundation silhouettes/icons;
- scope synthesis only, never identical pile grids under the whole city.

Optional historical context candidates:
- `VR-04` Nicolas de Fer 1725 map — Public Domain, high-resolution context;
- `VR-05` 1838 map — Public Domain, alternate high-resolution context;
- `VR-02` 1380 map — Public Domain, only if wide/low-detail treatment works despite low source resolution.

Allowed use:
- city-shape/time-context background;
- slow map push/pull as a semantic scale bridge.

Forbidden use:
- exact location of specific foundation typologies inferred from map depiction;
- survey-grade spatial claim.

Default preference: use **one** map candidate, not a montage of all four.

Preproduction verdict: **BOUND / MAP CANDIDATE SELECTION DEFERRED TO STORYBOARD**.

---

## SH15 — Final Venice Return
Primary execution: `RR / still+parallax`  
Binding class: `B1 REAL-CONTEXT`

Preferred binding:
- reuse `VR-06` if selected for SH01, ideally same image/angle family with different crop or motion.

Fallback:
- `VR-07` only if continuity/readability is materially better;
- generated context only if no rights-cleared real visual works.

Purpose:
Create a bookend: the visible city is unchanged, but the viewer now mentally sees the hidden system.

Forbidden:
- do not introduce a new dramatic landmark just for spectacle;
- no new factual claim in the final beauty shot.

Preproduction verdict: **BOUND / BOOKEND LOCK**.

---

# 3. External-Asset Minimality Verdict

For the current 15-shot plan:

- Core mechanism proof can be completed with **zero third-party technical figures**.
- Recommended real-context third-party media: **1 primary modern Venice source** reused across SH01/SH15.
- Recommended historical context: **0–1 map/cityscape source** for SH09 or SH14 if it improves temporal/context clarity.
- `VR-01` Campanile drawing remains optional named-case reference, not central proof.
- No external asset is allowed to override Evidence Pack or Spatial Bible authority.

This prevents a reference-heavy slideshow and keeps the episode's visual identity centered on project-authored X-Ray explanation.

---

# 4. Storyboard Promotion Gate

A candidate binding may move from this preproduction appendix into real media assembly only when:

1. exact source file/revision is captured;
2. rights/credit state passes P6 Rights/Credit Gate;
3. factual role is explicitly classified;
4. shot objective remains unchanged;
5. Visual QA confirms the reference does not visually overclaim;
6. using the asset is better than the project-authored Blender/2D alternative;
7. the asset does not create redundant decoration or montage pressure;
8. final selected external assets remain minimal enough that the episode still reads as Civilization X-Ray, not archival slideshow.

Current gate verdict: **PASS FOR STORYBOARD / NO MEDIA ASSEMBLY AUTHORIZED**.
