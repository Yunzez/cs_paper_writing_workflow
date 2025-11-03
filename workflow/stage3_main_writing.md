# Stage 3: Main Section Writing

## Purpose
Transform the approved outline and literature synthesis into polished LaTeX sections for the core of the paper (introduction, related work narrative, method, experiments, discussion, conclusion). This stage relies heavily on `initial_instruction.md` to ensure stylistic consistency.

## Inputs
- `initial_instruction.md` (must be cited verbatim within the prompt).
- Stage 1 outputs (`stage1_research_brief.md`, `stage1_outline.md`).
- Stage 2 outputs (`paper/related_work_brief.md`, `stage2_gap_analysis.md`).
- Any experimental results, figures, or tables available so far.

## Deliverables
- Updated LaTeX files under `paper/sections/*.tex` for core sections.
- `paper/drafts/stage3_progress.md`: log of what was written, pending evidence, and outstanding questions for the user.

## Workflow
1. **Confirm prerequisites.** Verify the outline and literature summaries have been accepted by the user. If results or figures are missing, note placeholders.
2. **Plan the writing order.** Generally follow: introduction → related work narrative → method → experiments → discussion → conclusion. Adjust based on data readiness.
3. **Draft section by section.** For each section, run a dedicated prompt (see template) that provides the relevant outline fragment, literature notes, and any quantitative results. Ensure LaTeX syntax matches the style rules.
4. **Respect citation placeholders.** Insert `[CITATION]` or descriptive placeholders (e.g., `[DWARF SPEC]`) where actual references will later reside. Use `\texttt{\detokenize{...}}` for code-like tokens.
5. **Record progress.** After each section, append to `stage3_progress.md` what was completed, evidence still needed (e.g., final numbers, figure captions), and follow-ups for the user.
6. **Self-review inline.** Re-read each section to confirm narrative flow, cross-references, and transitions between sections.

## Section Prompt Template

```text
You are an expert research writing partner helping plan a CS paper. You are writing Stage 3 of our paper. Follow every style rule in initial_instruction.md. Produce LaTeX prose (no \section commands) for the <SECTION NAME> section, targeting the file paper/sections/<SECTION_FILE>.tex.

Context you must read:
- Stage 1 brief: paper/drafts/stage1_research_brief.md
- Stage 1 outline segment for this section: <paste relevant outline excerpt>
- Stage 2 related work entries that matter: <paste relevant excerpts from paper/related_work_brief.md>
- Stage 2 gap analysis notes: <paste relevant bullets>
- Available experimental evidence: <paste tables/numbers/figure descriptions or note \"TBD\">
```

Writing requirements:
- Maintain narrative paragraphs; only use lists when absolutely necessary.
- Introduce each subsection with an overview paragraph that explains why it matters.
- Use `\texttt{\detokenize{...}}` for any identifiers with underscores.
- Insert citation placeholders like [CITATION] where references will go.
- Align transitions with preceding and following sections specified in the outline.
- Use clear and hierarchical document structures. Employ `subsection`s to break down complex topics into logical, manageable parts.
- When introducing technical concepts, provide detailed explanations. Don't assume the reader is already an expert. For example, when mentioning "DWARF scope chain resolution," explain what it is and how it works.
- When figures are available, they should be included in the document. The surrounding text must be adapted to refer to and describe the figures, explaining their relevance and what they illustrate.
- To clarify complex topics, use concrete examples. This can include code snippets, data excerpts (like DWARF output), or step-by-step walkthroughs of a process.
- Reduce use of ; and -– Prefer sentences with better readability.

**LaTeX Specific**

- Underscores: To ensure proper compilation and robustly handle literal strings, use the `\detokenize{}` command for words that contain underscores. This is the preferred method. For example, `DW_AT_location` should be written as `\texttt{\detokenize{DW_AT_location}}`.
-  Text Formatting: Use `\texttt{}` for code-like text (e.g., variable names, function names) and `\textit{}` for emphasis or to introduce key terms. Never use ` or _ or * for formatting. Use - instead of \- for hyphenation in text.


Output:
- Provide the updated LaTeX content only. Do not wrap in Markdown fences.
- After the LaTeX, summarize \"Outstanding Needs\" listing data, figures, or analysis still required.
