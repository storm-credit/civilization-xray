# 2026-08-22 — AniJam Hybrid Workbench Routing

- Previous decision / assumption: Generative cinematic video was routed primarily through direct provider adapters such as current Google video models, while named SaaS tools were optional and no single provider was mandatory.
- New decision: Add an optional supervised creative-workbench subroute under the existing Generative Cinematic Video capability. AniJam is the current candidate at `W0 OPTIONAL MANUAL/ASSISTED WORKBENCH`; direct provider adapters remain the core automation/provenance path.
- Trigger / evidence: User identified a current video workflow referencing AniJam. Review of AniJam official pages showed script/image/audio-to-animation, automatic scene breakdown, character/style consistency claims, motion/camera assistance, lip sync, timeline editing and a multi-provider ecosystem.
- Four alternatives considered: direct providers only; AniJam-first; exploration-only AniJam; hybrid direct-provider + AniJam workbench. Hybrid selected.
- Why changed: AniJam may reduce app switching and accelerate supervised multi-scene cinematic candidate production, but AniJam-first would introduce shadow-authority and provenance/runtime risks.
- Authority rule: AniJam may execute approved Visual Work Orders but may not own factual claims, Story Pack structure, canonical shot planning, Spatial/Asset Bible truth, or final Audio/Post timeline. Whole-script scene breakdown is non-canonical unless promoted by the relevant upstream owner.
- Provenance rule: Record workbench identity/project/scene references, inputs, output, rights/disclosure state and underlying provider/model when exposed. If not exposed, record `NOT_EXPOSED`; do not guess. Opaque output cannot become factual/spatial authority.
- Runtime boundary: A stable public automation API/job/provenance contract was not verified in this review, so AniJam must not be a required runtime integration or automation dependency yet.
- Impact: `MODELING_CAMERA_RENDER_ROUTER.md`, empirical validation status, optional P6 workbench provenance child fields, future supervised tool auditions.
- Architecture impact: None. No new orchestra, agent, core artifact or physical workflow state.
- Reversible?: Yes. AniJam can be removed without changing the episode architecture because direct-provider/still/composite fallbacks remain.
- Rollback path: Remove AniJam-specific candidate references and retain the generic Generative Cinematic Video direct-provider route.
- Follow-up validation: Run one fixed non-factual historical-activity work order through direct provider, AniJam supervised workbench and still/composite fallback. Measure usable-output ratio, consistency benefit, edit burden, effective cost, provenance completeness, export reliability and time saved.
- Promotion gate: Supervised standardization requires measured benefit. Automated integration additionally requires verified API/auth/job lifecycle, machine-readable output identity/provenance, retry/error semantics and quota/cost observability.
