# Camera & Transition Grammar v1

Status: **Design Closure 0.6 / production-language contract / no implementation**

Purpose: 카메라를 `slow push-in`, `cinematic orbit` 같은 미학적 형용사 모음이 아니라 **설명 기능을 가진 재사용 가능한 언어**로 고정한다.

기존 `MODELING_CAMERA_RENDER_ROUTER.md`의 C01–C12와 T1–T6를 폐기하지 않고, 실제 Video Director work order에서 사용할 계약으로 구체화한다.

---

# 1. Camera Selection Law

카메라 선택 순서:
1. viewer가 이 shot 뒤에 무엇을 이해해야 하는가?
2. spatial relation을 카메라 이동 자체가 가르치는가?
3. 동일 구조의 orientation을 보존해야 하는가?
4. movement가 설명을 방해하지 않는가?
5. Blender/2D가 Veo보다 더 정확하고 싼가?
6. cinematic motion이 정말 설명가치를 높이는가?

If camera path is evidence → deterministic route.
If camera path is mood → generative route allowed.

---

# 2. Standard Camera Rig Vocabulary

## CX-CAM-01 / ESTABLISH_ORBIT
Maps to: C01

Purpose:
- 대상의 전체 형태와 기준 축을 소개
- 이후 cutaway의 orientation anchor 생성

Preferred route: Blender
Veo: atmosphere-only establishing에서 가능

Entry:
- full subject visible
Exit:
- one stable hero angle

Failure mode:
- 과도한 orbit으로 좌우/전후 기준 상실

---

## CX-CAM-02 / TARGET_PUSH
Maps to: C02

Purpose:
- 전체에서 특정 component로 attention 이동

Preferred route: Blender / controlled still composite
Veo: topology가 중요하지 않은 인물/역사 장면

Rule:
- target component ID가 있어야 함
- 단순 “멋있는 zoom” 금지

---

## CX-CAM-03 / CONTEXT_PULLBACK
Maps to: C03

Purpose:
- detail이 전체 시스템에서 어디에 속하는지 재확인

Best use:
- micro material → foundation → building
- component → network

Hard requirement:
- exit frame에서 parent structure relation이 읽혀야 함

---

## CX-CAM-04 / SURFACE_TO_SECTION
Maps to: C04 + C05

Purpose:
- 현실 exterior/plan view에서 숨은 내부 구조로 진입

Canonical pattern:
`surface registered view → descent/section plane → cutaway lock`

Preferred route: Blender / 2D→Blender hybrid

Hard locks:
- section plane
- vertical/world axis
- subject alignment

Failure mode:
- 물/지면을 통과한 뒤 어느 방향을 보고 있는지 잃음

---

## CX-CAM-05 / SECTION_INSPECTION
Maps to: C05

Purpose:
- 단면에서 층/구성요소 관계 설명

Camera:
- section plane에 거의 수직
- 움직임 최소화

Best for:
- foundations
- tunnel sections
- wall layers
- dam internals

Rule:
설명 중 불필요한 perspective drama를 피한다.

---

## CX-CAM-06 / PATH_FOLLOW
Maps to: C06/C07

Purpose:
- 물/공기/사람/신호/터널 등 하나의 semantic journey 추적

Preferred route:
- deterministic 3D when route is proof
- 2D map/elevation when route comprehension is clearer

Semantic anchor required:
- tracer/color/object identity

Failure mode:
- 빠른 flythrough로 context 상실

---

## CX-CAM-07 / EXPLODED_INSPECTION
Maps to: C08

Purpose:
- 구성요소가 어떻게 조립되는지 보여줌

Camera movement:
- 최소
Object movement:
- defined axes along component relationships

Preferred route: Blender

Rule:
explosion 자체보다 component relationship이 읽혀야 한다.

---

## CX-CAM-08 / XRAY_REGISTERED_REVEAL
Maps to: C09

Purpose:
- exterior position을 유지한 채 내부를 reveal

Operation:
- shell opacity/remove
- section/cutaway
- hidden component highlight

Preferred route: Blender/composite

Success:
viewer가 “이 내부가 방금 본 외부의 어디에 있다”를 즉시 이해.

---

## CX-CAM-09 / SCALE_BRIDGE
Maps to: C10

Purpose:
- city/system ↔ object ↔ component ↔ material scale 연결

Routes:
- Blender registered move
- 2D map → 3D anchor
- match-cut composite

Rule:
새 scale마다 orientation anchor를 하나 유지한다.

---

## CX-CAM-10 / STRESS_LOCKOFF
Maps to: C11

Purpose:
- parameter/force/load를 바꿔 causal effect를 비교

Camera:
- fixed by default

Preferred route:
- Blender / 2D simulation

Rule:
원인 변수를 보여주기 위해 카메라는 가급적 변수가 되지 않는다.

---

## CX-CAM-11 / REASSEMBLY_RETURN
Maps to: C12

Purpose:
- episode payoff에서 분해한 구조를 다시 전체로 조립

Pattern:
`detail/section → reassemble → original hero angle`

Rule:
Cold Open 또는 first reveal의 spatial state를 회수하는 것이 우선.

---

## CX-CAM-12 / CINEMATIC_CONTEXT
New explicit generative class

Purpose:
- 역사적 사람/현장/날씨/규모/생활감을 전달

