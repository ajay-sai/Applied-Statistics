# Simpson's Paradox

**Source:** LinkedIn  
**Difficulty:** Easy

## Problem Statement

What is Simpson’s Paradox? Illustrate an example.

Use the following cost-per-click (CPC) example comparing the U.S. vs Japan:

### Aggregated (country level)

| Country | Clicks | Total Cost | CPC |
| --- | ---: | ---: | ---: |
| U.S. | 1,000 | $2,000 | $2 / click |
| Japan | 500 | $3,000 | $6 / click |

### Disaggregated (country × search term)

Search terms are {cat, dog}:

| Country | Search Term | Clicks | Total Cost | CPC |
| --- | --- | ---: | ---: | ---: |
| U.S. | Cat | 200 | $400 | $2.00 / click |
| U.S. | Dog | 800 | $1,600 | $2.00 / click |
| Japan | Cat | 300 | $2,700 | $9.00 / click |
| Japan | Dog | 200 | $300 | $1.50 / click |

Explain how the overall conclusion (Japan has higher CPC) can differ from conclusions within subgroups (by search term).

## Approach

- Define Simpson’s Paradox as a reversal (or masking) of a trend when aggregating over a confounding variable.
- Compute the aggregated CPC for each country.
- Compute CPC by country within each search term (cat vs dog).
- Show how different mixes of traffic across terms (different click weights) drive the reversal.
- Explain the “right” comparison depends on the causal/decision question (e.g., comparing like-for-like terms).
- Note practical implication for A/B testing: always inspect key segments before shipping a global rollout.

## Solution

See `solution.ipynb` for the worked example, calculations, and a visualization.

## Resources

- [Simpson's paradox (Wikipedia)](https://en.wikipedia.org/wiki/Simpson%27s_paradox)
- [Simpson’s paradox (Britannica)](https://www.britannica.com/science/Simpsons-paradox)
- [Blyth (1972): “On Simpson’s Paradox and the Sure-Thing Principle” (JSTOR)](https://www.jstor.org/stable/2681491)
- [Tu, Gunnell, Gilthorpe (2008): explanation + applications (ScienceDirect)](https://www.sciencedirect.com/science/article/pii/S0165027014002267)
- [Brady Neal: Causal Inference course notes](https://www.bradyneal.com/causal-inference-course)

## LinkedIn Post
<!-- Link: [LinkedIn Post](https://www.linkedin.com/posts/your-post-url) -->

## Substack Article
<!-- Link: [Substack Article](https://your-substack.com/p/article-title) -->
