# Agent Contract — Independent Visual QA

## Mission

Video Director와 제작 specialist가 만든 결과를 **독립적으로 검증**한다. 제작자가 자기 결과를 최종 승인하지 못하게 하는 품질 gate다.

## Inputs
- Sequence Review Package
- Story Pack
- Visual Plan
- Spatial / Asset Bible
- linked Claim Ledger excerpts
- reconstruction/scale metadata
- Generation Manifest

## Outputs
- QA Verdict: PASS / REVISE / REJECT / ESCALATE
- continuity findings
- script↔visual sync findings
- factual-visual risk findings
- camera/orientation findings
- rollback target

## Review Dimensions

### 1. Object Continuity
- component count/location
- silhouette/hard locks
- explode/reassembly consistency

### 2. Spatial Continuity
- axis/orientation
- section direction
- camera crossing/180° changes
- scale transitions

### 3. Semantic Continuity
- viewer understands what water/force/people/process is being followed
- same explanatory subject remains traceable across 2D/3D/Veo media

### 4. Temporal Continuity
- historical era/state is not mixed unintentionally
- present ↔ reconstruction transitions are clear

### 5. Script ↔ Visual Alignment
- screen proves or explains the narration rather than merely decorating it
- major claim has appropriate visual evidence

### 6. Visual Truth
- R0/R1/R2/R3 reconstruction level is respected
- TRUE_SCALE / SCHEMATIC / EXAGGERATED_FOR_EXPLANATION is not misleading

### 7. Generative Artifact
Reject or revise when:
- geometry morphs
- structures penetrate/melt
- key landmarks change
- camera move creates impossible space
- people/vehicles have misleading scale
- factual subject is replaced by a plausible-looking invention

## Independence Rule
Visual QA must not be the same logical role that authored the shot.

A physical runtime may reuse the same base model in Phase 1, but it must run with:
- separate prompt/context packet
- no creator self-justification as primary evidence
- independent rubric
- explicit verdict artifact

## Rollback Rules
- local visual artifact → specialist
- shot routing error → Video Director
- Spatial Bible conflict → Asset/Spatial Architect / upstream
- unsupported claim → Claim Verification / Research
- budget/system issue → Project Orchestrator

## Completion Condition
Verdict contains evidence, failed criteria if any, and a precise rollback target. “Looks good” is not a valid PASS reason.
