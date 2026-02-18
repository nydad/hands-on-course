---
name: deep-search
description: Performs deep web research using 3-5 parallel agents for comprehensive information gathering. Use when asked to "deep search", "research thoroughly", "find detailed information", "심층 검색", "깊이 조사", "자세히 알아봐", "리서치 해줘", or when complex questions require multi-source investigation.
---

# Deep Search

Orchestrates 3-5 parallel research agents to conduct comprehensive web research, gathering information from multiple perspectives and synthesizing results into actionable insights.

## When to Use

- User asks for in-depth research on a topic
- Complex questions requiring multi-source verification
- Technology comparisons or evaluations
- Market research or trend analysis
- Understanding best practices across different sources
- Any query where shallow search would be insufficient

## Architecture

```
┌─────────────────────────────────────────────────────────┐
│                   ORCHESTRATOR (You)                     │
│   - Analyze user query                                   │
│   - Design search strategy                               │
│   - Spawn parallel agents                                │
│   - Synthesize results                                   │
└─────────────────────────────────────────────────────────┘
                           │
           ┌───────────────┼───────────────┐
           │               │               │
           ▼               ▼               ▼
    ┌──────────┐    ┌──────────┐    ┌──────────┐
    │ Agent 1  │    │ Agent 2  │    │ Agent 3  │    + Agent 4, 5
    │ Broad    │    │ Technical│    │ Practical│
    │ Overview │    │ Deep Dive│    │ Examples │
    └──────────┘    └──────────┘    └──────────┘
           │               │               │
           └───────────────┼───────────────┘
                           ▼
                 ┌─────────────────┐
                 │  SYNTHESIS      │
                 │  - Consolidate  │
                 │  - Deduplicate  │
                 │  - Structure    │
                 └─────────────────┘
```

## Core Instructions

### Phase 1: Query Analysis

1. **Understand the request**
   - Identify the core topic and subtopics
   - Determine the depth required
   - Note any specific constraints or preferences

2. **Design search angles** (pick 3-5 based on query complexity)
   - **Broad Overview**: General understanding, definitions, context
   - **Technical Deep Dive**: Implementation details, specifications, architecture
   - **Practical Examples**: Real-world use cases, tutorials, how-tos
   - **Comparative Analysis**: Alternatives, pros/cons, benchmarks
   - **Trend/Future**: Latest developments, roadmap, community sentiment

### Phase 2: Parallel Agent Execution

Launch 3-5 Task agents **simultaneously** in a SINGLE message with multiple Task tool calls.

Each agent should be configured as:
- **subagent_type**: "general-purpose"
- **description**: Brief 3-5 word summary
- **prompt**: Detailed research instructions including:
  - Specific angle to investigate
  - What tools to use (WebSearch, WebFetch)
  - What information to gather
  - Output format requirements

**Agent Prompt Template:**

```markdown
You are a research agent focused on [ANGLE].

TOPIC: [User's query]

YOUR MISSION:
1. Use WebSearch to find relevant sources about [specific aspect]
2. Use WebFetch to extract detailed information from top results
3. Focus on: [specific focus areas]

OUTPUT FORMAT:
## Key Findings
- [Bullet points of main discoveries]

## Sources
- [URLs with brief descriptions]

## Notable Quotes/Data
- [Specific facts, statistics, or expert opinions]

DO NOT: Make assumptions or include information you cannot verify.
DO: Cite all sources and be specific about where information came from.
```

### Phase 3: Result Synthesis

After all agents complete, synthesize their findings:

1. **Consolidate** - Merge findings from all agents
2. **Deduplicate** - Remove redundant information
3. **Cross-verify** - Note where sources agree or conflict
4. **Structure** - Organize into coherent narrative
5. **Cite** - Include all sources with markdown links

## Research Angles Reference

| Angle | Focus | Search Keywords |
|-------|-------|-----------------|
| **Broad Overview** | Definitions, history, basic concepts | "what is", "introduction to", "basics of" |
| **Technical Deep Dive** | Architecture, implementation, specs | "how does X work", "X architecture", "X internals" |
| **Practical Examples** | Tutorials, use cases, code samples | "X tutorial", "X example", "how to use X" |
| **Comparative Analysis** | Alternatives, benchmarks, pros/cons | "X vs Y", "X alternatives", "X comparison" |
| **Trend Analysis** | Latest news, future direction | "X 2026", "X roadmap", "X latest updates" |

## Output Format

Present research results in this structure:

```markdown
# Deep Research: [Topic]

## Executive Summary
[2-3 sentence overview of key findings]

## Detailed Findings

### [Subtopic 1]
[Content with inline citations]

### [Subtopic 2]
[Content with inline citations]

### [Subtopic 3]
[Content with inline citations]

## Key Insights
- [Insight 1]
- [Insight 2]
- [Insight 3]

## Recommendations
[If applicable, actionable recommendations based on research]

## Sources
- [Source 1](URL) - Brief description
- [Source 2](URL) - Brief description
- [Source 3](URL) - Brief description
```

## Example Usage

**User Query**: "React Server Components에 대해 깊이 조사해줘"

**Agent Distribution**:
1. **Broad Agent**: RSC 개념, 기본 원리, SSR과의 차이
2. **Technical Agent**: RSC 아키텍처, 동작 방식, 제약사항
3. **Practical Agent**: RSC 사용 예시, 튜토리얼, 마이그레이션 가이드
4. **Comparative Agent**: RSC vs SSR vs CSR, Next.js vs Remix 비교
5. **Trend Agent**: RSC 최신 업데이트, 커뮤니티 반응, 로드맵

## Best Practices

1. **Always launch agents in parallel** - Use single message with multiple Task calls
2. **Be specific in agent prompts** - Vague prompts yield vague results
3. **Include year in searches** - Add "2026" for current information
4. **Verify across sources** - Note when sources conflict
5. **Cite everything** - Every fact should have a source
6. **Synthesize, don't just aggregate** - Add value through analysis

## Error Handling

- If an agent fails, note the gap and continue with available results
- If all agents fail, fall back to direct WebSearch
- If results are insufficient, spawn additional targeted agents

## Token Efficiency

- Parallel execution reduces wall-clock time by 70-90%
- Each agent has isolated context, preventing window pollution
- Synthesis phase should be concise - avoid repeating raw agent output
