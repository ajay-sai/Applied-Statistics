# Copilot instructions for this repo

## Repo shape (what you’re editing)
- This is a learning repository of **many small, independent exercises**.
- Canonical structure is: one topic folder → many numbered question folders → `README.md` + `solution.ipynb`.
  - Examples: `Basic-Statistics/03_Unbiased_Estimation_of_Variance/`, `Hypothesis-Testing/03_CLT_and_Z_Test/`.

## Conventions to preserve
- **Do not reorganize folders** or rename question directories; numbering is part of navigation.
- Each question folder’s `README.md` follows the same template sections:
  - `## Problem Statement`, `## Approach`, `## Solution` (points to the notebook), `## Resources`, `## LinkedIn Post`, `## Substack Article`.
- Keep edits **scoped to a single question folder** unless the user explicitly asks for repo-wide changes.

## Notebook workflow (how to run)
- Install dependencies from `requirements.txt`:
  - `pip install -r requirements.txt`
- Run notebooks via Jupyter:
  - `jupyter notebook`
- Notebooks are the “source of truth” for implementations; the folder README should stay lightweight and link to `solution.ipynb`.

## What good changes look like here
- When asked to “fill in” a problem, update the folder `README.md` placeholders (HTML comments) with:
  - a clear problem statement, a short approach explanation, and relevant resources.
- When changing a notebook, prefer:
  - reproducible cells (set seeds when simulating),
  - clear markdown headings mirroring the README sections,
  - minimal external data dependencies (generate synthetic data unless a dataset is already present).

## Environment notes
- VS Code settings select the system Python (`.vscode/settings.json`). Avoid adding heavy tooling/config unless requested.

## Where to look first
- High-level overview and workflow: `README.md`
- Dependencies: `requirements.txt`
- Per-question templates: any `*/**/README.md` and sibling `solution.ipynb`
