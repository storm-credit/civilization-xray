# 2026-08-15 — Operational Hardening Rules

- Previous decision / assumption: Design Closure 0.6 had closed the studio architecture and already covered design-first work, evidence gates, provenance, stale propagation, retry concepts, and governance. Some cross-project execution safety rules remained implicit rather than top-level operating law.
- New decision: Add seven cross-cutting operational rules to `CLAUDE.md`: minimal-change/blast-radius control, no silent fallback, reproducibility/resumability/idempotency, retry-cost-time ceilings, secrets/credentials handling, dependency-aware stale propagation, and Definition of Done as an evidence bundle.
- Trigger / evidence: User re-audited the working-method checklist and asked whether further rules should be added. Review of the current `CLAUDE.md` showed these concerns were present only partially or indirectly.
- Why changed: These rules reduce failure modes that usually appear only after automation begins: accidental broad refactors, hidden provider degradation, unreproducible outputs, runaway retries/costs, credential leakage, over-broad regeneration, and unsupported completion claims.
- Impact: Applies to future implementation, research, content production, agent execution, media generation, and release workflows. Does not reopen or expand the four-orchestra studio architecture.
- Reversible?: Yes. Individual rules can be simplified if prototype evidence shows unnecessary burden, but silent fallback, credential safety, and evidence-based completion should remain strong defaults.
- Rollback path: Revert the `Operational Hardening Rules` subsection in `CLAUDE.md` and this decision record.
- Affected files/stages: `CLAUDE.md`; future Phase 1 implementation planning and runtime contracts.
- Follow-up validation: During Phase 1, verify one provider failure, one retry-budget exhaustion, one stale-field change, one resumable interrupted run, and one evidence-bundle completion report.