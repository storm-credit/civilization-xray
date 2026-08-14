# Blind-Spot Sweep & Pre-Mortem

이 문서는 “좋은 아이디어 같다”는 낙관을 깨기 위한 점검표다. 발견한 위험을 전부 기능으로 해결하려 하지 말고, 심각도와 발생 가능성을 보고 필요한 대응만 설계한다.

## Severity

- Critical: 채널 신뢰/법적 문제/제작 지속 가능성을 무너뜨릴 수 있음
- High: 반복 제작에서 품질 또는 비용을 크게 악화시킴
- Medium: 운영 중 우회 가능하지만 누적되면 문제
- Low: 기록만 하고 후순위 대응 가능

---

## 1. Editorial / Brand Blind Spots

- 건축·도시·역사·토목을 모두 다루다가 채널 정체성이 흐려질 수 있는가?
- “문명의 숨은 원리”라는 공통 포맷이 실제로 충분히 강한가?
- 질문형 제목이 반복되면 패턴 피로가 생기는가?
- 소재는 달라도 매번 같은 “겉→단면→내부→복귀” 구조만 반복되는가?
- 관광 상식 채널이나 역사 요약 채널로 미끄러질 위험은 없는가?
- 공학적 원리 설명과 역사적 드라마 중 무엇이 주인공인지 불명확해질 수 있는가?
- 한 번 크게 뜬 소재 때문에 채널 전체가 특정 분야로 끌려가는가?

## 2. Audience Blind Spots

- 초보자에게는 어렵고 전문가에게는 얕은 중간지대가 될 위험은?
- 한국 시청자에게 익숙하지 않은 해외 인프라는 hook이 약할 수 있는가?
- 8–15분 롱폼에서 시각적 신기함만으로 retention을 유지할 수 있는가?
- “정교한 3D”를 기대한 시청자가 AI artifact를 발견하면 신뢰가 급락하는가?
- 어린 시청자/가족 시청 가능성까지 고려할 것인가?

## 3. Research / Factual Integrity Blind Spots

- 건축/공학 정보가 2차 블로그의 반복 인용으로 굳어질 수 있는가?
- 수치가 출처마다 다를 때 어떤 기준을 적용하는가?
- 오래된 건축물 내부 구조가 추정뿐인데 확정 사실처럼 시각화될 수 있는가?
- 역사적 재구성과 공학적 사실이 한 장면에서 섞일 수 있는가?
- “왜 그런가”를 설명하기 위해 인과를 지나치게 단순화할 위험은?
- 현대 구조물의 보안/안전상 공개되지 않은 정보를 상상으로 채우게 되는가?
- 번역된 기술용어가 한국어에서 의미를 잃는가?
- 최신 개보수/재건축/운영 상태가 반영되지 않을 수 있는가?

## 4. Script Blind Spots

- 정보는 정확하지만 이야기가 없는 백과사전식 대본이 되는가?
- hook을 세게 만들려고 사실을 과장하는가?
- 질문에 대한 답을 너무 늦게 미뤄 clickbait가 되는가?
- 내레이션이 화면보다 빨라서 시청자가 구조를 이해할 시간이 없는가?
- 시각화 가능한 내용만 선택하면서 중요한 설명이 삭제되는가?
- 반대로 말로 설명할 수 있는 부분까지 비싼 3D로 만들고 있는가?
- 문장마다 새 사실을 넣어 cognitive load가 과도해지는가?

## 5. Script ↔ Visual Grammar Blind Spots

- 멋있는 화면이 나오지만 해당 문장을 설명하지 않는가?
- 화살표/단면/분해가 실제 원인을 증명하지 않고 장식으로 쓰이는가?
- 화면이 먼저 답을 보여줘 내레이션의 suspense를 죽이는가?
- 내레이션의 “이것/여기/이 구조”가 화면에서 무엇인지 불명확한가?
- 한 문장에 여러 시각 행동을 요구해 컷이 난잡해지는가?
- visual action taxonomy가 너무 복잡해 프롬프트가 불안정해지는가?

## 6. 3D / Spatial Continuity Blind Spots

- 장면마다 구조물의 창문, 기둥, 층수, 비례가 바뀌는가?
- 외관과 단면의 내부 구조가 서로 모순되는가?
- 카메라가 이동하면서 공간 축이 뒤집혀 시청자가 방향을 잃는가?
- 절개/폭발도에서 실제 연결관계가 사라지는가?
- AI video interpolation이 구조를 녹이거나 새 부품을 만들어내는가?
- 규모감이 장면마다 달라지는가?
- 같은 Hero Object를 유지하기 위해 실제 geometry가 필요한데 이미지 레퍼런스로만 버티는가?

## 7. Visual Truth / Reconstruction Blind Spots

- “설명용 개념도”와 “실제 구조”가 시청자에게 구분되는가?
- 과거 건축물의 미확정 내부를 photoreal하게 만들면 사실처럼 보이지 않는가?
- 색상 코딩이 실제 재질을 의미하는지 설명용 표시인지 구분되는가?
- 실제 사진과 AI 재구성 사이의 전환 규칙이 필요한가?
- 화면의 시각적 확신이 자료의 확신보다 높아지는 fake precision 문제가 있는가?

## 8. Video Analysis Blind Spots

- transcript만 분석해 화면 문법을 놓치는가?
- keyframe만 보고 중요한 짧은 transition을 놓치는가?
- 10분 이상 영상에서 프레임 샘플링이 지나치게 희박한가?
- scene cut 중심 샘플링이 느린 카메라 이동/geometry 변화의 핵심을 놓치는가?
- 레퍼런스 채널의 편집 결과만 보고 실제 제작 순서를 잘못 추론하는가?
- 사용 툴을 공개 근거 없이 단정하는가?

