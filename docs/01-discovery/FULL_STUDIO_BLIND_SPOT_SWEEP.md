# Full Studio Blind-Spot Sweep

Status: **Design audit — no implementation code**

## Executive Finding

Civilization X-Ray의 기존 설계는 Research/Script 논리 capability와 Blender/Veo 중심 Visual Production 계층은 강하지만, 완성된 롱폼을 실제로 출고하기 위한 아래 책임이 상대적으로 약하다.

1. Editorial/Research가 아직 production-agent 수준으로 구체화되지 않음
2. Narration/TTS ownership이 없음
3. Music / score / sound design ownership이 없음
4. Picture edit / final assembly ownership이 없음
5. Audio mix/master, captions, final delivery ownership이 없음
6. Thumbnail/title/release package ownership이 없음
7. Post-publish analytics가 학습으로 되돌아가는 책임자가 없음
8. Rights/provenance가 단계별 체크 항목은 있으나 전 파이프라인 독립 governance로 묶이지 않음
9. Asset reuse / sonic identity / camera rig / prompt learning을 관리하는 library service가 명확하지 않음

결론:

> 오케스트라는 무한히 늘리지 않는다. **4개의 책임 오케스트라 + 1개의 cross-cutting governance plane + shared library/memory service**로 닫는다.

---

# 1. Proposed Studio-Level Responsibility Map

## O1 — Editorial & Research Orchestra
Owns:
- topic selection
- research
- claim verification
- story architecture
- script
- retention editing
- script ↔ visual intent

## O2 — Visual Production Orchestra
Owns:
- shot design
- spatial truth
- Blender
- Veo/generative cinema
- 2D explanatory motion
- visual continuity

## O3 — Audio & Post Orchestra
Owns:
- narration performance/TTS
- pronunciation
- score/music
- sound design
- picture assembly/edit
- sync
- mix/master
- captions/subtitles
- final master package

## O4 — Release & Learning Orchestra
Owns:
- title/thumbnail package
- chapters/description/source notes
- publication checklist
- derivative clip candidates
- post-publish metrics
- audience feedback synthesis
- channel-DNA learning proposal

## G1 — Fact / Rights / Quality Governance Plane
Independent reject authority across all orchestras.

Owns:
- factual lineage
- reconstruction labeling
- asset/music/SFX rights provenance
- final claim integrity
- final continuity/quality verdicts

## S1 — Shared Asset & Memory Service
Not an orchestra.

Owns registries for:
- channel DNA
- spatial asset library
- camera rig library
- visual style bible
- music/sonic motif library
- pronunciation glossary
- prompt/version registry
- failure/recovery memory
- rights/provenance manifest references

---

# 2. Critical Blind Spots

## B01 — Music is treated as decoration instead of narrative structure

Risk: HIGH

Failure mode:
- 음악이 마지막에 아무 트랙이나 깔림
- hook/reveal/payoff와 음악의 구조가 충돌
- narration intelligibility 저하
- 모든 영상이 같은 감정 밀도로 들림

Required control:
- Story Pack에서 **Audio Beat Map** 파생
- 각 cue에 narrative function을 명시
- music cue는 장면이 아니라 story beat에 연결
- silence/near-silence도 의도된 cue로 취급

---

## B02 — Narration identity has no owner

Risk: CRITICAL

Failure mode:
- 같은 채널인데 화마다 음성 톤/속도/호흡이 변함
- 역사/지명/기술용어 발음이 흔들림
- 대본 수정 후 TTS와 edit가 어긋남

Required control:
- Narration & TTS Specialist
- Voice Bible
- pronunciation glossary
- pace/emphasis annotations
- final script version lock before final voice generation

---

## B03 — Picture editing is nobody's explicit job

Risk: CRITICAL

Failure mode:
- 좋은 Blender 컷과 Veo 컷이 있어도 10분짜리 영상이 지루함
- narration과 shot duration이 맞지 않음
- transition이 많아도 정보 rhythm이 없음

Required control:
- Post-Production Director / Picture Editor ownership
- rough cut → pacing review → fine cut → audio lock → final master state
- no direct jump from generated shots to publish

---

## B04 — Sound effects may create fake physical certainty

Risk: HIGH

