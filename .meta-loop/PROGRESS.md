# PROGRESS

## Current Iteration Objective

**Iteration 7 — Final QA & Deploy**: 모든 이터레이션 목표 로컬에서 달성. 배포는 user-level Actions 비활성화로 자동 트리거 안 됨. Pages legacy 빌드 큐잉 완료 — 전파 대기 중.

## Completed ✅

### Pre-Setup
- [DONE] 슬라이드 11 비유 구조 (Samsung 제거, 첫 행 통일)
- [DONE] 슬라이드 12 성능 공식 ("코딩" 제거)
- [DONE] GitHub Pages 최초 배포

### Iteration 1 — Diagnosis
- [DONE] 5개 서브에이전트 병렬 조사 (narrative/seedance/hyperscaler/tone/css)
- [DONE] narrative-map.md 합성
- [DONE] 편집 계획 수립

### Iteration 2 — Narrative
- [DONE] 메모리 슬라이드 재프레이밍 → "AI 인프라에서 어디가 병목인가"
- [DONE] 하이퍼스케일러 치킨게임 신규 슬라이드 삽입
- [DONE] NEW SECTION 06 AI 인프라 병목 (amber 테마)
- [DONE] SECTION 재번호 (07 역할의 변화, 08 현실 제약)
- [DONE] partMap JS 업데이트

### Iteration 3 — Content (merged with Iter 2)
- [DONE] 메모리 stat-card 확장 (KV 캐시 card 추가)
- [DONE] Seedance 링크 → 공식 ByteDance + fal.ai 2개 링크

### Iteration 4 — Multi-agent Team
- [DONE] 슬라이드 17 Team Lead + 전문가 계층 시각화
- [DONE] TEAM 배지, Orchestrator 명시, 수직/수평 커넥터

### Iteration 5 — Tone cleanup
- [DONE] "저는 지금/집에서 커스텀 게임/온몸으로" → 담백한 재작성
- [DONE] "만능 인터페이스" → "다목적 인터페이스" (3곳)
- [DONE] "세계 상위 8등" → "상위권 성능"
- [DONE] "새 공식 도출 + 12시간 자체 증명" → "난제 풀이 + 자체 검증"
- [DONE] "쏟아지는 PR" → "증가하는 PR 처리량"
- [DONE] "이것이 오늘 실습의 핵심" → "오늘 실습의 핵심"
- [DONE] "들어는 봤다 → 해봤다" → "들어본 것에서 해본 것으로"
- [DONE] "직접 해본 사람만 할 수 있는 이야기" → "직접 경험한 사람의 판단"

### Iteration 6 — Visibility
- [DONE] html 117% 폰트 스케일
- [DONE] 속성 선택자로 낮은 opacity 일괄 밝기 상향
- [DONE] `.sub`, `.meta`, `.tag`, `.tbl th`, `.arch-layer` 등 클래스 override
- [DONE] 작은 폰트 최소 0.88~0.95rem 확보
- [DONE] `.em` font-weight 상향

### Iteration 7 — QA & Deploy
- [DONE] 로컬 Chrome QA: 54 슬라이드, 모든 키 콘텐츠 검증 (infra/team/hyperscaler/tone)
- [DONE] git commit + push (commits: 3e3f4ef + 0090990)
- [DONE] Pages 설정 build_type: workflow → legacy (main/)
- [DONE] Pages build 큐잉 (2회)
- [BLOCKED] 자동 배포 — user-level Actions 비활성화됨 ("Actions has been disabled for this user")

## Outstanding Issue

GitHub Actions가 사용자 계정 레벨에서 비활성화됨. Pages legacy 빌드가 큐잉됐지만 전파에 시간 필요하거나 수동 개입 필요.

**해결 방안** (사용자 선택):
1. github.com/settings → Actions → Enable
2. 또는 repo settings → Pages → 수동 재저장으로 재빌드 트리거
3. 또는 로컬에서 확인: `http://localhost:8899/발표자료/presentation.html` (python http.server 실행 중)

## Current Iteration Objective (for next loop fire)

루프 재발화 시:
1. Pages 배포 상태 재확인 (`curl https://nydad.github.io/hands-on-course/발표자료/presentation.html | grep '인프라에서'`)
2. 전파 완료되었으면 Chrome에서 최종 시각 QA
3. 미반영이면 대안 배포 방법 실행

## Next Iteration

배포 전파 후 최종 시각 검수만 남음.