## 9. AI Model / Vendor Blind Spots

- 특정 이미지/영상 모델의 현재 기능에 하네스를 종속시키는가?
- API가 없거나 이용약관상 자동화가 제한된 서비스를 핵심 경로에 넣는가?
- 모델 업데이트로 prompt behavior가 바뀌면 재현이 불가능해지는가?
- seed/reference 기능이 vendor마다 달라 continuity contract가 깨지는가?
- 모델 가격이 오르면 제작 단가가 감당 불가능해지는가?
- 콘텐츠 정책/지역 제한 때문에 특정 역사 장면 생성이 막힐 수 있는가?

## 10. Cost / Throughput Blind Spots

- 10분 영상의 모든 컷을 고가 AI video로 만들 필요가 있는가?
- 실패 generation 재시도 비용이 실제 예산을 몇 배로 만드는가?
- 4K/고해상도가 설명력보다 비용만 올리는가?
- 사람 검수 시간이 API 비용보다 더 큰 병목이 되는가?
- render queue / rate limit 때문에 발행 주기가 깨지는가?
- 주간 제작량 목표가 quality bar와 양립 가능한가?

## 11. Harness / Agent Blind Spots

- 에이전트 역할이 이름만 다르고 책임이 겹치는가?
- Research Agent와 Fact Checker가 같은 모델/같은 검색 결과를 보고 서로를 검증하는 척하는가?
- Script Agent가 원본 source lineage를 잃어버리는가?
- Visual Agent가 script meaning보다 이미지 미학을 최적화하는가?
- shared context가 커져 모든 에이전트가 불필요한 정보를 받는가?
- 반대로 handoff가 지나치게 축약돼 중요한 제약이 사라지는가?
- orchestrator가 실패를 감지하지 못하고 다음 단계로 넘기는가?
- retry loop가 품질을 개선하지 않고 비용만 소모하는가?
- agent 개수를 늘리는 것이 곧 품질 향상이라고 착각하는가?
- 서로 다른 reviewer가 실제로 독립된 기준을 갖지 않는가?
- human approval가 너무 많아 자동화 이점이 사라지는가?
- human approval가 너무 적어 고비용 오류가 끝 단계에서 발견되는가?

## 12. Memory Blind Spots

- 장기 channel DNA와 episode-specific state가 섞이는가?
- 잘못된 과거 결정이 memory에 남아 계속 재사용되는가?
- memory의 근거/source가 사라지는가?
- 실패 generation과 그 원인을 저장하지 않아 같은 실수를 반복하는가?
- 너무 많은 memory가 검색돼 오히려 prompt를 오염시키는가?
- 최신 style bible과 폐기된 규칙을 구분할 versioning이 있는가?

## 13. Evaluation Blind Spots

- “정교하다”, “재미있다”처럼 재현 불가능한 평가만 있는가?
- 영상 완성 후에야 품질을 평가해 수정 비용이 너무 커지는가?
- script quality와 visual quality를 한 점수로 뭉개는가?
- 자동 평가기가 실제 시청자 이해도를 대변한다고 착각하는가?
- retention 데이터가 없는 초기 단계에서 조회수만 성공조건으로 두는가?

## 14. Rights / Provenance Blind Spots

- 레퍼런스 영상의 장면 구성을 너무 가깝게 모방하는가?
- 지도/도면/사진/논문 figure의 사용권을 확인하는가?
- 생성형 모델 입력으로 넣은 자료의 권리를 추적할 수 있는가?
- 영상 설명란/자료 출처 표기 정책이 있는가?
- 실제 인물/사건 재현에서 오해를 만드는 표현이 있는가?

## 15. Operations Blind Spots

- 한 명이 빠지거나 특정 SaaS가 막혀도 workflow가 유지되는가?
- episode별 산출물 위치와 상태가 명확한가?
- 어떤 prompt/version/model로 컷을 만들었는지 재현 가능한가?
- 실패 원인과 계획 변경이 run ledger에 남는가?
- 오래된 episode를 새 모델로 재생성할 수 있는가?

---

# Pre-Mortem Template

## Failure Scenario
“3개월 뒤 Civilization X-Ray가 기대 품질/발행 주기/조회 성과를 만들지 못했다.”

| Failure mode | Severity | Early signal | Prevention | Detection | Recovery | Stop condition |
|---|---|---|---|---|---|---|
| 채널 정체성 분산 | TBD | TBD | TBD | TBD | TBD | TBD |
| AI 3D continuity 붕괴 | TBD | TBD | TBD | TBD | TBD | TBD |
| 팩트 신뢰 하락 | TBD | TBD | TBD | TBD | TBD | TBD |
| 영상 한 편 비용 과다 | TBD | TBD | TBD | TBD | TBD | TBD |
| 롱폼 retention 부족 | TBD | TBD | TBD | TBD | TBD | TBD |
| 하네스 과설계 | TBD | TBD | TBD | TBD | TBD | TBD |

> 위 표의 TBD는 Discovery에서 실제 가설과 증거로 채운다. TBD가 남아 있는 상태는 “맹점 검토 완료”가 아니다.

# Completion Rule

이 문서를 읽었다는 것만으로 blind-spot sweep이 완료된 것이 아니다.

완료 증거:
- 항목별 relevant / not relevant 판정
- Critical/High 목록
- 대응/검증 방식
- unknown risk 목록
- 실제 pre-mortem 표 작성
- 사용자 또는 Director review
