# Claude Code Skills 모음

이 디렉토리에는 Claude Code에서 활용할 수 있는 4개의 커스텀 스킬이 포함되어 있습니다.
스킬은 Claude Code에 특정 도메인의 전문 지식과 워크플로우를 주입하여, 일관된 고품질 결과물을 생성할 수 있게 해주는 기능입니다.

---

## 포함된 스킬 목록

| 스킬 | 설명 | 주요 출력물 |
|------|------|------------|
| html-slides | 단일 HTML 파일 프레젠테이션 생성기 | .html 슬라이드 |
| confluence-wiki | Confluence 위키 문서 생성기 | .wiki / .xhtml + .drawio |
| mermaid-diagram | Mermaid 다이어그램 생성기 | .md / .mmd / .html |
| deep-search | 병렬 에이전트 기반 심층 웹 리서치 | 구조화된 리서치 보고서 |

---

## 설치 방법

### 1단계: 스킬 디렉토리 생성

사용자 홈 디렉토리 아래에 스킬 폴더를 생성합니다.

```bash
# macOS / Linux
mkdir -p ~/.claude/skills

# Windows (Git Bash)
mkdir -p ~/. claude/skills

# Windows (PowerShell)
New-Item -ItemType Directory -Force -Path "$env:USERPROFILE\.claude\skills"
```

### 2단계: 스킬 복사

원하는 스킬을 `~/.claude/skills/` 디렉토리에 복사합니다.

```bash
# 전체 스킬 한번에 복사 (Git Bash / macOS / Linux)
cp -r .skills/html-slides ~/.claude/skills/
cp -r .skills/confluence-wiki ~/.claude/skills/
cp -r .skills/mermaid-diagram ~/.claude/skills/
cp -r .skills/deep-search ~/.claude/skills/
```

```powershell
# Windows (PowerShell)
Copy-Item -Recurse .skills\html-slides $env:USERPROFILE\.claude\skills\
Copy-Item -Recurse .skills\confluence-wiki $env:USERPROFILE\.claude\skills\
Copy-Item -Recurse .skills\mermaid-diagram $env:USERPROFILE\.claude\skills\
Copy-Item -Recurse .skills\deep-search $env:USERPROFILE\.claude\skills\
```

### 3단계: 확인

Claude Code를 재시작하면 스킬이 자동으로 인식됩니다. `/skills` 명령어로 설치된 스킬을 확인할 수 있습니다.

---

## 스킬별 상세 안내

### 1. html-slides -- HTML 프레젠테이션 생성기

단일 HTML 파일로 구성된 프로페셔널한 프레젠테이션을 생성합니다. 다크 테마 기반의 디자인 시스템을 사용하며, 글래스모피즘 카드, 13가지 색상 테마, 25개 이상의 컴포넌트를 지원합니다. 별도의 소프트웨어 없이 웹 브라우저에서 바로 발표할 수 있습니다.

**트리거 키워드:**
`presentation`, `slides`, `ppt`, `deck`, `slideshow`, `keynote`, `pitch`, `발표자료`, `슬라이드`

**사용 예시:**
```
"AI 트렌드에 대한 발표자료 만들어줘"
"클라우드 아키텍처 소개 slides 30장으로 만들어줘"
"신규 프로젝트 pitch deck 만들어줘"
```

**주요 특징:**
- 단일 .html 파일 (CSS/JS 모두 인라인)
- 키보드 네비게이션 (방향키, 스페이스바)
- 반응형 디자인 (모바일/태블릿 대응)
- 인쇄 지원
- 접근성 지원 (ARIA, 축소 모션)

**디렉토리 구조:**
```
html-slides/
  SKILL.md                          -- 스킬 명세 및 워크플로우
  references/
    template.html                   -- 기본 HTML 템플릿 (CSS + JS)
    slide-patterns.md               -- 슬라이드 컴포넌트 패턴
    design-tokens.md                -- 색상/타이포그래피 토큰
    creative-guidelines.md          -- 커스텀 비주얼 가이드라인
```

---

### 2. confluence-wiki -- Confluence 위키 문서 생성기

Confluence에 바로 붙여넣기할 수 있는 Wiki Markup 또는 XHTML 문서를 생성합니다. 선택적으로 draw.io 다이어그램도 함께 생성할 수 있습니다. 7가지 색상 테마, ac:layout 페이지 레이아웃, 11가지 다이어그램 유형을 지원합니다.

**트리거 키워드:**
`confluence`, `wiki`, `cwiki`, `confluence 문서`, `위키 작성`, `컨플루언스`, `draw.io 다이어그램`

