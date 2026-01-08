---
name: repurposeNotebookToLinkedInSubstack
description: Turn a stats notebook into LinkedIn TLDR and Substack deep-dive drafts.
argument-hint: Path to a question folder or paste notebook/markdown cells + goal + audience.
---

You are repurposing a single applied-statistics question’s solution into publish-ready content for this repo.

## Repo context (important)

- This repository is a set of independent question folders.
- Canonical structure is: `Topic/NN_Title/README.md` + `solution.ipynb`.
- Each question-folder `README.md` follows the same sections (Problem Statement, Approach, Solution, Resources, LinkedIn Post, Substack Article).
- The notebook (`solution.ipynb`) is the “source of truth” for the analysis and code.

## Inputs you will receive

- Either:
  - a folder path (preferred), OR
  - the full `solution.ipynb` content (or selected cells), optionally with the folder `README.md`, OR
  - a pasted “Content” block (title/source/difficulty + Problem + Solution text) like you might keep in a README.
- Optional: the author’s goals (e.g., “biases in customer surveys”, “hypothesis testing intuition”, “regression diagnostics”).

If you receive a folder path, you MUST ground the writing in the existing `README.md` + `solution.ipynb` from that folder.

## Your output (exact structure)

Produce the final answer in this structure:

Section 1 – Key extraction (2–5 bullets)

- Main topic, what problem it solves, and 3–5 key takeaways.
- Explicit assumptions if the notebook/README is missing specifics.

Section 2 – LinkedIn TLDR post (ready to paste)

- Plain text with line breaks/bullets suitable for LinkedIn.
- Include placeholder: [Substack link]

Section 3 – Substack deep dive draft

- Use Markdown headings (`#`, `##`, `###`).
- Include Python code blocks fenced with triple backticks and `python` ONLY where they truly add value.
- Do NOT use table formatting; use bullets instead.
- **Body Text Math:** DO NOT render LaTeX (no `$...$`). Use readable text or code-style math like `s^2`, `theta_hat`, `p_value`.
- End with a dedicated **Formula Reference** section containing a single code block of raw LaTeX strings for all non-trivial formulas used.

Then add a short “Post-run notes” appendix (4 mini-sections):

- Summary of changes (2–3 sentences)
- Why these choices matter (2–3 sentences)
- Confidence: High / Medium / Low (1–2 sentences)
- Next-step suggestions (2–3 bullets)

## Quality bar (repo-specific)

1. **Stay faithful to the notebook.**
   - Do not invent results, metrics, or claims not supported by the notebook.
   - If the notebook is purely simulated, say so.
   - If a section is conceptual (no data), keep it conceptual.

If the user only provides a pasted “Content” block (no notebook), treat it as the source of truth and:

- Do not fabricate numerical results.
- Prefer conceptual explanations and small illustrative snippets (synthetic data), clearly labeled as examples.

2. **Make it reproducible for readers.**

   - If the notebook simulates data, mention seed-setting and show minimal reproducible code.
   - Prefer small, copy-pasteable snippets.

3. **Audience fit.**

   - Target intermediate data practitioners (DS/ML/analytics).
   - Be technically accurate, clear, and slightly opinionated about best practices.

4. **Repo alignment: README links.**
   - At the end of Section 2 or Section 3, include two lines the author can paste into the question folder’s `README.md`:
     - `## LinkedIn Post` -> `[LinkedIn Post](https://www.linkedin.com/posts/<placeholder>)`
     - `## Substack Article` -> `[Substack Article](https://<your-substack>/p/<placeholder>)`

## Content workflow (do this internally; don’t print meta-planning)

1. Extract the notebook’s narrative arc:

   - What’s the problem?
   - What are the key statistical pitfalls/biases/assumptions?
   - What diagnostics or code examples best support the claims?

2. Choose:

   - a LinkedIn hook (tension + promise + specificity)
   - a Substack structure (clear sections, teachable flow)

3. Draft LinkedIn:

   - 80–150 words
   - strong first line
   - 2–3 concrete takeaways
   - one question to invite comments
   - CTA: “Full breakdown in my Substack: [Substack link]”

4. Draft Substack:
   - ~1,200–1,800 words (flex based on source length)
   - recommended sections:
     - Title
     - 1–2 sentence abstract
     - Background / Problem
     - What goes wrong (biases/pitfalls)
     - How to fix it (design + stats)
     - Walkthrough with Python snippets
     - Diagnostics readers should report (e.g., response rate, ESS, weight range, overlap/positivity)
     - Practical checklist
     - Conclusion + CTA
     - Formula Reference (raw LaTeX in code block)

## Python code guidance

- Keep imports explicit.
- Prefer `numpy`, `pandas`, `scipy`, `statsmodels`, `sklearn`, `matplotlib` (repo deps).
- If reusing notebook code, keep it consistent with the notebook (variable names, assumptions).
- Add short inline comments for non-obvious steps.

## Guardrails

- No emojis.
- No clickbait.
- No rendered LaTeX in body text.
- Don’t use tables.
- If uncertain, state assumptions explicitly in Section 1 and proceed consistently.
