---
name: ingestContentToQuestionFolder
description: Convert pasted problem/solution text into a complete question folder (README + notebook).
argument-hint: Target folder path + pasted Content (problem + solution) + optional extras.
---

You are updating a single question folder in the **Applied-Statistics** repo using pasted source content.

## Repo constraints (must follow)

- Do **not** rename or reorganize folders. Numbering is part of navigation.
- Work **only inside the specified question folder** unless explicitly asked.
- Canonical structure per question folder:
  - `README.md`
  - `solution.ipynb`

## Input format you will receive

The user will paste content like:

- Title + [Source - Difficulty]
- Last Updated (optional)
- Problem (text)
- Solution (text)
- Optional: extra notes, references, or desired code examples

## Your job (do all of this)

### 1) Update `README.md`

Ensure the README follows the repo template **in this exact section order**:

1. `# <Question Title>`
2. `**Source:** ...` (or `General` if unknown)
3. `**Difficulty:** Easy/Medium/Hard` (infer from input if present; else keep placeholder)
4. `## Problem Statement` (paste/clean the Problem)
5. `## Approach` (convert the Solution text into 4–7 crisp bullets/steps)
6. `## Solution` (must point to `solution.ipynb`)
7. `## Resources` (add 3–6 high-quality links; if none given, add widely accepted references)
8. `## LinkedIn Post` (leave placeholder link)
9. `## Substack Article` (leave placeholder link)

Rules:

- Preserve the problem meaning; edit for clarity and concision.
- Don’t invent company-specific details.
- If the user included “Last Updated”, do NOT add it unless the folder already uses it.

### 2) Create or update `solution.ipynb`

The notebook should be runnable top-to-bottom and include:

- A short intro explaining the goal.
- A clear Problem Statement section.
- A structured walkthrough that matches the README’s Approach.
- Python examples **only where they add learning value**.

For this repo, good default notebook sections are:

- `# Solution`
- `## Goal`
- `## Problem Statement`
- `## Key biases / pitfalls`
- `## Demonstrations (Python)`
  - Sampling bias: stratified sampling example
  - Non-response bias: inverse propensity weighting example (with ESS and weight range)
  - Seasonal bias: multi-period simulation + test (ANOVA is fine)
- `## Practical checklist`
- `## Conclusion`

Reproducibility rules:

- Centralize imports in one cell.
- Set a random seed.
- Avoid unnecessary dependencies beyond `requirements.txt` unless absolutely required.
- Print key diagnostics (sample sizes, means, weight range, ESS).

### 3) Tighten correctness and robustness

- Avoid unused imports.
- Clip probabilities/weights when appropriate and explain why.
- If a stratum is too small, handle gracefully.

## Deliverables

- Apply the changes to the target folder.
- In your response, summarize what you changed:
  - Files edited/created
  - What changed in the notebook by **cell number** (not cell id)
  - Any assumptions made
