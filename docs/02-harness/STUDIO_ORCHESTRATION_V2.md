# Studio Orchestration V2

Status: **Selected studio-level design — no implementation code**

## Executive Decision

Civilization X-Ray는 하나의 거대한 agent swarm이 아니라, **네 개의 책임 오케스트라 + 독립 governance + shared memory/library**로 운영한다.

```text
                         USER
                          │
                          ▼
                ┌────────────────────┐
                │ PROJECT ORCHESTRATOR│
                └─────────┬──────────┘
                          │
      ┌───────────────────┼────────────────────┐
      │                   │                    │
      ▼                   ▼                    ▼
┌─────────────┐     ┌─────────────┐      ┌─────────────┐
│ EDITORIAL & │     │   VISUAL    │      │ AUDIO & POST│
│ RESEARCH    │     │ PRODUCTION  │      │ ORCHESTRA   │
└──────┬──────┘     └──────┬──────┘      └──────┬──────┘
       │                   │                    │
       └───────────────────┼────────────────────┘
                           ▼
                  ┌────────────────┐
                  │ RELEASE &      │
                  │ LEARNING       │
                  └────────────────┘

Cross-cutting independent plane:
  FACT / RIGHTS / QUALITY GOVERNANCE

Shared service:
  ASSET / MEMORY / PROMPT / RIGHTS REGISTRIES
```

---

# 1. Why Four Orchestras

Top-level unit를 역할마다 쪼개지 않는다.

## O1 Editorial & Research
Goal: **무엇을 말할 것인가, 왜 믿을 수 있는가, 어떤 순서로 이해시킬 것인가**

## O2 Visual Production
Goal: **그 설명을 공간적으로 정확하고 영화적으로 어떻게 보여줄 것인가**

## O3 Audio & Post
Goal: **완성된 narration/visual assets를 어떻게 하나의 감정·리듬·소리·편집 경험으로 조립할 것인가**

## O4 Release & Learning
Goal: **영상의 약속을 어떻게 정확하게 패키징하고, 공개 후 무엇을 학습할 것인가**

These responsibilities have different failure modes and different lock points, so one director should not silently own all four.

---

# 2. Project Orchestrator

Owns only cross-orchestra coordination:
- episode state
- gate transitions
- artifact version lineage
- budget ceiling
- retry/escalation
- stale dependency detection
- human approval state
- orchestration ledger

Does NOT:
- choose facts by itself
- rewrite script silently
- override Video Director camera judgment
- approve its own final QA
- optimize title/thumbnail against factual constraints

---

# 3. O1 — Editorial & Research Orchestra

Director: **Editorial Director**

Logical roles:
1. Topic Strategist
2. Research Specialist
3. Claim Verifier
4. Narrative Architect / Script Writer
5. Script Editor / Retention Reviewer
6. Script ↔ Visual Architect

### Internal independence
Claim Verifier must be able to reject Research Specialist findings.
Script Editor must be able to reject/return Script Writer output.

### Output contract
Produces/locks:
- Episode Brief
- Evidence Pack
- Story Pack
- Script ↔ Visual intent in Visual Plan

### Handoff to Visual
Video Director receives:
- locked narration units
- claim links
- explanatory objective
- reconstruction/uncertainty
- beat timing intent

---

# 4. O2 — Visual Production Orchestra

Director: **Video Director**

Core specialist roles already defined:
- Blender Spatial & Camera Specialist
- Veo Cinematic Camera Specialist
- 2D / Motion Graphics capability
- Independent Visual QA

Owns:
- shot language
- media routing
- camera grammar
- spatial continuity
- transitions
- previs
- visual pacing proposal

Output:
- Visual Plan
- Spatial / Asset Bible
- visual Production Pack material
- approved shot assets / proxies

Does NOT own:
- final narration performance
- music
- final picture edit lock
- publish package

---

# 5. O3 — Audio & Post Orchestra

Director: **Post-Production Director**

Logical roles:
1. Picture Editor
2. Narration & TTS Specialist
3. Music Supervisor / Score Designer
4. Sound Designer
5. Mix / Master / Caption Specialist

Why combined:
Picture timing, voice timing, score cue placement and SFX rhythm are interdependent. Splitting Audio and Post into separate top-level orchestras creates unnecessary sync overhead for Phase 1.

Owns:
- rough/fine edit
- voice production
- pronunciation
- music cue map realization
- SFX
- audio sync
- dialogue-first mix
- captions/subtitles
- final master assembly

### Post cannot alter factual meaning silently
If edit reorders explanation or removes qualifying language, return to Editorial Gate.

