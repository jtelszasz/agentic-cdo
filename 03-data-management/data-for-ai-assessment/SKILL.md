---
name: data-for-ai-assessment
description: Assess an open government dataset's AI-readiness using a synthesized rubric drawn from the ODI, Snowflake, US Commerce, and UK government frameworks. Trigger ONLY when Justin explicitly invokes this skill by name or command — phrases like "/ai-readiness", "run an ai-readiness assessment", "assess this dataset for ai-readiness", "do an ai-readiness review", or "ai-ready assessment". Do NOT trigger on generic dataset questions, data quality reviews, or metadata questions unless Justin explicitly asks for an AI-readiness assessment. This skill produces a four-part inline report (dataset summary + data dictionary, unresolved questions, rubric scores, tiered recommendations) for any municipal open data portal — ArcGIS Hub, Socrata, or CKAN.
---

# AI-Readiness Assessment

A repeatable, framework-synthesized assessment for evaluating whether a municipal open dataset is ready for use by AI systems. The target audience is Chief Data Officers and municipal data leaders.

## When this skill applies

Trigger only on explicit invocation. Example triggering phrases:
- "/ai-readiness on [dataset]"
- "Run an AI-readiness assessment on [dataset]"
- "Do an AI-ready review of [dataset URL]"
- "Assess [dataset] against the AI-readiness rubric"

If Justin asks a generic question about a dataset's metadata or quality without invoking this skill, do not activate it. Answer the narrower question instead and, if appropriate, mention this skill exists as a deeper option.

## Inputs the skill expects

Before starting, confirm you know:
1. **Which dataset** — a title, a portal URL, a Hub ID, or a permalink.
2. **Which portal type** — ArcGIS Hub, Socrata, or CKAN. Infer from the URL if possible; ask if ambiguous.
3. **Optional scoping** — the user may ask you to focus on a specific framework or skip the publisher-research phase. Default to the full four-phase workflow below.

If the dataset identifier is missing or ambiguous, ask once before proceeding.

## The workflow — four phases

Work through these in order. Each phase produces a section of the final inline report. Don't skip phases unless the user explicitly asks you to.

### Phase 1 — Dataset inventory

Pull the publisher-provided metadata and a sample of actual records. The goal is a reconstructed data dictionary and a candid assessment of what *isn't* documented.

Steps:
1. **Retrieve dataset metadata** using the appropriate portal tool:
   - ArcGIS Hub → OpenContext MCP (`arcgis__get_dataset`)
   - Socrata → `web_fetch` on the dataset's `/api/views/{id}.json` endpoint
   - CKAN → `web_fetch` on the `/api/3/action/package_show?id={id}` endpoint
2. **Sample 5–10 records** with the portal's query interface to see actual field names and values. The Hub/metadata record almost never contains the field-level schema — the sample is how you find it.
3. **Reconstruct a data dictionary** as a table with columns: Field, Observed values/format, Inferred meaning, Confidence (High/Medium/Low). Apply the confidence rubric in `references/confidence-rubric.md`.
4. **List unresolved questions** as a separate bulleted list. Be specific and concrete — "I don't know the timezone of ExpirationDate" is useful; "the documentation is thin" is not. This list drives Phase 2.

Don't guess. If a field's meaning isn't clear from name + observed values + publisher docs, mark it Low confidence and add it to the unresolved list.

### Phase 2 — Publisher research

For each unresolved question from Phase 1 that could plausibly be answered by the publishing agency, do targeted research.

Steps:
1. **Identify the publishing agency** from the dataset owner field. For Baltimore datasets, that's usually a specific department (DHCD, DOT, Planning, etc.).
2. **Search** with `web_search` for the agency + the unresolved topic. Good search patterns: "[agency] [dataset topic] data dictionary", "[agency] [field name] definition", "[agency] [code list name]".
3. **Fetch** the most relevant agency documentation pages with `web_fetch`. Expect some URLs to fail (403s, redirects, dynamic content); fall back to additional searches rather than giving up.
4. **Categorize findings** into three buckets for the final report:
   - **Confirmed** — publisher docs directly answer the Phase 1 question
   - **Partially resolved** — publisher docs give context but don't fully answer
   - **Still unresolved** — no authoritative source found; flag as a metadata gap

