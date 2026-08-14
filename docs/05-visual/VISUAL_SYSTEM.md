# Visual System

## Visual North Star

Civilization X-Ray의 화면은 “AI가 만든 멋있는 3D”가 아니라 **설명을 위해 통제된 공간 모델**처럼 보여야 한다.

시청자는 다음을 느껴야 한다.
- 같은 구조물을 계속 보고 있다.
- 카메라가 어디에 있는지 이해된다.
- 구조가 왜 작동하는지 화면만 봐도 따라갈 수 있다.
- 실제 사실과 설명용 재구성을 혼동하지 않는다.

---

# Four Visual Directions

## V1. Cinematic AI Reconstruction

특징:
- photoreal establishing shots
- dramatic light/weather
- AI image/video 비중 큼

장점:
- 감정적 몰입
- 역사 장면과 규모감에 강함
- 빠른 스타일 탐색

약점:
- spatial continuity 약함
- 내부 구조 설명에서 hallucination 위험
- 에피소드가 길수록 Hero Object drift 증가

결론: **보조 레이어로 채택, core explainer에는 부적합.**

## V2. Clean Technical Infographic 3D

특징:
- 단색/명확한 재질
- clean background
- schematic cutaway
- overlay/label 중심

장점:
- 설명 명확
- 일관성 유지 쉬움
- 오류 발견 쉬움

약점:
- 감정/역사적 몰입 부족
- 유튜브 영상으로 너무 교육자료처럼 보일 수 있음

결론: **설명 구간의 핵심 언어로 채택.**

## V3. Documentary Hybrid 3D

특징:
- 실제/영화적 establishing
- geometry-backed 구조 장면
- AI reconstruction
- technical overlays
- seamless transition

장점:
- 설명력과 몰입 균형
- 건축/도시/역사 모두 확장 가능
- Civilization X-Ray 이름과 가장 잘 맞음

약점:
- asset 관리와 compositing 설계 필요
- 자동화 난이도가 높음

결론: **Selected primary direction.**

## V4. Stylized X-Ray Signature

특징:
- 고유한 반투명 재질
- 특정 색상 코딩
- 일관된 orthographic/isometric 시각언어
- 브랜드 중심

장점:
- 썸네일/채널 아이덴티티 강함
- 비현실적 재구성임을 쉽게 구분

약점:
- 반복되면 게임/교육 애니메이션 느낌
- 역사적 분위기를 약화시킬 수 있음

결론: **브랜드용 signature mode로 제한 채택.**

---

# Selected Visual Architecture

**V3 Documentary Hybrid 3D + V2 Technical Clarity + limited V4 signature language.**

화면 레이어:

1. Reality / Establishing Layer
2. Hero Object Layer
3. X-Ray / Technical Layer
4. Flow / Force / Evidence Overlay
5. Reconstruction Layer
6. Annotation Layer

이 레이어들을 한 컷에 전부 쓰지 않는다.

---

# Hero Object Bible

설명 대상이 구조적으로 중요하면 촬영/생성 전에 Hero Object Bible을 만든다.

최소 항목:
- canonical silhouette
- front / side / rear / top reference
- major dimensions or ratios
- fixed landmarks
- material regions
- interior topology if known
- ground/foundation relationship
- moving components
- parts allowed to simplify
- parts that must never change
- unknown/reconstructed parts
- scale references

## Continuity Locks

각 episode에서 다음을 나눈다.

### Hard Lock
변하면 설명이 틀려지는 것.
- 층수
- 주요 기둥 위치
- 터널/관로 경로
- 기초 관계
- 축/방향

### Soft Lock
스타일상 유지하면 좋지만 설명과 직접 관계없는 것.
- 작은 표면 디테일
- 일부 주변 오브젝트
- 날씨

### Free
컷마다 바뀌어도 되는 것.
- 군중
- 구름
- 비핵심 차량

---

# Geometry Decision Rule

“실제 3D를 써야 하나?”를 툴 선호로 결정하지 않는다.

다음 질문 중 2개 이상 YES면 geometry/depth-backed 접근을 우선 검토한다.

