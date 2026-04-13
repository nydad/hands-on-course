# BASELINE — Origin Snapshot (Immutable)

캡처 시점: 2026-04-13 (meta-loop-protocol setup)

## 파일 구조

```
발표자료/
  presentation.html    (1390 줄) — 메인 강의 슬라이드
  tips.html            (407 줄) — Claude Code Tips 카드
assets/
  ai-users-scale.png
  github-readme-for-human-for-agent.jpg
  saaspocalypse-chart.png
index.html             (루트 리다이렉트)
.github/workflows/deploy-pages.yml   (GitHub Pages 배포)
```

## presentation.html 현재 슬라이드 순서 (53개)

| # | 라인 | 테마 | 제목/주제 |
|---|------|------|-----------|
| 1 | 174 | samsung | 01 Cover |
| 2 | 181 | surface | 02 프로그램 구성 |
| 3 | 232 | rose | SECTION 01 — 시장 반응 (SaaSpocalypse) |
| 4 | 240 | default | SaaSpocalypse Chart |
| 5 | 269 | default | 피처폰 vs 스마트폰 |
| 6 | 287 | mint | SECTION 02 — 업계 기준선 |
| 7 | 294 | surface | AI 사용자 규모 |
| 8 | 323 | surface | 핵심 지표 |
| 9 | 351 | surface | 변화의 속도 |
| 10 | 388 | indigo | SECTION 03 — Model ≠ Agent |
| 11 | 395 | surface | 비유로 이해하는 구조 (edited) |
| 12 | 441 | default | 성능 공식 (edited: "코딩 성능" → "성능") |
| 13 | 449 | orange | SECTION 04 — 패러다임 전환 |
| 14 | 478 | default | ARS vs 전담 참모 |
| 15 | 506 | surface | 대답하는 도구 → 일하는 도구 (표) |
| 16 | 542 | default | 이미 일어나고 있는 변화 (GitHub README) |
| 17 | 569 | surface | 그 다음 단계 — 멀티에이전트 |
| 18 | 641 | cyan | SECTION 05 — 코딩을 넘어 |
| 19 | 648 | in-cyan | 영상 AI — ByteDance Seedance 2.0 (YouTube 링크) |
| 20 | 660 | in-cyan | Science AI |
| 21 | 671 | surface | 메모리 수요의 구조적 전환 |
| 22 | 696 | violet | SECTION 06 — 역할의 변화 |
| 23 | 703 | default | 구현 비용의 붕괴 (Jensen Huang 인용) |
| 24 | 710 | default | PM : Engineer 비율 역전 |
| 25 | 726 | default | 인지 노동의 심화 |
| 26 | 753 | surface | 생산성 역설과 도파민 루프 |
| 27 | 776 | default | AI는 증폭기 (DORA) |
| 28 | 792 | default | 역할의 재정의 (Addy Osmani) |
| 29 | 803 | teal | SECTION 07 — 기술·현실 분리 |
| 30 | 810 | default | 기술 가능성과 적용 가능성 |
| 31 | 852 | surface | 우리 환경의 제약 |
| 32 | 874 | default | 사외망 이유 |
| 33 | 897 | surface | 함께 논의할 질문들 |
| 34 | 908 | surface | 과제 (Vera Rubin / HBM / 삼성전자 등) |
| 35 | 938 | surface | 오늘의 커리큘럼 |
| 36 | 977 | cyan | SECTION — Hands-on |
| 37 | 984 | default | Lab 0 intro |
| 38-46 | 991-1184 | in-cyan | Lab 1-6 / Tips cards |
| 47 | 1207 | surface | Tips 집합 |
| 48 | 1244 | surface | 실무에서 바로 쓰는 팁 |
| 49 | 1271 | in-mint | 배운 건 나누자 |
| 50 | 1294 | surface | 코딩 도구가 아닙니다 (Claude Code로 자료 제작 자랑) |
| 51 | 1324 | surface | Today's Takeaway |
| 52 | 1337 | default | "들어는 봤다" → "해봤다" |
| 53 | 1346 | blue | 마지막 섹션 |

## 내러티브 왕복 문제 (N1 분석)

현재 구조에서 개념 왕복 사례:

1. **에이전트 ↔ 멀티에이전트 왕복**:
   - 슬라이드 14 ARS/전담참모 (에이전트 개념)
   - 슬라이드 15 대답→일하는 (에이전트 속성)
   - 슬라이드 16 GitHub README (에이전트 현실)
   - 슬라이드 17 멀티에이전트 (확장)
   - 슬라이드 18 (SECTION 05로 점프)
   → 다시 에이전트 시연/데모가 뒤에 섞여있지 않은지 재확인 필요

2. **SECTION 05 (코딩을 넘어) 구성**:
   - 영상 AI → Science AI → 메모리
   - 메모리 섹션이 "코딩을 넘어" 축에 정확히 맞는지 재검토 필요 (인프라 병목 주제로 재프레이밍 필요)

3. **역할의 변화 (SECTION 06)** 내부:
   - 구현 비용 → PM:Engineer → 인지 노동 → 도파민 → 증폭기 → 역할 재정의
   - 상대적으로 잘 흐르나, 증폭기/재정의 통합 여지 있음

## CSS 토큰 (현재)

- 기본 배경: radial gradient on `#0C0F1E/#0B1326/#0A0D16`
- 텍스트: `#EFF2FA` 주, `#99ABCA` 서브
- 폰트: Noto Sans KR 400/700/900
- 주요 포인트 컬러 (em 클래스별):
  - blue/navy/indigo/samsung: #7AB8FF
  - violet: #C4B5FD
  - rose: #FDA4AF
  - mint/teal: #4EEDB4 / #4EEAB8
  - cyan: #38E8F8
  - amber/orange: #FBCF60/80
- 회색 텍스트: `rgba(255,255,255,0.25-0.5)` 다수 사용

## Gray Text Opacity 사용 빈도 (대략)

- `rgba(255,255,255,0.25)`: 매우 옅은 — 거의 안 보임
- `rgba(255,255,255,0.3~0.35)`: 옅은 서브텍스트
- `rgba(255,255,255,0.4~0.45)`: 중간
- `rgba(255,255,255,0.5)`: 표준 서브

## 외부 링크 (검증 필요)

- `https://www.youtube.com/watch?v=6D4_ZMnPx7I` — Seedance 2.0 데모

## 폰트 스케일 (현재)

- h1: clamp(3rem, 6vw, 5.5rem)
- h2: clamp(2.2rem, 4.5vw, 4rem)
- h3: 1.28rem (fixed)
- .sub: clamp(1.3rem, 2.2vw, 1.8rem)
- 본문: ~0.95~1.1rem 흐름
- 소형 (desc): 0.78~0.95rem (사용자 지적: 작음)

## 이미 적용된 수정 사항

- [DONE] 슬라이드 11: Samsung 비유 → "비유로 이해하는 구조", 첫 행 스타일 통일
- [DONE] 슬라이드 12: "코딩 성능" → "성능"

## 보존해야 할 핵심 팩트 (왜곡 금지)

- Jensen Huang 인용 (구현 비용 붕괴)
- Andrew Ng 팀 PM:Engineer = 2:1
- 전통 조직 1:7
- Addy Osmani 인용
- DORA Report 2025
- GPT-5.2 이론 물리 공식 도출, Codeforces 세계 8등
- 2024 노벨 화학상 AlphaFold
- ByteDance Seedance 2.0 2026. 2. 12 출시
- MPA/디즈니/파라마운트/SAG-AFTRA 법적 대응
