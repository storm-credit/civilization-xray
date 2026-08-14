# Civilization X-Ray — Working Rules Audit

Date: 2026-08-14
Status: **PASS with handoff/status corrections applied**

Purpose: re-check the user's project-working rules and methodology references before continuing in a fresh Claude/Claude Code session.

## Audit Summary

| Requirement | Status | Effective location / action |
|---|---|---|
| Blind-spot sweep | PASS | `CLAUDE.md`, `docs/01-discovery/*` |
| Pre-implementation trap / pre-mortem | PASS | `CLAUDE.md`, risk/pre-mortem design |
| 4 design alternatives | PASS | consequential design decisions; avoid fake four-way duplication |
| User intent / audience / success interview | PASS | `CLAUDE.md`; now explicitly prohibits repeated questions already answered |
| Reference-first comparable work | PASS | `REFERENCE_METHODS.md`; software/video/domain-specific reference rule clarified |
| Record where/why plan changed | PASS | `docs/99-decisions/CHANGE_LOG.md` |
| Keep top-level rules in CLAUDE.md | PASS | `CLAUDE.md` updated |
| Meta prompting: context dump | PASS | `CLAUDE.md` |
| Meta prompting: prompt refinement | PASS | `CLAUDE.md` |
| Meta prompting: output review | PASS after correction | explicit `Output Review` section added |
| AI asks for missing context | PASS after correction | asks only when missing context materially changes result; no redundant questions |
| Verifiable success criteria | PASS | universal prompt envelope / quality gates |
| Goal prompt stop condition | PASS | environment-specific prompt conversion |
| Agent/coding constraints | PASS | file scope / forbidden area / verification evidence |
| Image prompt composition/style/light/camera | PASS | image prompt conversion rules |
| Research source/scope/validation rules | PASS | research prompt conversion rules |
| Harness only after enough discovery | PASS | Harness Readiness Gate and Validation 0.5 |
| Evidence before completion claims | PASS | top-level non-negotiable rule |
| Automatic progress without needless blocking | PASS after correction | bounded assumptions may proceed; blocking unknowns only are asked |

## Methodology Reference Verification

Verified GitHub repositories:

1. `multica-ai/andrej-karpathy-skills`
2. `bradautomates/claude-video`
3. `obra/superpowers`
4. `Egonex-AI/Understand-Anything` — current lineage of the former `Lum1104/Understand-Anything`
5. `rohitg00/agentmemory`

These remain methodology references, not code-copy mandates.

## Internal Reference Boundaries

- `storm-credit/askanything_video_generator`: selected provider/Veo operational infrastructure only; do not inherit Shorts editorial policy.
- `storm-credit/oddengine`: executable artifact gates, continuity bridge and durable prompt/reference provenance only; do not inherit MV ontology/pipeline.

## Corrections Made for Claude Handoff

1. Removed stale implication that the project is still at initial Phase 0 discovery.
2. Current state is now explicit: architecture design + Validation 0.5 complete; implementation not started/authorized.
3. Added cross-assistant continuation rule so new sessions use repository truth before questioning the user.
4. Added explicit output-review step to meta prompting.
5. Added no-repeated-question rule and bounded-assumption automatic-progress rule.
6. Clarified reference analog by domain.
7. Updated Understand-Anything lineage.
8. Added `docs/00-project/CLAUDE_HANDOFF.md` with a paste-ready Claude bootstrap prompt.

## Remaining Gap

The only material empirical gap is still the same one already recorded by Validation 0.5:

> frame-level + timestamp-transcript reverse engineering of a full 10-video benchmark corpus is PARTIAL pending direct media access.

This does **not** invalidate the current harness topology. New evidence may refine camera/script-visual grammar and contracts; architecture should not be redesigned without evidence.

## Verdict

**PASS.**

The user's working methodology is represented strongly enough for a fresh Claude session to continue without reconstructing the prior chat. The new Claude session should start from repository state, not restart brainstorming or implementation.
