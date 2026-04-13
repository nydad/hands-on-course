# Narrative Map — Iteration 1 Synthesis

## Current Structure (53 slides, linear order)

| Old ACT | Range | Issue |
|---------|-------|-------|
| 0 Opening | #1-2 | OK |
| 1 시장반응 | #3-5 | OK |
| 2 업계기준선 | #6-9 | OK |
| 3 Model≠Agent | #10-12 | OK (slide #11,#12 edited) |
| 4 패러다임 | #13-17 | 문제: #17 멀티에이전트가 확장이라 ACT 경계 애매 |
| 5 코딩을넘어 | #18-21 | 문제: 메모리(#21)가 영상/Science와 동일 ACT 안에 있음 — 성격 다름 |
| 6 역할변화 | #22-28 | OK, 내부 7슬라이드 약간 산만 |
| 7 현실제약 | #29-34 | OK |
| 커리큘럼 | #35 | 위치 애매 (ACT 7 뒤) |
| 8 Hands-on | #36-49 | OK |
| 마무리 | #50-53 | 문제: #50 "저는 지금 Claude Code로 만들었습니다" 자기자랑 톤 |

## Proposed Structure (same count, clearer axis)

| New ACT | Slides | Change |
|---------|--------|--------|
| 0 Opening | #1-2 | 유지 |
| 1 시장반응 | #3-5 | 유지 |
| 2 업계기준선 | #6-9 | 유지 |
| 3 Model≠Agent | #10-12 | 유지 |
| 4 패러다임 챗봇→에이전트 | #13-16 | #17 분리 |
| 5 확장 에이전트→멀티에이전트 | #17 (재디자인) | 독립 ACT, Team 구조 강조 |
| 6 분야 확산 | #18-20 | 메모리 제외 |
| **7 AI 인프라 병목** | #21(재프레이밍) + NEW | 신규 ACT — 메모리 재프레이밍 + 하이퍼스케일러 치킨게임 신규 슬라이드 |
| 8 역할의 변화 | #22-28 | 유지 |
| 9 현실 제약 | #29-34 | 유지 |
| 10 커리큘럼+Handson | #35-36 통합 | 경계 명확화 |
| 11 Hands-on | #37-49 | 유지 |
| 12 마무리 | #50-53 | #50 재작성 (담백화) |

## Concrete Edit Plan (Iteration 2)

1. **메모리 슬라이드 재프레이밍** (line 670-691)
   - h3: `메모리 수요의 구조적 전환` → `AI 인프라에서 어디가 병목인가`
   - 3열 stat-card에 추론 메모리 포인트 추가 (KV 캐시)
   - tip 박스: 추론 시장/영상/월드모델 모두 메모리 수렴 강조

2. **하이퍼스케일러 치킨게임 신규 슬라이드** (메모리 슬라이드 직후 삽입)
   - h3: `왜 천문학적 투자를 멈출 수 없는가`
   - Pichai 인용 + 과소투자>과잉투자 대비 구조
   - 치킨게임 다이어그램 또는 개념 카드 3개

3. **SECTION 재라벨링** (중요)
   - SECTION 05 코딩을 넘어 (cyan) → 유지 (영상·Science AI만)
   - **NEW SECTION: AI 인프라 병목** (teal 배경) — 메모리 + 하이퍼스케일러
   - SECTION 06 역할의 변화 (violet) → SECTION 07
   - SECTION 07 현실 제약 (teal) → SECTION 08
   - 이후 SECTION 재번호

## External Resources Verified

- **Seedance YT (6D4_ZMnPx7I)**: 출처 미확인. 공식 대체 URL 사용 권장
  - 공식: `https://seed.bytedance.com/en/seedance2_0`
  - 3rd party 신뢰: `https://fal.ai/seedance-2.0`
- **Claude Code 공식 데모 (없었던 슬라이드)**:
  - `https://www.youtube.com/watch?v=iI_zWNunkc4` (A Developer's Intro, 1시간)
  - `https://www.youtube.com/watch?v=8dcI0CqBQq4` (Live Webinar)

## Tone Audit (17 issues)

HIGH priority:
- Line 664-665: "GPT-5.2 새 공식 도출", "Codeforces 세계 상위 8등" 톤 톤다운
- Line 1055: "만능 인터페이스" → "다목적" (반복 사용)
- Line 1177: "같은 품질로 무한 생산" → "확장 가능한"
- Line 1294-1318 슬라이드 전체 재작성: "저는 지금", "집에서 커스텀 게임", "온몸으로 느끼는"
- Line 1338: "들어는 봤다 → 해봤다" 대비 구조 완화

## CSS Override Plan

단일 `<style>` 하단 블록 추가:
- `html { font-size: 118% }` (체감 125%)
- 속성 선택자로 `rgba(255,255,255,0.25-0.45)` 계열 → `0.6` 밝기 up
- `.sub`, `.meta`, `.tag`, `.tbl th`, `cite` 등 작은 클래스 `!important`로 명도/사이즈 상향
- 포인트 em은 opacity 0.92로 채도 유지

## Hyperscaler Slide Content (draft)

**Title**: 왜 천문학적 투자를 멈출 수 없는가

**Subtitle**: 과잉투자는 비용의 문제, 과소투자는 존재의 문제

**3-card structure**:

Card 1 - 공포
> "밀려나면 다음 10-15년 AI 플랫폼에서 제외된다"
> — 기업 수뇌부 발언 종합

Card 2 - 비대칭 리스크
> "과소투자 리스크가 과잉투자 리스크보다 극적으로 크다"
> — Sundar Pichai, Alphabet CEO, 2024 Q2 실적 콜

Card 3 - 구조
> 수요 > 공급, 긴 리드타임
> 지금 안 깔면 따라잡을 수 없음 → 치킨게임

**Closing line**: 앞다퉈 선점하는 것 외에 합리적 선택지가 없다
