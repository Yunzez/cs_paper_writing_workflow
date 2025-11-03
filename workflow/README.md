# Paper Writing Workflow

This repository operationalizes a five-stage pipeline for drafting a CS research paper with LLM assistance. Each stage has a dedicated playbook under `workflow/` and writes its outputs into `paper/`.

## Stage Overview
1. **Initial Planning and Outlining** (`stage1_initial_planning.md`)  
   Clarify scope, audience, contributions, and produce a narrative outline plus research brief.
2. **Related Work Refinement** (`stage2_related_work.md`)  
   Fetch references listed in `paper/metadata/references.bib`, summarize them in `paper/related_work_brief.md`, and synthesize positioning insights.
3. **Main Section Writing** (`stage3_main_writing.md`)  
   Use `initial_instruction.md` as the style guide to draft LaTeX prose for core sections under `paper/sections/`.
4. **Multi-Round Review, Rebuttal, and Refinement** (`stage4_review_rebuttal_refine.md`)  
   Run three critic–rebuttal–revision cycles, saving artifacts in `paper/drafts/review_rounds/` and updating the main draft.
5. **Finishing Up Remaining Sections** (`stage5_finishing_up.md`)  
   Polish auxiliary sections (abstract, broader impact, acknowledgements, appendix) and complete the submission checklist.

## Key Directories
- `paper/sections/`: Section-specific LaTeX files that accumulate the draft.
- `paper/drafts/`: Logs, outlines, reviews, and checklists produced across stages.
- `paper/metadata/`: Reference files such as `references.bib`.
- `paper/related_work_brief.md`: Auto-generated summaries of literature.

## How to Use
1. Populate `paper/metadata/references.bib` with BibTeX entries for all papers to be reviewed.
2. Start with Stage 1 and proceed sequentially—later stages assume earlier outputs exist.
3. When prompting an LLM, paste the relevant stage playbook and provide the latest artifacts as context.
4. After completing each stage, review deliverables with collaborators before moving forward.

Refer to `initial_instruction.md` for global narrative and LaTeX conventions that apply to every stage.