- 정확한 부품 위치가 설명의 근거인가?
- 카메라가 여러 각도를 돌아야 하는가?
- 외부와 내부가 정확히 연결돼야 하는가?
- 특정 부품을 제거/분해/재조립해야 하는가?
- 힘/물/사람의 경로가 topology를 따라야 하는가?
- 3개 이상 컷에서 같은 구조를 재사용하는가?

YES가 적으면 AI image/video 기반으로 충분할 수 있다.

---

# Camera Grammar

## Establishing
- slow approach
- aerial-to-object
- city-to-detail

목적: 위치와 규모 이해.

## Explanation
- orbit with axis lock
- top-down
- orthographic-ish inspection
- section perpendicular view
- controlled dolly

목적: 공간 관계 이해.

## Reveal
- ground sinks/cuts
- shell becomes transparent
- component separation
- camera dives through opening

목적: “보이지 않던 것” 공개.

## Flow
카메라가 물/공기/사람과 함께 이동할 수 있으나 너무 빠른 chase는 피한다.

## Stress Test
가능하면 카메라를 고정하고 parameter만 변화시킨다.
원인과 결과를 비교하기 쉬워진다.

---

# Orientation Rules

1. 공간 축을 정하면 설명 구간에서는 함부로 뒤집지 않는다.
2. 카메라가 180도 넘어갈 경우 명확한 transition을 둔다.
3. 단면 방향은 장면마다 바꾸지 않는다.
4. flow direction은 색/화살표/카메라 중 최소 하나로 유지한다.
5. 새로운 scale로 이동할 때 zoom transition을 사용해 관계를 보여준다.

---

# Material / Color Semantics

최종 색상은 branding 단계에서 정하지만 의미 규칙은 선행한다.

예:
- 실제/주 구조물: neutral material
- 현재 설명 대상: accent
- force/load: distinct overlay
- water/air flow: semantic overlay
- reconstructed/uncertain: 별도 표시 또는 stylization

색만으로 의미를 전달하지 않는다. 움직임/형태/label 중 하나를 병행한다.

---

# Reconstruction Policy

화면 상태를 네 등급으로 관리한다.

## R0 — Documented
도면/공식 자료/신뢰도 높은 기록으로 확인.

## R1 — Strong Engineering Inference
직접 자료가 없더라도 구조/동시대 사례/전문 자료로 강하게 추론 가능.

## R2 — Plausible Reconstruction
여러 가능성 중 설명용으로 하나를 재구성.

## R3 — Illustrative
실제 모습을 주장하지 않는 개념 시각화.

R2/R3는 narration 또는 visual treatment에서 확정 사실과 구분해야 한다.

---

# AI Artifact Reject List

다음은 aesthetics가 좋아도 reject 후보다.
- 부품 수가 컷 사이에서 변함
- 구조물이 녹거나 서로 관통
- 사람/차량 scale이 비정상
- 카메라 이동 중 벽/기둥 위치 변형
- 텍스트/표지판 왜곡이 시선을 끔
- 실제 역사/지역과 다른 랜드마크 혼합
- 물리적 flow가 벽을 통과
- 분해된 부품이 원래 위치로 재조립 불가능

---

# Shot-Level Continuity Sheet

후속 구현에서 각 shot은 최소 다음 상태를 참조해야 한다.
- hero object version
- axis/orientation
- camera start/end
- visible layers
- removed/transparent components
- flow state
- time/era
- reconstruction level
- hard locks
- transition target

---

# Visual Success Criteria

PASS 후보:
- 소리 없이 봐도 핵심 공간 관계를 추적 가능
- 동일 Hero Object의 hard locks가 유지됨
- visual action이 narration 의미를 실제로 설명함
- cutaway/explode 사용 후 원 구조로 재조립 가능
- uncertainty level이 시각적으로 과장되지 않음

FAIL 후보:
- “그럴듯하지만 같은 구조인지 모르겠다”
- 화면이 예쁘지만 설명이 없어도 상관없는 B-roll 수준
- AI artifact가 원리 이해를 방해
