# Copilot instructions for this repo

## What this repo is

- A learning repository of **many small, independent statistics exercises**.
- Canonical structure is: topic folder → numbered question folder → `README.md` + (usually) `solution.ipynb`.
  - Example: `Basic-Statistics/03_Unbiased_Estimation_of_Variance/`.

## Golden rules (don’t break navigation)

- **Do not rename or reorganize** topic/question directories; the numbering is part of the repo’s navigation.
- Keep changes **scoped to a single question folder** unless explicitly asked for repo-wide edits.

## Per-question contract (README + notebook)

- Each question folder’s `README.md` follows the same sections:
  - `## Problem Statement`, `## Approach`, `## Solution` (links to the notebook), `## Resources`, `## LinkedIn Post`, `## Substack Article`.
- The notebook (`solution.ipynb`) is the **source of truth** for code/math/plots; keep the folder `README.md` lightweight and pointing to it.

## How to run

- Install dependencies: `pip install -r requirements.txt`
- Launch notebooks: `jupyter notebook`
- Common libraries already in `requirements.txt`: numpy/pandas/scipy/statsmodels/matplotlib/seaborn (+ scikit-learn, lifelines).

## Notebook patterns to preserve

- Prefer reproducibility: set a random seed once near the top (many notebooks use `np.random.seed(42)`).
- Keep clear markdown structure (commonly starts with `# Solution` and `## Import Libraries`).
- Avoid accidental duplication (e.g., repeated import/seed cells) unless it’s pedagogically necessary.
- Minimize external data dependencies; generate synthetic data unless the folder already includes a dataset.

## Repo-specific authoring helpers

- Prompts for repurposing notebooks into posts live in `.github/prompts/` (e.g., LinkedIn/Substack repurpose).

### Intended workflow (use these prompts in order)

1. `ingestContentToQuestionFolder.prompt.md`

- Input: target question folder + pasted problem/solution text.
- Output: update that folder’s `README.md` (fixed section order) and create/update `solution.ipynb` with a runnable, well-structured draft.

2. `reviewStatsNotebook.prompt.md`

- Run from a clean kernel top-to-bottom; fix hidden-state issues, duplicated imports/seed cells, and reproducibility problems.
- If linting is requested, run Ruff and apply safe fixes; keep changes local to the question folder.

3. `repurposeNotebookToLinkedInSubstack.prompt.md`

- Ground writing in the folder’s `README.md` + `solution.ipynb`.
- Output: LinkedIn TLDR + Substack draft, plus two paste-ready README link lines for `## LinkedIn Post` and `## Substack Article`.

## Where to look first

- Overview + workflow: `README.md`
- Dependencies: `requirements.txt`
- A representative solved folder: `Basic-Statistics/03_Unbiased_Estimation_of_Variance/`