**사용 예시:**
```
"시스템 아키텍처를 confluence 문서로 정리해줘"
"장애 보고서를 컨플루언스 위키로 작성해줘"
"API 설계 문서를 wiki markup으로 만들어줘"
```

**주요 특징:**
- Wiki Markup (.wiki) 또는 XHTML (.xhtml) 출력
- ac:layout 기반 페이지 레이아웃 (2단, 3단 구성)
- draw.io 다이어그램 XML 생성 (아키텍처, 플로차트, 네트워크 등)
- GCP 아이콘 지원
- 7가지 색상 테마 (Ocean Blue, Forest Green 등)

**디렉토리 구조:**
```
confluence-wiki/
  SKILL.md                          -- 스킬 명세 및 워크플로우
  references/
    design-system.md                -- 색상 팔레트, ac:layout 패턴
    drawio-diagram-templates.md     -- 다이어그램 유형별 템플릿
    drawio-gcp-reference.md         -- GCP 아이콘 및 스타일 레퍼런스
```

---

### 3. mermaid-diagram -- Mermaid 다이어그램 생성기

20가지 이상의 Mermaid 다이어그램 유형을 지원하는 다이어그램 생성기입니다. 플로차트, 시퀀스 다이어그램, ERD, 클래스 다이어그램, 간트 차트, 마인드맵, C4 모델 등을 정확한 문법으로 생성합니다.

**트리거 키워드:**
`mermaid`, `diagram`, `flowchart`, `sequence diagram`, `ERD`, `다이어그램`, `플로차트`, `시퀀스 다이어그램`

**사용 예시:**
```
"사용자 인증 플로우를 다이어그램으로 그려줘"
"주문 시스템 ERD를 mermaid로 만들어줘"
"MSA 아키텍처를 시퀀스 다이어그램으로 표현해줘"
"프로젝트 일정을 간트 차트로 만들어줘"
```

**주요 특징:**
- 20가지 이상 다이어그램 유형 (flowchart, sequenceDiagram, erDiagram, classDiagram, stateDiagram, gantt, mindmap, C4Context 등)
- 3가지 출력 형식 (Markdown 코드 블록, .mmd 파일, HTML)
- 5가지 내장 테마 (default, forest, dark, neutral, base)
- 커스텀 노드/엣지 스타일링

**디렉토리 구조:**
```
mermaid-diagram/
  SKILL.md                          -- 스킬 명세 및 워크플로우
  references/
    diagram-types.md                -- 전체 다이어그램 유형 문법 패턴
    theme-config.md                 -- 테마 설정 및 커스텀 스타일링
```

---

### 4. deep-search -- 심층 웹 리서치

3-5개의 병렬 에이전트를 동시에 실행하여 다각적인 웹 리서치를 수행합니다. 각 에이전트는 서로 다른 관점(개요, 기술 심화, 실용 사례, 비교 분석, 트렌드)에서 조사하며, 결과를 종합하여 구조화된 보고서를 생성합니다.

**트리거 키워드:**
`deep search`, `research thoroughly`, `find detailed information`, `심층 검색`, `깊이 조사`, `자세히 알아봐`, `리서치 해줘`

**사용 예시:**
```
"React Server Components에 대해 깊이 조사해줘"
"Kubernetes vs ECS 비교를 심층 검색해줘"
"2026년 AI 에이전트 트렌드를 리서치 해줘"
"GraphQL Federation 도입 사례를 자세히 알아봐"
```

**주요 특징:**
- 3-5개 에이전트 병렬 실행으로 빠른 리서치
- 5가지 조사 관점: 개요, 기술 심화, 실용 사례, 비교 분석, 트렌드
- 교차 검증을 통한 정보 신뢰도 확보
- 출처 인용이 포함된 구조화된 보고서 출력

**디렉토리 구조:**
```
deep-search/
  SKILL.md                          -- 스킬 명세 및 워크플로우
  agents/
    broad-researcher.md             -- 개요 조사 에이전트
    technical-researcher.md         -- 기술 심화 에이전트
    practical-researcher.md         -- 실용 사례 에이전트
    comparative-researcher.md       -- 비교 분석 에이전트
    trend-researcher.md             -- 트렌드 분석 에이전트
  references/
    research-patterns.md            -- 리서치 패턴 레퍼런스
```

---

## 참고 사항

- 스킬은 `~/.claude/skills/` 디렉토리에 위치해야 Claude Code가 인식합니다.
- 각 스킬의 `SKILL.md` 파일이 스킬의 핵심 명세이며, `references/` 디렉토리에 참조 자료가 포함됩니다.
- 스킬을 수정하거나 새로운 스킬을 만들고 싶다면 기존 스킬의 구조를 참고하세요.
- 자세한 스킬 문법은 각 스킬의 `SKILL.md` 파일을 확인하세요.
