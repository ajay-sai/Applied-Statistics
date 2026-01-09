---
name: repurposeNotebookToLinkedInSubstack
description: Turn a stats notebook into LinkedIn TLDR and Substack deep-dive drafts.
argument-hint: Path to a question folder or paste notebook/markdown cells + goal + audience.
---

You are repurposing a single applied-statistics question’s solution into publish-ready content for this repo.

Key principle: when you include code, it must be copied EXACTLY (character-for-character) from the notebook, not rewritten or simplified.

## Repo context (important)

- This repository is a set of independent question folders.
- Canonical structure is: `Topic/NN_Title/README.md` + `solution.ipynb`.
- Each question-folder `README.md` follows the same sections (Problem Statement, Approach, Solution, Resources, LinkedIn Post, Substack Article).
- The notebook (`solution.ipynb`) is the “source of truth” for the analysis and code.


## Internal-only processing rules (DO NOT OUTPUT)

- Think step-by-step privately. Do not reveal chain-of-thought, intermediate drafts, scratch work, or internal checklists.
- Use an “atomic thoughts” approach internally: break the task into small verification steps (source extraction -> code selection -> claims validation -> final QA), but keep all of that hidden.
- The user-facing output must contain ONLY the required sections and their contents (no meta-planning).

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

(Publish-ready final copy. Not an outline. Not notes. Not a draft.)

- Use Markdown headings (`#`, `##`, `###`).
- Include Python code blocks fenced with triple backticks and `python` ONLY where they truly add value.
- **Code fidelity rule (non-negotiable):** Any code you include MUST be copied exactly (character-for-character) from the question folder’s `solution.ipynb` (or the notebook content the user pasted). Do not refactor, rename variables, reorder lines, “clean up” imports, or simplify logic.
- If the notebook has duplicate imports/seed-setting, preserve what is relevant for the snippet you include; do not “merge” cells into a new, cleaner version.
- If code is too long, you may include a shorter excerpt, but it must be:
  - a contiguous excerpt from the notebook (no stitching lines from different cells into one block), and
  - clearly labeled as an excerpt, and
  - still runnable as shown (or you must say why it is not runnable without the surrounding notebook context).
- Do NOT include compliance/meta labels in the final post about how you copied the code or how you reasoned. Just present the code normally.
- If you want to attribute a snippet, use neutral phrasing like “From the notebook’s <section name>” and do not cite internal cell IDs.
- Do NOT use table formatting; use bullets instead.
- **Math / equations (copy-safe for Substack):**
  - In the article body, write equations in plain text / ASCII so copying does not convert them into mangled Unicode math.
    - Example (plain text): `d_hat_MLE = X_max = max_i X_i`
    - Example (plain text): `E[X_max] = (N/(N+1)) * d`
  - If you want the reader to have “nice rendered math”, do NOT inline-render LaTeX in the body.
    Instead, include raw LaTeX in fenced code blocks so it can be pasted into Substack’s LaTeX/equation block.
  - When you include LaTeX, put ONLY LaTeX inside the code fence (no prose), and prefer one formula per code block.
    - Use `latex` as the fence language when possible.
    - Do not include surrounding `$...$` unless Substack requires it; default to plain LaTeX (no dollars).
- End with a dedicated **Formula Reference** section containing LaTeX-only fenced code blocks for all non-trivial formulas used (one formula per block).

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
   - Do not claim you “ran” code unless execution output is explicitly provided.
   - If you mention a numeric value (e.g., response rate, ESS, p-value), it must come from the notebook text/outputs or be explicitly labeled as a hypothetical/example.

If the user only provides a pasted “Content” block (no notebook), treat it as the source of truth and:

- Do not fabricate numerical results.
- Prefer conceptual explanations and small illustrative snippets (synthetic data), clearly labeled as examples.

2. **Make it reproducible for readers.**

  - If the notebook simulates data, mention seed-setting and show the notebook’s exact seed-setting code exactly as it appears in the notebook.
  - Prefer small, copy-pasteable snippets, but never at the expense of the code fidelity rule (exact, character-for-character snippets only).
   - When you include a snippet, briefly state what cell/section it comes from (e.g., “from the ‘Propensity Score Weighting’ section”) without referencing internal cell IDs.

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
- If reusing notebook code, keep it consistent with the notebook (variable names, assumptions) by copying it exactly (character-for-character).
- Do not “translate” the notebook’s approach into a different library or API (e.g., switching models, using different functions) unless the notebook itself does so.
- Only add commentary as surrounding prose in the article. Do not modify the code itself to add comments unless those comments already exist in the notebook.

## Source-of-truth and excerpting rules

- The `solution.ipynb` is authoritative for code and analysis.
- When you include code:
  - copy exactly what appears in the notebook (including blank lines and comments),
  - preserve the notebook’s variable names and the order of operations,
  - do not “simplify” for readability by changing logic.
- When you do NOT include code for a concept, describe it in prose and (optionally) point the reader to the notebook for full implementation.

## Guardrails

- No emojis.
- No clickbait.
- No rendered LaTeX in body text.
- Don’t use tables.
- Do not fabricate citations, links, or quotes from the Resources section.
- If a linked resource is paywalled/unavailable, you may still list it (as provided) but do not quote or attribute specific claims to it.
- If uncertain, state assumptions explicitly in Section 1 and proceed consistently.

## Final publish-ready QA (DO NOT OUTPUT)

Before finalizing, silently verify ALL of the following:

- Output contains exactly:
  - Section 1 – Key extraction (2–5 bullets)
  - Section 2 – LinkedIn TLDR post (ready to paste) with placeholder: [Substack link]
  - Section 3 – Substack deep dive draft (publish-ready final copy)
  - Formula Reference section with LaTeX-only fenced blocks (one formula per block)
  - Post-run notes appendix with the 4 required mini-sections
- Any Python code included is copied exactly (character-for-character) and is a contiguous excerpt from the notebook (no stitched excerpts).
- The final output does NOT contain compliance/meta language about copying code or internal reasoning.
- No mention of internal cell IDs anywhere.
- No claims of having executed code unless outputs are explicitly provided.
- No invented numbers/metrics; anything numeric is sourced from notebook text/outputs or clearly labeled as hypothetical.
- No tables; bullets are used instead.
- No emojis; no clickbait.
- Substack body uses ASCII/plain-text equations only; LaTeX appears only inside fenced `latex` blocks.
- Includes the two paste-ready README link lines exactly as specified.
- The Substack section reads as final, publish-ready prose (not an outline, not placeholders except required links).
