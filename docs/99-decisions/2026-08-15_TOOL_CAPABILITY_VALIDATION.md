# 2026-08-15 — Tool Capability Validation & Process Deviation

This decision record supplements `CHANGE_LOG.md` for the current empirical-validation pass.

## Decision — Current provider capabilities remain behind adapters

- Previous decision / assumption: Architecture was closed at Design Closure 0.6, with Blender as deterministic spatial truth and Google video/TTS/music providers intentionally left swappable.
- New decision: Keep that architecture unchanged. Current official capabilities strengthen the adapter boundary: general Google video may route to Gemini Omni Flash while Veo 3.1 is reserved for capability-specific needs; TTS and music remain provider-swappable.
- Trigger / evidence: Current official Google/Blender documentation reviewed on 2026-08-15.
- Why changed: No topology change is needed, but stale assumptions such as “Veo is always the default” must not leak into Phase 1 implementation.
- Impact: Future provider registry, Generation Manifest, model selection, cost accounting and audition plan.
- Reversible?: Yes; capability facts are dated and must be refreshed.
- Rollback path: Supersede this snapshot with a newer official capability registry.
- Affected stages/files: `docs/09-validation/TOOL_CAPABILITY_REGISTRY_2026_08_15.md`; future Phase 1 provider adapter implementation.
- Follow-up validation: Refresh immediately before implementation and run fixed-input provider auditions.

## Process Deviation — Temporary direct-main file writes during branch setup

- Intended plan: All validation documentation changes should occur on a dedicated branch, then be reviewed via diff/PR before main merge.
- What happened: During connector branch setup, temporary probe/noop files were accidentally created directly on `main` in separate commits.
- Recovery: Each temporary file was immediately deleted. The final main working tree contains none of those temporary files.
- User/product impact: No project design, source artifact, implementation code, or persistent file content was changed by the probes. Git history contains the transient create/delete commits.
- Why it happened: Incorrect write-action target was selected while attempting to establish a new branch through the connector.
- Prevention: After this incident, branch creation was performed explicitly through the GitHub `create_branch` action before any file writes. Future writes must verify the target branch name before invoking a contents mutation.
- Reversible?: The working tree recovery is complete. Rewriting main history solely to erase harmless transient commits is not justified.
- Affected files/stages: Git history only; no final project file.
- Follow-up validation: PR diff must contain only intentional validation documentation before merge.