Failure mode:
- 실제로 확인되지 않은 역사적/기계적 소리를 사실처럼 제시
- 과도한 whoosh/impact가 다큐 신뢰감 훼손

Required control:
- SFX truth class
  - documented/recorded
  - plausible reconstruction
  - illustrative/design sound
- misleading sound reject rule

---

## B05 — Music/SFX copyright and Content-ID risk

Risk: CRITICAL

Failure mode:
- 출처는 있는데 commercial use 권한이 불명확
- 생성 음악/라이브러리 음원이 추후 claim 발생
- license version이 바뀌었는데 기록 없음

Required control:
- every audio asset has provenance entry
- source, creator/tool, license/terms snapshot date, commercial-use status, edit rights, attribution requirement
- unresolved rights => publish block

---

## B06 — Final audio mix can destroy an otherwise good episode

Risk: HIGH

Failure mode:
- music masks narration
- SFX peak가 지나치게 큼
- section마다 loudness가 다름
- mobile speaker에서 이해 안 됨

Required control:
- dialogue-first mix hierarchy
- narration intelligibility gate
- platform delivery target stored in delivery spec, not hard-coded into creative prompts
- mobile/headphone spot checks during pilot

---

## B07 — No sonic brand identity

Risk: MEDIUM

Failure mode:
- 화면은 Civilization X-Ray인데 소리는 generic AI documentary

Required control:
- Sonic Bible
- opening identity rule
- reveal motif
- X-Ray transition motif
- restraint rules
- avoid one jingle repeated mechanically every episode

---

## B08 — No silence policy

Risk: MEDIUM

Failure mode:
- 8–15분 동안 음악이 계속 깔려 피로 증가
- 중요한 reveal에도 대비가 없음

Required control:
- silence is first-class audio state
- high-information visuals may reduce score density
- major reveal may use pre-reveal drop/space when appropriate

---

## B09 — Script changes can invalidate everything downstream

Risk: CRITICAL

Failure mode:
- narration 한 문장 수정
- shot timing, TTS, music cues, captions, edit가 모두 stale

Required control:
- artifact dependency graph
- script version referenced by Voice Pack, Edit Pack, Caption Pack, Audio Cue Sheet
- upstream change marks dependent artifacts stale

---

## B10 — Release package is an afterthought

Risk: HIGH

Failure mode:
- 완성 영상은 좋지만 제목/썸네일이 채널 약속을 전달하지 못함
- sources/chapters/description 누락

Required control:
- Release & Learning Orchestra
- Title/Thumbnail Brief derived from central question, not generated from final transcript blindly

---

## B11 — Thumbnail can contradict factual nuance

Risk: HIGH

Failure mode:
- 영상에서는 reconstruction이라고 설명했는데 썸네일은 확정 사실처럼 과장

Required control:
- Packaging must pass Fact/Rights Governance
- no claim escalation beyond approved Evidence Pack

---

## B12 — Post-publish metrics are collected but not converted into design learning

Risk: HIGH

Failure mode:
- retention graph를 보고도 다음 영상 설계가 바뀌지 않음
- 단기 CTR 때문에 channel identity가 흔들림

Required control:
- Analytics & Learning Specialist
- distinguish episode anomaly vs repeatable channel pattern
- memory update requires evidence from multiple episodes for structural rules

---

## B13 — Overfitting to metrics

Risk: HIGH

Failure mode:
- 모든 영상이 더 자극적인 hook, 빠른 컷, 과장 썸네일로 수렴

Required control:
- quality/trust guardrail cannot be overridden solely by CTR/retention
- Channel Constitution > short-term metric optimization

---

## B14 — No explicit accessibility ownership

Risk: MEDIUM

Failure mode:
- 자동자막 기술용어 오인식
- 화면 label과 narration 용어 불일치

Required control:
- caption glossary from pronunciation/term glossary
- final subtitle QA
- key meaning cannot rely on color only

---

## B15 — Cross-media continuity is not just visual continuity

Risk: HIGH

Failure mode:
- 화면은 정확하지만 narration, label, SFX, music cue가 서로 다른 의미를 암시

Required control:
- final QA checks semantic sync across narration / visual / text / sound

---

## B16 — Generated historical atmosphere may silently invent culturally wrong details

