Follow this project's Meta Loop Protocol for all work.

## Iteration Start Procedure (mandatory — cannot be skipped)

Follow this exact sequence. Do not reorder or skip any step.

1. Read `.meta-loop/WHY.md` → confirm the purpose and principles of this work
2. Read `.meta-loop/PROGRESS.md` → understand what was done and what's next
3. Read `.meta-loop/DECISIONS.md` → review prior judgments (prevent repetition/reversal)
4. Compare `.meta-loop/BASELINE.md` against current state → compute delta from origin
5. Record this iteration's objective in PROGRESS.md → then begin work

## Work Principles

- When changing any numeric value, record "why this value?" in DECISIONS.md
- If monotonic escalation (inflation) is detected, stop and recalibrate against BASELINE
- At every decision point, record the rationale in DECISIONS.md
- Do not make changes that deviate from WHY.md's intent
- On direction drift: self-verify and re-establish direction autonomously (do NOT wait for user)
- For complex changes, use subagents for Writer/Reviewer separation
- Run /compact autonomously if context is growing long
- Full project re-analysis every iteration is acceptable (resources are unlimited)
- Web searches for consistency/correctness verification are permitted

## Iteration Wrap-up (mandatory)

After completing work:

1. Update PROGRESS.md with this iteration's results
2. Specify what must be done next iteration (clear and actionable)
3. Record any decisions made in DECISIONS.md
4. Run /compact or /simplify if needed

## Specific Work Instructions

**전체 목표**: `발표자료/presentation.html` 을 선형적·점진적 내러티브로 재구성, 가시성·톤·콘텐츠 정확성 완성.

**이터레이션 순서 (Strict Priority)**:

### Iteration 1 — 진단 & 내러티브 설계
- Chrome 탭 열기 → `file:///D:/workspace/lecture/PL_임원_AI_Handson-1st/발표자료/presentation.html` 로드
- 모든 슬라이드 순회 (get_page_text + screenshot)
- 개념 왕복 지점 구체 매핑 → `.meta-loop/narrative-map.md` 작성
- 목표 슬라이드 순서(최종안) 제안 → PROGRESS.md 업데이트
- Seedance YouTube 링크 WebFetch 검증 (N9)

### Iteration 2 — 내러티브 재구성 실행 (N1)
- 슬라이드 순서 이동 (HTML 내 div 재배열)
- 에이전트/멀티에이전트 섹션 통합
- 800줄 청크 규칙 엄수 — Edit 단위로 작업

### Iteration 3 — 메모리/인프라 섹션 재구성 (N7a + N7b + N8)
- 슬라이드 "메모리 수요의 구조적 전환" → "AI 인프라에서 어디가 병목인가" 프레이밍
- 추론 시장 메모리 중요성 명시 추가
- 하이퍼스케일러 경쟁 슬라이드 신규 (치킨게임/과소투자 공포 내러티브, 구체 숫자 대신 개념)

### Iteration 4 — 멀티에이전트 Team 재디자인 (N4)
- 슬라이드 17 멀티에이전트 시각화 개선
- Team Lead + 전문가들 구조
- 임팩트 있는 레이아웃

### Iteration 5 — 톤 정리 (N6)
- 슬라이드 50 "코딩 도구가 아닙니다" 재작성
- "증거/대단/짜잔/보시는바와같이" 표현 grep → 모두 담백하게
- 자기자랑 투 제거

### Iteration 6 — 가시성 (N5a/b/c)
- `<style>` 블록 최하단에 override 추가
  - html { font-size: 117% } (체감 125% 효과)
  - rgba(255,255,255,0.25~0.5) 계열 밝기 상향
  - 작은 포인트 텍스트에 테마 색상 힌트 (은은하게)
- 기존 clamp() 값 상향 (0.78→0.92 등)

### Iteration 7 — Chrome QA & 최종 검수 (N10)
- 전체 슬라이드 재순회
- 레이아웃 깨짐/오타/링크 점검
- 커밋 & 푸시

## Autonomous Constraints

- 사용자 자리 비움 — 질문 금지, 멈춤 금지
- 모든 결정은 WHY.md/BASELINE.md 기반 자체 판단
- 막히면 subagent 스폰해서 돌파
- Chrome 도구 문제 시 정적 분석으로 대체
- 800줄 초과 I/O 절대 금지 — 청크로 분할
- 각 이터레이션 종료 시 git commit (local only, push는 최종)