Don't invent publisher intent. If the publisher's site is silent on a question, that silence is itself a finding.

### Phase 3 — Rubric scoring

Apply the synthesized seven-dimension rubric in `references/rubric.md`. The rubric merges the ODI, Snowflake, Commerce, and UK frameworks into one scoring system to avoid four redundant assessments.

Steps:
1. Read `references/rubric.md` for the full rubric, scoring criteria, and evidence prompts.
2. Score each of the seven dimensions 0–2 (0 = absent, 1 = partial, 2 = strong) with specific evidence drawn from Phases 1 and 2.
3. Compute a total (out of 14) and express it as a rough ratio.
4. Present as a scored table in the final report — one row per dimension with score, evidence, and gap.

Score conservatively. A dimension earns 2 only if the publisher has explicitly documented it in a way an AI system could ingest. "It's probably fine" is not evidence.

### Phase 4 — Tiered recommendations

Generate prioritized recommendations organized by urgency, using the template in `references/recommendations-tiers.md`.

Steps:
1. Read `references/recommendations-tiers.md` for the tier definitions and common patterns by framework.
2. Produce **Tier 1** (blocking — must be fixed before responsible AI use), **Tier 2** (substantial — meaningful improvement), **Tier 3** (modernization — for agentic/generative AI readiness).
3. Each recommendation should cite which framework(s) call for it, briefly.
4. End with a **strategic framing** paragraph pulling the findings up to a CDO-audience level — what this tells us about municipal open data generally, not just this dataset.

Don't list every possible improvement. Prioritize ruthlessly — a recommendation is only in Tier 1 if its absence actually blocks AI use.

## Output format — four-part inline report

Always use this exact structure. The headings are fixed; the content is dataset-specific.

```markdown
# AI-Readiness Assessment: [Dataset Name]

## Dataset summary and data dictionary

[2-3 sentences of dataset context, then the reconstructed data dictionary table.]

## Unresolved questions and publisher research findings

[Three subsections: Confirmed, Partially resolved, Still unresolved.]

## Rubric scores

[Table: Dimension | Score (0–2) | Evidence | Gap. Then total.]

## Recommendations

### Tier 1 — Blocking
### Tier 2 — Substantial
### Tier 3 — Modernization

## Strategic framing

[One short paragraph lifting findings to CDO-audience relevance.]
```

Output is inline in chat. Do not create files or artifacts unless the user explicitly asks.

## Tone and audience

The audience is Justin's CDO peers via the Civic Analytics Network. Use direct, substantive language — this isn't a sales document. Paraphrase framework guidance rather than quoting it verbatim. Score harshly but fairly: most municipal datasets will score low, and pretending otherwise doesn't help anyone.

## Common failure modes to avoid

- **Scoring generously.** If you can't point to evidence in the publisher's metadata or documentation, the dimension is not strong.
- **Guessing at field meaning.** Low confidence is a legitimate and useful finding.
- **Skipping Phase 2.** The publisher's website usually resolves at least half of Phase 1's unresolved questions. Doing the research meaningfully changes the rubric scores.
- **Quoting frameworks verbatim.** Synthesize. The reader doesn't need four redundant score cards.
- **Producing a flat recommendations list.** Tier the recommendations — that's the whole point of this section.
- **Adding new sections.** The four-part output structure is fixed.

## References

- `references/confidence-rubric.md` — How to score field-meaning confidence in Phase 1
- `references/rubric.md` — Full seven-dimension scoring rubric for Phase 3
- `references/recommendations-tiers.md` — Tier definitions and common patterns for Phase 4
- `references/portal-tools.md` — Portal-specific retrieval guidance (ArcGIS Hub, Socrata, CKAN)