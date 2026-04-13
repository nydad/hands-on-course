# DECISIONS

판단 이력 — 번복 방지, 맥락 보존.

## 2026-04-13 — Setup

### D1: 루프 작업 타겟을 presentation.html 한 파일로 제한
- **이유**: tips.html은 독립 부록, 다른 실습 파일은 스코프 외. 집중도 확보.

### D2: 기존 팩트·인용 보존
- **이유**: 사용자 명시 — "내용을 전체적으로 왜곡하면 안 된다"
- **영향**: Jensen Huang, Andrew Ng, Addy Osmani, DORA, AlphaFold 등 수치·출처 절대 변경 금지.

### D3: 색상 팔레트는 기존 테마 유지
- **이유**: 전체 톤 일관성
- **영향**: 신규 SECTION 06은 amber 선택 (teal과 연속성, violet과 대조)

### D4: 125% 스케일은 `html { font-size: 117% }` 방식
- **이유**: clamp/vw 기반 폰트가 자동 확장. 레이아웃 파괴 최소화.

### D5: Chrome QA는 로컬 `python http.server 8899`
- **이유**: GitHub Pages 배포 지연·캐시 우회

## 2026-04-13 — Iteration 1

### D6: 5개 서브에이전트 병렬 스폰
- **이유**: 자원 무제한, 각 서브 도메인(narrative/link/research/tone/css)을 독립 관점으로 평가
- **결과**: 교차 검증된 편집 계획 확보, 편향 감소

### D7: 새로운 SECTION 06 "AI 인프라 병목" 독립화
- **이유**: 메모리 슬라이드가 "코딩을 넘어"(SECTION 05) 아래에 있으면 축이 혼재. 인프라·하이퍼스케일러와 함께 별도 ACT로 분리하면 선형 확장 명확.
- **영향**: SECTION 07~08 재번호. partMap JS 업데이트.

### D8: 하이퍼스케일러 슬라이드에 구체 숫자(680B, 5대) 미사용
- **이유**: 사용자 명시 — 개념 수준으로 표현 요구
- **영향**: "천문학적 자본", "공포", "비대칭 리스크", "치킨게임" 개념 카드 3개로 구성

### D9: Pichai 인용만 직접 인용체 사용, 타 경영진은 종합 서술
- **이유**: Pichai "under-investing dramatically greater than over-investing" 발언은 공식 실적콜 1차 출처. Zuckerberg/Nadella 등은 2차 요약 중심이므로 "빅테크 CEO 발언 종합"으로 처리.

### D10: 멀티에이전트 슬라이드 Team Lead(오케스트레이터) + 하위 전문가 위계 구조
- **이유**: 사용자 요구 "Team으로 구성된다는 느낌". 계층 시각화가 Team 정체성을 가장 잘 전달.
- **영향**: 수직 커넥터 + 수평 바 + 상단 짧은 커넥터로 트리 구조 구현.

### D11: "Claude Code로 이 자료 만들었습니다" 슬라이드 전면 재작성
- **이유**: 사용자 지적 — "증거/대단/짜잔 느낌 제거"
- **전환**: 1인칭 자기자랑 → "실제 활용 영역" 객관 프레이밍. "집에서 커스텀 게임 플레이" → "프로토타입·분석·창작" 일반화.

### D12: CSS override는 `<style>` 블록 말미에 추가 (재정의 방식)
- **이유**: 기존 CSS 수정 시 영향 범위 예측 어려움. override 블록은 독립적으로 on/off 가능.
- **영향**: 17개 선택자 override, !important 필요 최소화.

### D13: Pages 배포가 Actions 비활성화로 자동 트리거 실패 → 로컬 QA로 검증 + Pages legacy 큐잉
- **이유**: "Actions has been disabled for this user" 응답. 대안으로 Pages build_type을 workflow→legacy 전환, 수동 build 요청, 로컬 HTTP 서버로 Chrome QA.
- **영향**: 배포 전파는 사용자 조치(Actions 활성화 또는 대기) 필요. 내용 검증은 로컬에서 완료됨.
