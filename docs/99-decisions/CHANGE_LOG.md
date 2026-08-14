# Change & Deviation Log

계획이 바뀌거나 처음 가정과 다른 결과가 나왔을 때 반드시 기록한다.

## Template

### YYYY-MM-DD — Decision title

- Previous decision / assumption:
- New decision:
- Trigger / evidence:
- Why changed:
- Impact:
- Reversible?:
- Rollback path:
- Affected stages/files:
- Follow-up validation:

---

## 2026-08-14 — Repository initialized

- Previous decision / assumption: 새 AI 롱폼 콘텐츠 프로젝트를 별도 저장소로 구성한다.
- New decision: 프로젝트 저장소명을 `civilization-xray`로 확정.
- Trigger / evidence: 건축만이 아니라 도시·역사·인프라까지 포괄하면서도 “내부 원리를 해부한다”는 정체성을 유지하기 위해 선택.
- Why changed: 해당 없음. 초기 결정.
- Impact: 프로젝트 문서/브랜드 코드네임 전체.
- Reversible?: Yes.
- Rollback path: 저장소 rename 및 문서 일괄 수정.
- Affected stages/files: all design docs.
- Follow-up validation: 사용자 인터뷰에서 content center of gravity를 확인.

## 2026-08-14 — Harness must follow completed discovery

- Previous decision / assumption: 멀티에이전트/하네스가 필요할 가능성이 높다.
- New decision: 에이전트 수나 topology를 미리 고정하지 않고, 브레인스토밍·맹점 훑기·pre-mortem·성공조건이 충분히 정리된 뒤 Harness Readiness Gate를 통과해야만 하네스 구조를 확정한다.
- Trigger / evidence: 사용자가 “충분히 브레인스토밍과 맹점 훑기가 완성되면 그에 맞는 하네스 구조를 잡는 것이 중요하다”고 명시.
- Why changed: 도메인을 하네스에 끼워 맞추는 premature architecture를 방지하기 위해.
- Impact: Phase 0 workflow, CLAUDE.md, Discovery Gates, Harness Design Policy.
- Reversible?: Yes, but changing requires explicit rationale.
- Rollback path: Harness Readiness Gate 수정 + CLAUDE.md 동기화.
- Affected stages/files: `CLAUDE.md`, `docs/01-discovery/DISCOVERY_GATES.md`, `docs/02-harness/HARNESS_DESIGN_POLICY.md`.
- Follow-up validation: 대표 episode/visual grammar 분석 후 실제 책임 경계가 드러나는지 검증.
