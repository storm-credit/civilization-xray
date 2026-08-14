# Validation 0.5 — Artifact Pruning Review

## Objective

Phase 0의 logical artifact 12종은 책임과 lineage를 이해하기에는 좋지만, Phase 1에서 물리 파일 12개를 매 episode마다 만들면 과설계가 될 수 있다.

Karpathy-style simplicity principle에 따라 paper walkthrough 결과를 바탕으로 **논리적 경계는 유지하되 물리 산출물은 줄인다.**

---

# Original Logical Artifacts

1. Topic Brief
2. Research Dossier
3. Claim Ledger
4. Beat Map
5. Narration Script
6. Script ↔ Visual Map
7. Hero Object Bible
8. Shot Spec Pack
9. Previs Pack
10. Generation Manifest
11. QA Reports
12. Episode Run Ledger

문제:
- logical separation이 곧 physical file separation일 필요는 없음.
- 많은 작은 파일은 agent context selection과 versioning 자체를 복잡하게 만들 수 있음.

---

# Selected Phase 1 Physical Artifact Set

## P1. Episode Brief

Combines:
- Topic Brief
- scope lock
- explanatory unit
- case anchor
- episode grammar
- topic score
- early risks

Why combined:
모두 episode 시작 전 editorial scope decision.

Must preserve logical fields separately inside artifact.

## P2. Evidence Pack

Combines:
- Research Dossier
- Claim Ledger
- Source Pack/index
- uncertainty/conflict map

Why combined:
claim과 source를 분리된 파일로 옮기면 provenance sync 오류 가능.

Rule:
각 claim row가 source id를 직접 reference.

## P3. Story Pack

Combines:
- Beat Map
- Narration Script
- claim links

Why combined:
beat 변경과 narration 변경이 강하게 결합됨.

Rule:
Narration unit마다 claim id 유지.

## P4. Visual Plan

Combines:
- Script ↔ Visual Map
- Shot Specs
- visual truth level
- scale treatment
- camera/transition plan

Why combined:
script unit의 visual objective와 shot spec이 서로 분리되면 중복/불일치 가능.

Exception:
큰 episode에서 shot count가 과도하면 shot table을 child artifact로 분리 가능.

## P5. Spatial / Asset Bible

Replaces:
- Hero Object Bible

Supports:
- hero_scope: object | system | component
- canonical geometry
- hard/soft/free locks
- spatial axes
- semantic continuity anchors
- reconstructed/unknown zones
- asset references

Why standalone:
여러 shot이 공통으로 읽는 stable artifact이고 expensive generation 전에 lock됨.

## P6. Production Pack

Combines:
- Previs Pack index
- Generation Manifest
- selected asset versions
- production state
- tool/model/prompt references

Binary media 자체를 한 파일에 넣는 뜻은 아님.
이 artifact는 asset registry/index 역할.

## P7. Review & Run Ledger

Combines:
- QA reports index/verdicts
- stage transitions
- human approvals
- retries
- costs
- deviations

Why combined:
“무슨 일이 일어났는가?”를 한 곳에서 추적.

Independent review rubric은 별도 stable project rubric으로 유지.

---

# Result

Logical concepts: 유지
Physical episode-level core artifacts: **12 → 7**

```text
Episode Brief
   ↓
Evidence Pack
   ↓
Story Pack
   ↓
Visual Plan ↔ Spatial / Asset Bible
   ↓
Production Pack
   ↓
Review & Run Ledger
```

---

# Why Not Reduce Further?

## Evidence Pack + Story Pack merge?
Reject.

Reason:
- research lock과 editorial writing lock의 authority가 다름
- script가 source material을 덮어써서는 안 됨

## Story Pack + Visual Plan merge?
Reject initially.

Reason:
- narration 변경과 expensive visual planning 사이 gate 필요
- Script Lock을 유지해야 함

## Visual Plan + Spatial Bible merge?
Reject.

Reason:
- Spatial Bible은 many-shot shared invariant
- Visual Plan은 shot-specific mutable state

## Production Pack + Ledger merge?
Reject.

Reason:
- production desired state와 execution/audit history를 구분

---

# Child Artifacts Allowed

대규모 episode에서 필요 시:
- evidence appendix
- individual source extract
- complex shot table
- multiple Hero Component sheets
- QA report detail

하지만 child artifact는 기본 템플릿이 아니라 complexity trigger가 있을 때만 추가.

---

# Complexity Triggers

## Split Visual Plan when
- shot count/sections가 한 context packet에 부담
- 서로 독립적으로 제작 가능한 visual sequence가 있음

## Split Spatial Bible when
- multiple unrelated hero systems
- distinct historical eras with incompatible geometry

## Split Evidence Pack when
- source corpus가 너무 커 analyst context를 압도
- sub-question별 independent domain expert 필요

---

# Harness Impact

Artifact Blackboard는 7개 core artifact version을 중심으로 운영.

각 capability가 읽는 기본 범위:

- Topic Strategy → Channel DNA + Episode Brief
- Research → Episode Brief + Evidence Pack
- Narrative → locked Evidence Pack + Story Pack
- Script–Visual → Story Pack + relevant Evidence claims + Visual Plan
- Spatial → Visual Plan + Evidence diagrams + Spatial Bible
- Production → locked Visual Plan + Spatial Bible + Production Pack
- QA → relevant locked artifacts + Review Ledger

Director:
- artifact content 전체를 항상 읽지 않고 status/version/verdict 중심.

---

# Decision

**Adopt 7-core-artifact model for Phase 1 design.**

This is a simplification, not a loss of logical controls.