Preferred route: Veo capability family

Not allowed when:
- exact component count is proof
- camera trajectory itself explains geometry
- hidden interior topology must remain exact

Contract:
- one primary action
- start state
- end state
- invariants
- reconstruction level
- continuity bridge if adjacent to deterministic shot

---

# 3. Lens / Framing Policy

정확한 mm를 지금 표준으로 고정하지 않는다.
대신 lens intent를 의미 기반으로 정의한다.

- `ORTHO/DIAGRAMMATIC`: 왜곡 최소, section/elevation
- `NEUTRAL_SPATIAL`: 자연스러운 공간 관계
- `WIDE_CONTEXT`: 전체 규모/환경, 왜곡이 설명을 바꾸지 않는 범위
- `DETAIL_INSPECTION`: component/material detail
- `CINEMATIC_CONTEXT`: 분위기 우선, hard geometry proof 금지

Implementation 시 실제 focal length range를 pilot render로 보정한다.

---

# 4. Movement Speed / Easing Policy

- dense explanation → slower movement or lockoff
- reveal → movement ends before/at key information landing
- camera and object animation이 동시에 복잡하게 움직이지 않음
- easing은 spectacle가 아니라 reading time을 지원
- visual objective를 이해하기 전에 다음 shot으로 나가지 않음

---

# 5. Transition Grammar

## CX-TR-01 / SPATIAL_CONTINUE
Same object/space, registered relation 유지.

Examples:
- orbit angle A → section angle A
- exterior → same-axis cutaway

Preferred: Blender/edit

---

## CX-TR-02 / LAYER_REVEAL
Surface → transparency/cut → internal.

Preferred: Blender/composite

Use when:
- X-Ray identity를 보여주는 핵심 transition

---

## CX-TR-03 / SCALE_MATCH
Large → small or reverse, shared anchor로 연결.

Examples:
- Venice city → selected building → wall foundation

---

## CX-TR-04 / REPRESENTATION_MATCH
Map/2D ↔ 3D ↔ real/reference imagery 사이의 동일 대상 연결.

Required:
- same semantic anchor
- orientation note

---

## CX-TR-05 / TEMPORAL_MATCH
Present ↔ historical reconstruction.

Required:
- reconstructed status explicit
- geometry anchor when possible

Veo may provide historical layer; deterministic base may anchor start/end.

---

## CX-TR-06 / CAUSAL_BEFORE_AFTER
Normal → parameter changed → result.

Preferred:
- same camera/space
- edit or deterministic simulation

---

## CX-TR-07 / SEMANTIC_BRIDGE
Different place/era but same function/shape/process.

Use carefully:
- must not imply physical continuity where none exists

---

## CX-TR-08 / CINEMATIC_BRIDGE
Water/smoke/weather/crowd/light etc.

Preferred: Veo/edit

Rule:
explanation 중 orientation을 감추는 장식 transition으로 남용 금지.

---

## CX-TR-09 / AUDIO_BRIDGE
J-cut/L-cut or ambient/music continuity가 먼저/나중 shot을 연결.

Owner: Post Director + Video Director

Rule:
visual truth를 덮는 transition이 아니라 cognitive continuity 지원.

---

# 6. Entry / Exit Frame Contract

모든 high-value shot은 최소 semantic entry/exit state를 가진다.

Entry state fields:
- visible subject/components
- camera relation
- object state
- light/time state if relevant
- semantic anchor

Exit state fields:
- same fields
- next-shot handoff target

Generative shot은 exact pixel match를 보장한다고 가정하지 않는다. 필요한 경우 Blender still/approved reference를 first/last frame anchor로 사용하되 provider capability는 실행 시 검증한다.

---

# 7. Camera QA Questions

1. 카메라가 무엇을 설명하는가?
2. 카메라 이동을 지워도 설명이 더 명확한가?
3. viewer가 현재 어느 방향/scale인지 아는가?
4. shot 끝 상태가 다음 shot 시작과 호환되는가?
5. Veo에 맡긴 경우 topology drift가 사실을 바꿀 수 있는가?
6. scale exaggeration이 있다면 표시되는가?
7. 카메라가 너무 움직여 narration을 읽을 시간을 빼앗는가?

---

# 8. Venice Pilot Mapping

Expected core sequence:
- CX-CAM-12 CINEMATIC_CONTEXT: modern Venice establishing
- CX-CAM-04 SURFACE_TO_SECTION: canal/building → water/ground section
- CX-CAM-05 SECTION_INSPECTION: wall/plank/pile/soil relationship
- CX-CAM-07 EXPLODED_INSPECTION: representative foundation layers
- CX-CAM-10 STRESS_LOCKOFF: unsupported soft soil vs reinforced representative section, only as labeled explanatory schematic
- CX-CAM-03 CONTEXT_PULLBACK: component → building
- CX-CAM-11 REASSEMBLY_RETURN: full city payoff

Historical workers are CX-CAM-12 and must be clearly reconstruction, not visual evidence of exact construction sequence unless sourced.

---

# 9. Closure Decision

Camera/transition vocabulary is now sufficient for Phase 1 planning.
Do not add more rig IDs merely to describe style. Add a new grammar item only if a future pilot reveals a distinct explanatory function not expressible by the current set.
