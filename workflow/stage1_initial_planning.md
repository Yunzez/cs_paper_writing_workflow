# Stage 1: Initial Planning and Outlining

## Purpose
Secure the high-level story before drafting any prose. Clarify the problem statement, target venue, primary contributions, evaluation plan, and expected figures so later stages can execute without rework.

## Inputs
- `initial_instruction.md` for narrative and LaTeX style expectations.
- User-supplied project notes: problem definition, hypothesis, datasets, baselines, metrics, timeline, and any existing experiments.
- Optional: prior slide decks, draft notes, or brainstorming documents.

## Deliverables
- `paper/drafts/stage1_research_brief.md`: 1–2 page prose memo covering motivation, audience, contributions, risks, and success criteria.
- `paper/drafts/stage1_outline.md`: hierarchical outline mapping the planned paper sections to key talking points, figures, and evidence.

## Workflow
1. **Elicit missing context.** Have the assistant interview the user to resolve open questions about goals, novelty, collaborators, datasets, compute limits, and target venues or deadlines.
2. **Draft the research brief.** Convert the gathered context into a narrative memo that frames the problem, articulates the thesis, enumerates contributions, lists anticipated figures/tables, and calls out uncertainties to validate later.
3. **Produce the paper outline.** Expand the memo into a section-by-section outline that tracks evidence requirements (figures, metrics, citations) for each subsection. Ensure the outline anticipates the structure of the LaTeX files in `paper/sections/`.
4. **Review with the user.** Highlight any assumptions or gaps that must be resolved before moving to Stage 2.

## Prompt Template
```text
You are an expert research writing partner helping plan a CS paper. Follow the style rules in initial_instruction.md. Collaborate with me to complete Stage 1 of our workflow: initial planning and outlining.

Tasks:
1. Ask clarifying questions about the project until you can confidently articulate the research problem, motivation, target venue, intended audience, existing results, datasets, baselines, compute constraints, collaborators, and deadlines.
2. Produce a Stage 1 research brief: 4–6 paragraphs of narrative prose that frame the problem, why it matters, how our approach differs from prior work, anticipated contributions, evidence we must gather, and major risks/open questions.
3. Produce a Stage 1 outline: a hierarchical outline describing the planned sections for the paper, what evidence or figures each section needs, and links to planned LaTeX files under paper/sections/*.tex.

Output format:
- Begin with \"Clarifying Questions\" and list any remaining information you need.
- After questions are resolved, output \"Stage 1 Research Brief\" followed by the memo.
- Then output \"Stage 1 Outline\" with a numbered or indented outline rendered in Markdown.
- Close with \"Next Checks\" summarizing what we must confirm before Stage 2.
```
