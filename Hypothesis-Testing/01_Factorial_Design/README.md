# Factorial Design

**Source:** Uncountable  
**Difficulty:** Hard

## Problem Statement

You are working with a customer called **Rubber Experts** (Detroit, MI). They want to formulate a new rubber product that is **stronger** than previous compounds.

They are experimenting with **two polymers** (main components of rubber) and **two additives** (believed to improve strength). They have already run 5 experiments (mixture weight percentages sum to 100) and measured strength (higher is better):

| Experiment | Polymer 1 | Polymer 2 | Additive 1 | Additive 2 | Strength |
| --- | --- | --- | --- | --- | --- |
| 1 | 90 | 0 | 10 | 0 | 16.5 |
| 2 | 0 | 90 | 10 | 0 | 8.6 |
| 3 | 45 | 45 | 0 | 10 | 12.6 |
| 4 | 60 | 30 | 5 | 5 | 18.9 |
| 5 | 30 | 60 | 5 | 5 | 9.8 |

As an Uncountable data scientist, advise Rubber Experts on what to do next:

- How many additional experiments should they run?
- Which ingredients should they use in their next experiments?
- What specific experiments (exact mixtures) do you recommend?

## Approach

- Treat this as a **designed experiment under a mixture constraint** (ingredients sum to 100%), where interactions and curvature are plausible.
- Start with quick EDA to look for structure (polymer balance, total additive level, and additive split) and to identify the current best region (Experiment 4).
- Fit a **baseline mixture regression** (linear mixture model) to get directional guidance; then plan additional runs to support a **quadratic mixture model** (to capture interactions).
- Choose new experiments to be **informative**, not just “close to the best”: add points that improve parameter identifiability (space-filling / D-optimal augmentation) plus **replicates** to estimate measurement noise.
- Recommend a small batch of next experiments (typically ~6–10):
  - 2–3 replicates (including the current best and a center-ish point)
  - several new mixtures covering low/high additive totals and varying polymer ratio and additive split
- After collecting the next batch, refit the model, check residuals/assumptions, and iterate with a second batch only if needed.

## Solution

See `solution.ipynb` for the Python implementation, simulation, or proof.

## Resources

- [NIST/SEMATECH e-Handbook of Statistical Methods (DOE overview)](https://www.itl.nist.gov/div898/handbook/)
- [NIST e-Handbook: Response Surface Methods](https://www.itl.nist.gov/div898/handbook/pri/section5/pri5.htm)
- [Mixture experiments (intro + Scheffé models)](https://en.wikipedia.org/wiki/Mixture_experiment)
- [Response surface methodology (includes CCD and Box-Behnken overviews)](https://en.wikipedia.org/wiki/Response_surface_methodology)
- [statsmodels OLS documentation](https://www.statsmodels.org/stable/regression.html)

## LinkedIn Post

<!-- Link to LinkedIn post explaining this concept -->
<!-- Example: [LinkedIn Post](https://www.linkedin.com/posts/your-post-url) -->

## Substack Article

<!-- Link to Substack article with detailed explanation -->
<!-- Example: [Substack Article](https://your-substack.com/p/article-title) -->