### Output
Production Pack gains:
- Voice Pack
- Music Cue Sheet
- SFX Plan
- Edit Decision List
- timeline/master state
- caption state
- audio provenance references

---

# 6. O4 — Release & Learning Orchestra

Director: **Release Director**

Logical roles:
1. Packaging Strategist
2. Title / Thumbnail Specialist
3. Publish Metadata Specialist
4. Analytics & Learning Specialist

Owns:
- title candidates
- thumbnail concepts
- description/source notes
- chapters
- publish checklist
- derivative clip candidates
- post-publish data interpretation
- learning proposals

Does NOT:
- invent stronger claims than the episode supports
- modify final factual content
- automatically write channel DNA from one episode anomaly

Output:
- Release Package
- post-publish learning report
- proposed Channel DNA updates

---

# 7. Governance Plane

Governance is **not another creative orchestra**.
It has reject authority where independence matters.

## Fact Governance
- claim lineage
- source conflict
- narration factual integrity
- packaging claim integrity

## Rights Governance
- footage
- images
- 3D assets
- generated media
- music
- SFX
- voice/TTS consent/license
- required attribution

## Quality Governance
Separate verdict dimensions:
- factual
- visual continuity
- cross-media semantic sync
- editorial clarity
- audio intelligibility
- rights/provenance

One PASS score cannot hide a CRITICAL fail in another dimension.

---

# 8. Shared Asset & Memory Service

Not an autonomous director.
Provides versioned registries.

## Registries
- Project Constitution
- Channel DNA
- Evidence/source index
- Spatial assets
- camera rigs
- Veo prompt lessons
- 2D templates
- Sonic Bible
- music motifs
- SFX library
- Voice Bible
- pronunciation glossary
- prompt blueprints
- rights/provenance manifests
- failure/recovery memory

## Status lifecycle
Candidate → Reviewed → Approved → Deprecated / Superseded

No asset becomes reusable merely because it appeared in a published episode.

---

# 9. Main Episode Handoff Flow

```text
Project Orchestrator
        │
        ▼
Editorial & Research
        │
        │  Episode Brief / Evidence / Story
        ▼
     GATE E
        │
        ▼
Visual Production
        │
        │  Previs / Spatial Bible / Shots
        ▼
     GATE V
        │
        ▼
Audio & Post
        │
        │  Voice / Music / SFX / Fine Cut / Master
        ▼
     GATE P
        │
        ▼
Release & Learning
        │
        │  Packaging / Publish / Analytics
        ▼
      RELEASE
        │
        ▼
Learning proposal → Project Orchestrator → Channel DNA review
```

Governance can block at every major gate.

---

# 10. Cross-Orchestra Stale Dependency Rules

Examples:

## Script text changes after voice generation
Mark stale:
- Voice Pack
- captions
- music cue timing where affected
- edit timing
- related shots if duration/meaning changed

## Spatial Bible changes
Mark stale:
- affected Blender shots
- visual QA
- composites using registered geometry
- packaging if thumbnail uses affected geometry

## Final edit changes narration order
Requires:
- Editorial semantic review
- audio cue re-check
- caption regeneration/check

## Title/thumbnail claim changes
Requires Fact Governance check.

---

# 11. Physical Agent Count Policy

This hierarchy describes **roles, not mandatory LLM process count**.

Phase 1 can start with fewer physical agents/processes:

- Project Orchestrator: 1
- Editorial Director + Topic/Script functions: may be combined
- Claim Verifier: keep logically independent
- Video Director: 1
- Blender Specialist: specialist tool context
- Veo Specialist: specialist tool context
- Visual QA: independent review context
- Post Director + Picture/Audio: may be combined initially
- Rights/Final QA: independent verdict context
- Release Director + Packaging/Analytics: may be combined

Split when:
- context is too large
- tool specialization differs
- reviewer independence required
- throughput requires parallelism

---

# 12. Studio Completion Boundary

A video is not complete when shots are generated.

Complete means:
- Editorial lock passed
- visual proof exists
- narration approved
- picture edit locked
- music/SFX/mix approved
- captions checked
- rights manifest complete
- fact/quality governance pass
- title/thumbnail package pass
- publish package ready
- learning capture slot prepared

---

# 13. No More Top-Level Orchestras by Default

Do NOT add separate top-level orchestras for:
- thumbnail only
- music only
- Blender only
- analytics only
- prompt engineering only
- asset library only

They are specialist roles/services within the four responsibility domains.

A fifth creative orchestra requires pilot evidence that one selected domain cannot maintain coherent ownership.