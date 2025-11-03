# Stage 4: Multi-Round Review, Rebuttal, and Refinement

## Purpose
Pressure-test the draft with adversarial feedback, defend decisions, and integrate improvements. Run three consecutive review rounds where the assistant serves as (1) a harsh external reviewer, (2) the author crafting rebuttals, and (3) an editor implementing revisions.

## Inputs
- Latest LaTeX sections under `paper/sections/*.tex`.
- Stage 3 progress log (`paper/drafts/stage3_progress.md`) and outstanding needs.
- Related work brief and gap analysis (Stage 2 outputs).
- Figures, tables, or experimental updates since Stage 3.

## Deliverables
- For each round `n ∈ {1,2,3}`:
  - `paper/drafts/review_rounds/round<n>_critique.md`
  - `paper/drafts/review_rounds/round<n>_rebuttal.md`
  - `paper/drafts/review_rounds/round<n>_revision_plan.md`
- Updated LaTeX sections reflecting agreed revisions.
- Entries in `paper/drafts/stage4_decision_log.md` summarizing accepted changes and unresolved risks.

## Round Structure
Each round consists of three prompts executed sequentially:

### 1. Reviewer Critique
Role-play an unforgiving program committee reviewer (\"Reviewer #<n>\"). Evaluate significance, originality, technical quality, experimental rigor, clarity, and reproducibility. Demand concrete evidence, spot missing citations, and question methodology. Output structured findings with severity tags (Blocker/Major/Minor/Nit).

### 2. Author Rebuttal
Switch roles to the author responding to the critique. Address every comment explicitly, referencing data or promising realistic fixes. Admit weaknesses honestly and propose concrete remediation steps (additional experiments, clarifications, figure updates).

### 3. Revision Plan & Implementation
Act as an editor synthesizing the exchange. Generate a prioritized todo list (fix immediately vs. future work). Implement textual revisions directly in the relevant `paper/sections/*.tex` files when the fix is editorial. When a fix requires new experiments or data, record an action item instead.

Escalate unresolved blockers to the user before proceeding to the next round.

## Prompt Templates

### Reviewer Critique (`round<n>_critique.md`)
```text
You are Reviewer #<n> for a top-tier CS conference. Read the entire draft (paper/sections/*.tex) and Stage 3/4 logs. Produce the harshest honest review you can. Judge novelty, evidence, clarity, and broader impact. Cite specific sections and lines when possible.

Format:
- Summary
- Strengths (brief)
- Weaknesses (prioritize blockers, it should harsh)
- Detailed Comments (numbered, each tagged Blocker/Major/Minor/Nit)
- Questions for Authors
```

### Author Rebuttal (`round<n>_rebuttal.md`)
```text
Switch to the author role. Respond point-by-point to Reviewer #<n>'s comments. For each critique, provide:
- Restatement of the comment
- Direct rebuttal or acknowledgement
- Action plan (cite which section/file will change or note new experiments required)
Maintain a professional, data-backed tone. Highlight evidence from Stage 2/3 materials or explain timelines for additional work.
```

### Revision Plan & Implementation (`round<n>_revision_plan.md`)
```text
Now act as the editor implementing agreed changes. Create:
1. Immediate Revisions: edits you will apply now (with file paths).
2. Pending Actions: tasks that require new data/experiments.
3. Risks Left Open: issues that might still draw reviewer criticism.

After listing the plan, apply the immediate revisions to the appropriate paper/sections/*.tex files, respecting initial_instruction.md style. Conclude with a status update appended to paper/drafts/stage4_decision_log.md that notes key decisions for Round <n>.
```

## Execution Tips
- Before each round, snapshot unresolved issues from previous rounds so progress is visible.
- Ensure implemented edits maintain cross-section coherence; if one section changes, update references elsewhere.
- Use `[CITATION]` placeholders instead of drafting new bibliographic entries.
- If a reviewer demands new experiments that are unavailable, craft a rebuttal explaining planned future work and flag it in the decision log.
- After Round 3, compile a short summary in `stage4_decision_log.md` aligning remaining tasks with Stage 5.
