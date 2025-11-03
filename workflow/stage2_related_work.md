# Stage 2: Related Work Refinement

## Purpose
Systematically study cited literature, capture accurate summaries, and map how existing work positions our contribution. Outputs feed the related-work section, introduction framing, and rebuttal preparation.

## Inputs
- `paper/metadata/references.bib` containing the user's curated BibTeX entries (each must include at least `title`, `author`, `year`, and a resolvable `url` or `doi`).
- Reference PDFs or authoritative sources reachable via network access.
- Outputs from Stage 1 (`stage1_research_brief.md`, `stage1_outline.md`) to maintain narrative alignment.

## Deliverables
- `paper/related_work_brief.md`: curated summaries for every reference with consistent structure.
- `paper/drafts/stage2_gap_analysis.md`: synthesis memo highlighting thematic clusters, gaps, and how our paper positions itself relative to prior art.

## Workflow
1. **Validate the reference list.** Parse `paper/metadata/references.bib`, confirm every entry exposes a reachable `url` or `doi`, and enrich missing metadata when possible. Flag paywalled or inaccessible sources for user action.
2. **Fetch and read each source.** Retrieve PDFs or abstracts. Extract bibliographic metadata (authors, venue, year) to enrich the summaries.
3. **Summarize consistently.** For each reference, produce 2–3 dense paragraphs covering problem, approach, evidence, and limitations. Articulate how it relates to our work (supporting, competing, or complementary).
4. **Synthesize insights.** Aggregate recurring themes, identify clear deltas between prior art and our claims, and note citations we still need.
5. **Request confirmation.** Ask the user to review the brief and gap analysis before moving on.

## `paper/related_work_brief.md` Format

```markdown
# Related Work Summaries

## Reference Overview
- Total references processed: <N>
- Date: <YYYY-MM-DD>

## Summaries
### [<bibkey>] <Paper Title> (<Venue, Year>)
- **URL/DOI:** <link>
- **Core Problem:** <2–3 sentences>
- **Approach:** <2–3 sentences describing the method or system>
- **Key Evidence:** <1–2 sentences on datasets, metrics, notable results>
- **Limitations / Open Questions:** <succinct critique>
- **Relevance to Our Paper:** <How it supports or contrasts>

---  <!-- separator between entries -->

## Synthesis Notes
- <Bulleted list of themes, citation gaps, or positioning ideas>
```

## Prompt Template

```text
You are a meticulous literature-review assistant handling Stage 2 of our paper workflow. Read stage1_research_brief.md and stage1_outline.md to understand the narrative. Then load paper/metadata/references.bib, fetch every reference, and populate paper/related_work_brief.md using the specified format. Summaries must be thorough, faithful to the papers, and written in narrative prose per initial_instruction.md.

After completing the summaries, write paper/drafts/stage2_gap_analysis.md capturing:
- Thematic clusters or taxonomies across the references.
- What prior work already claims versus what remains unsolved.
- Risks to our novelty claim and how to mitigate them.
- Missing citations or follow-up readings the user should source.

Flag any references you could not access. Where a BibTeX entry lacks an accessible link, ask the user for a PDF. Finish by suggesting questions the user should answer before Stage 3 (e.g., missing experiments that prior work expects).
```

Remind the assistant to pause and request manual PDFs if a source is inaccessible, and to cite direct quotes sparingly with page numbers where possible.