Risk: HIGH

Failure mode:
- Veo historical reconstruction visuals + period music together create false authenticity

Required control:
- reconstruction level applies to audio as well as visuals
- period/cultural specificity must be sourced or labeled as illustrative

---

## B17 — Asset library grows without curation

Risk: MEDIUM

Failure mode:
- duplicate models/music/SFX/prompts accumulate
- old bad assets reused because they are easy to find

Required control:
- asset status: candidate / approved / deprecated / superseded
- reuse requires current rights and quality status

---

## B18 — Too many agents can create coordination tax

Risk: CRITICAL

Failure mode:
- one episode needs 20 agents to agree
- overhead exceeds creative work

Required control:
- **logical roles ≠ physical agents**
- Phase 1 may combine several roles in one runtime agent/process while keeping output contracts/rubrics separate
- split only when independence, context size, specialist tool use, or reject authority requires it

---

# 3. Orchestra Count Decision

Four alternatives were considered.

## A — 2 orchestras: Editorial + Video
Reject.
Reason: Audio/post/release have no clear owner.

## B — 3 orchestras: Editorial + Visual + Post
Good minimal production core, but release/learning gets buried.

## C — 4 orchestras: Editorial + Visual + Audio/Post + Release/Learning
**Selected.**
Best separation between creation, finishing, and feedback without creating excessive top-level units.

## D — 6+ orchestras: Research, Script, Visual, Audio, Post, Growth, etc.
Reject for Phase 1.
Reason: unnecessary coordination overhead.

---

# 4. What Music Actually Means in This Project

Music is not “AI song generation.”

The system must manage:

1. **Score Intent** — why music exists in this beat
2. **Cue Sheet** — start/end/transition/energy
3. **Source Route** — original generation / licensed library / commissioned / reused approved motif
4. **Stems if available** — rhythm, texture, tonal bed, impacts separated when useful
5. **Narration Ducking Intent** — dialogue always wins
6. **Sonic Truth Level** — factual/period-specific vs illustrative
7. **Rights Manifest** — commercial rights and attribution
8. **Mix State** — draft / approved / final

Typical cue functions:
- curiosity
- scale/awe
- tension/problem
- mechanism explanation bed
- reveal
- historical transition
- payoff/resolution
- silence/space

Rule:
> 음악이 설명을 이기면 실패다. 음악은 information hierarchy를 돕는다.

---

# 5. Missing Outputs to Add to Episode Artifacts

Physical artifact count를 무작정 늘리지 않고 기존 7개 core artifact 안에 하위 sections를 둔다.

## Story Pack gains
- Audio Beat Map
- pronunciation candidates
- narration performance notes

## Visual Plan gains
- cross-media sync anchors
- transitions that require sound support

## Production Pack gains
- Voice Pack
- Music Cue Sheet
- SFX Plan
- Edit Decision List / timeline state
- Caption/Subtitles state
- Audio/rights manifest references

## Review & Run Ledger gains
- audio QA verdict
- mix QA verdict
- caption QA verdict
- release package verdict
- post-publish learning proposal

Thus the 7-artifact simplification remains intact.

---

# 6. Stop / Escalation Conditions Added

STOP or escalate when:
- no clear commercial-use right for a music/SFX/voice asset
- final narration version is not locked but final audio production is requested
- music cue materially masks or changes meaning of narration
- generated historical sound/music is being presented as documented fact without evidence
- final edit changes explanation order without Editorial approval
- thumbnail/title makes a stronger factual claim than Evidence Pack permits
- post-publish metric optimization conflicts with trust/accuracy constitution

---

# 7. Final Audit Result

Current architecture is not missing another “3D orchestra.”

It was missing the **finishing and release half of a real studio**.

Selected studio architecture:

```text
Project Orchestrator
│
├─ Editorial & Research Orchestra
├─ Visual Production Orchestra
├─ Audio & Post Orchestra
└─ Release & Learning Orchestra

Cross-cutting:
├─ Fact / Rights / Quality Governance
└─ Shared Asset & Memory Service
```

This is the recommended completeness boundary for Phase 1 design.

Do not create additional top-level orchestras unless a pilot proves one of these four has become too broad to manage.