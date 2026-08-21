# Generative Workbench Routing Addendum v1

Status: **ADDITIVE DESIGN CONTRACT / NO ARCHITECTURE REOPEN**  
Applies to: optional manual/supervised tools such as AniJam that bundle scene generation, character/style consistency, motion/camera assistance, lip sync and timeline editing over one or more underlying generative models.

This addendum does not create a new core artifact or responsibility domain. It clarifies how an aggregated creative workbench may participate in the existing Generative Cinematic Video capability.

## 1. Core Principle

> A workbench may execute an approved visual intent. It may not become a second story director, spatial authority, factual authority or final post authority.

## 2. Selected Topology

```text
Video Director
  ├─ Blender Spatial & Camera Specialist
  ├─ 2D Motion / Compositing
  └─ Generative Cinematic Video
       ├─ Direct Provider Adapter
       └─ Optional Workbench Route
            └─ AniJam [current candidate]
```

The Direct Provider route remains available even if a workbench is used.

## 3. Workbench Execution Classes

- `WB-EXPLORE` — non-canonical ideation; whole-script or broad concept input allowed; outputs cannot be selected until remapped to canonical Visual Plan.
- `WB-CANDIDATE` — approved Visual Work Order is used to create one or more candidate production assets.
- `WB-PREASSEMBLY` — selected candidate assets may be arranged for preview; this is not the canonical final timeline.
- `WB-AUTOMATED` — reserved for a future tool with verified API/job/provenance contracts. AniJam is not currently promoted to this class.

## 4. Authority Matrix

| Responsibility | Canonical owner | Workbench authority |
|---|---|---|
| factual claim | Evidence Pack / Fact Governance | none |
| explanation order / qualifier | Story Pack | none |
| shot/work-order intent | Visual Plan / Video Director | execute within allowed variation |
| topology / structure / spatial locks | Spatial / Asset Bible | none |
| generated-candidate creation | Production Pack route | yes |
| shot-local lip sync / temp voice | production candidate only | yes, non-final |
| final voice/music/SFX/caption timing | Audio & Post | none |
| publish selection / rights / disclosure | Review & Run Ledger / Governance | none |

## 5. Default Context Packet

A canonical workbench execution receives only:
1. work-order ID and approved objective;
2. linked claim qualifier when needed for visual truth;
3. reconstruction / truth level;
4. required references and hard locks;
5. start/end semantic state;
6. camera intent;
7. allowed variation;
8. forbidden changes;
9. duration/output intent.

Do not default to full-project or full-script context.

## 6. Shadow-Authority Guard

If the workbench automatically proposes:
- new scenes;
- reordered beats;
- new dialogue;
- new camera sequence;
- new visual interpretation;

those proposals are `NON-CANON` until explicitly accepted into the correct upstream artifact by its owner.

A convenience-generated shot list cannot silently overwrite the Visual Plan.

## 7. Workbench Provenance Extension to P6

For workbench-assisted attempts, P6 may carry child fields:
- execution route/class;
- workbench identity;
- project/scene reference if available;
- tool snapshot date/version if available;
- underlying provider/model if exposed, otherwise `NOT_EXPOSED`;
- prompt/instruction hash;
- reference/input bindings;
- export timestamp/settings;
- reproducibility level;
- rights review state;
- disclosure class.

`NOT_EXPOSED` is an explicit value, not missing data.

Selection rules:
- fact-bearing/spatial-truth shots require sufficient direct provenance and deterministic evidence; opaque workbench output is not acceptable as authority;
- non-factual cinematic/reconstruction candidates may use `PARTIAL_WORKBENCH` provenance when tool identity, inputs, output, rights and QA are preserved;
- `INSUFFICIENT` provenance blocks final selection.

## 8. Stale Propagation

### If Story/Visual intent changes
Affected workbench attempts become STALE, but unrelated Blender/2D assets remain valid.

### If only workbench model/setting changes
Only affected candidate attempts and continuity neighbors require review; Evidence/Story/Spatial do not become stale by default.

### If Spatial hard lock changes
Any workbench shot using the old spatial anchor becomes STALE even if visually convincing.

### If Post timing changes
Workbench source clips remain valid unless the change requires new source duration/action; final timeline is re-edited in Post.

## 9. Fallback Chain

For a workbench-routed cinematic shot:

`AniJam candidate → direct provider candidate → still/composite → omit non-essential cinematic shot`

If the cinematic shot is not necessary to explain the central mechanism, failure of AniJam must never block episode truth.

## 10. Promotion Gate

AniJam remains optional until a fixed benchmark audition measures:
- usable-output ratio;
- consistency benefit;
- edit/revision burden;
- cost including rejected attempts;
- provenance completeness;
- rights/disclosure clarity;
- export reliability;
- time saved versus direct-provider workflow.

Automation is separately gated on a verified API/job lifecycle and machine-readable provenance.

## 11. Stop Rule

Do not create:
- AniJam Orchestra;
- AniJam Agent by default;
- AniJam-specific core artifact;
- AniJam-owned Story/Visual state;
- AniJam-only pipeline.

If future evidence proves a distinct authority/scaling/security need, reopen only the failing boundary.

## Verdict

**PATCH, not NEW DESIGN.**

The closed studio/harness architecture remains valid. AniJam is integrated conceptually as an optional supervised workbench subroute under Generative Cinematic Video.
