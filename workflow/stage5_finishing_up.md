# Stage 5: Finishing Up Remaining Sections

## Purpose
Polish the paper for submission once the core sections survive Stage 4. Complete the remaining front/back-matter, ensure consistency, and prepare submission assets.

## Inputs
- Finalized core sections from Stage 3/4.
- Stage 4 decision log highlighting open risks.
- Venue-specific formatting or checklist requirements (if available).

## Deliverables
- Completed LaTeX files for auxiliary sections: `abstract.tex`, `broader_impact.tex`, `acknowledgements.tex`, `appendix.tex`, plus any other venue-required sections.
- Updated `paper/drafts/stage5_submission_checklist.md` covering formatting, references, figures, and reproducibility artifacts.
- Optional: camera-ready to-do list if additional steps remain (e.g., anonymization, artifact submission).

## Workflow
1. **Review outstanding items.** Scan `stage4_decision_log.md` and `stage3_progress.md` for unresolved tasks.
2. **Draft auxiliary sections.** Use the provided prompt template to fill each front/back-matter file, grounding claims in the latest results. Ensure abstract and conclusion align with evidence and do not promise undone work.
3. **Proofread globally.** Check transitions, consistent terminology, citation placeholders, figure references, and grammar.
4. **Construct submission checklist.** Document compliance with venue formatting, double-check references, verify figures render, and note any remaining tasks (e.g., camera-ready edits).
5. **Package artifacts.** If the venue requires supplementary material or code, note packaging actions in the checklist.

## Prompt Template for Auxiliary Sections
```text
You are finalizing Stage 5 of our paper workflow. Read the full draft (paper/sections/*.tex) plus logs in paper/drafts. Fill the following LaTeX files with polished prose adhering to initial_instruction.md:
- paper/sections/abstract.tex
- paper/sections/broader_impact.tex
- paper/sections/acknowledgements.tex
- paper/sections/appendix.tex (summaries of proofs, algorithm details, or extra experiments)

Writing requirements:
- Keep the abstract within the venue's word limit; summarize motivation, method, key results, and significance.
- Broader impact should discuss ethics, risks, mitigations, and societal implications.
- Acknowledgements should remain anonymized unless the venue permits naming.
- Appendix may include algorithmic details, ablations, or proofs referenced in the main text.

After drafting, output a \"Submission Checklist\" section that updates paper/drafts/stage5_submission_checklist.md with:
- Formatting compliance (page/word limits, margins, template version).
- References status (placeholders replaced?).
- Figure/table readiness (resolution, captions).
- Reproducibility artifacts (code, datasets, configs).
- Final QA tasks before submission.
```

## Final Touches
- Run LaTeX compilation to confirm no errors (e.g., missing references) once placeholders are replaced.
- Replace `[CITATION]` tags with actual BibTeX keys before submission.
- Coordinate with co-authors for final approvals and sign-offs.
