---
name: reviewStatsNotebook
description: Review an applied-stats notebook for correctness, reproducibility, and clarity.
argument-hint: Notebook or selected cells + goals (accuracy, narrative, visuals, robustness).
---

You are reviewing and improving an applied-statistics Jupyter notebook.

## Inputs

- The current notebook (or the selected cells).
- The user’s goals (e.g., verify correctness, fix issues, improve explanations, add visualizations, improve reproducibility).

## What to do

1. **Run from a clean kernel**

   - Restart kernel and run cells top-to-bottom.
   - Note any missing dependencies, import errors, hidden state dependencies, or execution-order assumptions.

2. **Run Ruff checks and fix issues (lint + format)**

   - Run Ruff on the notebook (and any helper `.py` files in the same question folder, if present).
   - Apply safe auto-fixes first, then format:
     - `ruff check --fix <path>`
     - `ruff format <path>`
   - Treat Ruff findings as real quality issues to resolve, not just to report:
     - Fix unused/duplicated imports, undefined names, shadowing, brittle exception handling, and dead code.
     - Prefer small, targeted changes that preserve the notebook’s teaching intent.
   - If a Ruff rule conflicts with the pedagogical goal, use the smallest, most local suppression (e.g., `# noqa: <RULE>` on a single line) and explain why.
   - If Ruff is missing from the environment, add it to `requirements.txt` (lightweight dev dependency) and ensure the notebook still runs end-to-end.

3. **Validate the statistical goal and data**

   - Identify the estimand/target (mean difference, regression coefficient, CI coverage, p-value, effect size, etc.).
   - Clarify what is observed vs simulated vs assumed.
   - Check data hygiene: missing values, encoding, units, duplicates, leakage, train/test contamination.

4. **Check technical correctness**

   - Verify formulas, estimators, transformations, and units.
   - Validate statistical tests/models against their assumptions (independence, normality/CLT, equal variance, linearity, etc.).
   - Verify interpretation of p-values, confidence intervals, effect sizes, and practical significance.
   - Identify conceptual pitfalls (selection bias, confounding, multiple testing, post-hoc choices, model misspecification, leakage).
   - Flag where results come from _pedagogical simulations_ vs _real-world observable data_.

5. **Check code quality & robustness**

   - Ensure random seeds are set consistently and reproducibly per section.
   - Remove/avoid no-op or misleading code.
   - Add guardrails where needed (e.g., safe division, clipping probabilities, handling empty groups/strata, stable sampling sizes).
   - Prefer vectorized operations over slow `apply` where practical.
   - Keep imports centralized; ensure required packages are listed (e.g., in `requirements.txt`).

6. **Add diagnostics that build trust**

   - Always report the key summary statistics relevant to the goal (means/medians, variability, sample sizes).
   - For hypothesis tests: include assumptions, effect sizes, confidence intervals, and interpretation.
   - For regression/classification: show residual diagnostics, calibration/ROC if relevant, and check multicollinearity/outliers.
   - For simulations: verify convergence/coverage with multiple runs and report Monte Carlo error.
   - For sampling/stratification/weighting (if present): show achieved sample sizes, weight ranges, effective sample size (ESS), and overlap/positivity checks.

7. **Improve teaching/narrative structure**

   - Add a short **Goal / Setup / Key takeaway** for each section.
   - Replace placeholders with concise text.
   - Add a compact results table comparing baseline vs improved (and/or true vs observed vs corrected where applicable).
   - Keep markdown headings consistent and scannable.

8. **Improve visuals**

   - Add plots that directly support the claims (distributions, bias shift, corrected vs true, trends).
   - Label axes, include legends, and use consistent bins/scales.
   - Prefer fewer, clearer plots over many redundant ones.

9. **Deliverables**
   - Provide:
     - A concise list of issues found (runtime + conceptual).
   - Ruff summary: what was fixed automatically vs manually, and any remaining suppressions with justification.
     - Specific improvements with rationale.
     - If editing files: make minimal, targeted edits and ensure the notebook runs end-to-end.

## Output format

- Summarize findings in sections:
  - Accuracy & assumptions
  - Bugs / fragile spots
  - Improvements (high impact first)
  - Optional enhancements
- If you make notebook edits, describe what changed and where (by cell number), and confirm it runs cleanly.
