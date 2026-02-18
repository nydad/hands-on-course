# Deep Research Patterns Reference

## Multi-Agent Research Architecture

Based on Anthropic's research system design, this document outlines proven patterns for effective deep research.

### Orchestrator-Worker Pattern

The most effective multi-agent research pattern uses:
- **Lead Agent (Orchestrator)**: Coordinates the research process
- **Worker Agents (3-5)**: Execute parallel searches on different angles
- **Synthesis Phase**: Consolidates and analyzes all findings

### Performance Benchmarks

From Anthropic's internal research:
- Multi-agent system with Claude Opus 4 lead + Sonnet 4 workers outperformed single-agent by **90.2%**
- Parallel execution cuts research time by **up to 90%** for complex queries
- Token usage explains **80%** of output quality variance

## Search Strategy: Broad to Narrow

Expert researchers follow a "funnel" approach:

```
BROAD QUERIES
     │
     ▼  Evaluate landscape
MEDIUM QUERIES
     │
     ▼  Identify key sources
NARROW QUERIES
     │
     ▼  Extract specific details
TARGETED FETCHES
```

### Implementation

1. Start with short, broad queries to understand the landscape
2. Evaluate available sources and identify promising directions
3. Progressively narrow focus based on findings
4. Deep dive into the most relevant sources

## Query Optimization

### Effective Search Queries

| Purpose | Pattern | Example |
|---------|---------|---------|
| Definition | "what is [X]" | "what is React Server Components" |
| How-to | "[X] tutorial [year]" | "kubernetes tutorial 2026" |
| Comparison | "[X] vs [Y]" | "PostgreSQL vs MySQL" |
| Problems | "[X] common issues" | "Docker common issues" |
| Best Practice | "[X] best practices [year]" | "API design best practices 2026" |
| Latest | "[X] [current year]" | "AI trends 2026" |

### Query Refinement Tips

- Add year for current information
- Include specific version numbers when relevant
- Use quotes for exact phrases
- Add "site:domain.com" for specific sources

## Source Evaluation

### Tier 1 Sources (Highest Priority)
- Official documentation
- Academic papers (peer-reviewed)
- Official blogs from technology creators

### Tier 2 Sources (High Value)
- Reputable tech publications (InfoQ, Martin Fowler, etc.)
- Conference talks and presentations
- Well-maintained GitHub repositories

### Tier 3 Sources (Supplementary)
- Technical blog posts
- Stack Overflow answers (highly voted)
- YouTube tutorials (from verified experts)

### Red Flags
- No date or very old content
- No author attribution
- Promotional content disguised as information
- Contradicts official documentation

## Synthesis Best Practices

### Information Consolidation

1. **Cluster by Theme**: Group related findings together
2. **Identify Consensus**: Note where multiple sources agree
3. **Flag Conflicts**: Highlight contradictory information
4. **Trace to Source**: Every fact should have attribution

### Output Quality Checklist

- [ ] All claims have source citations
- [ ] Conflicting information is noted
- [ ] Technical accuracy verified against official docs
- [ ] Current information (check dates)
- [ ] Balanced perspective (pros and cons)
- [ ] Actionable insights provided

## Error Recovery

### When Agents Return Poor Results

1. **Refine Query**: Make search terms more specific
2. **Change Angle**: Try different search approach
3. **Spawn Additional Agent**: Target the gap specifically
4. **Direct Search**: Fall back to manual WebSearch

### When Sources Conflict

1. Prioritize official documentation
2. Check publication dates (prefer recent)
3. Look for primary sources
4. Note the conflict in output

## Token Efficiency

### Reduce Token Usage

- Use `files_with_matches` mode in Grep for initial scans
- Extract only relevant sections from web pages
- Avoid repeating raw agent output in synthesis
- Summarize rather than quote extensively

### Context Management

- Each parallel agent gets isolated context
- Prevents context window pollution
- Enables higher quality focused research
- Synthesis should be concise consolidation
