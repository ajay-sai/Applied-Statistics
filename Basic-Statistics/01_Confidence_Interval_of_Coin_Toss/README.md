# Confidence Interval of Coin Toss

**Source:** Google  
**Difficulty:** Medium

## Problem Statement

How can you calculate a confidence interval for the proportion of heads in a series of coin tosses?

## Approach

- Compute the sample proportion: $\hat{p} = x / n$ (heads / total tosses).
- Choose a confidence level (e.g., 90%, 95%, 99%) and set $\alpha = 1 - \text{confidence}$.
- Find the critical value $z_{1-\alpha/2}$ from the standard normal distribution.
- Compute the standard error: $\mathrm{SE} = \sqrt{\hat{p}(1-\hat{p})/n}$.
- Compute the margin of error: $m = z_{1-\alpha/2} \cdot \mathrm{SE}$.
- Construct the interval: $(\hat{p}-m,\; \hat{p}+m)$.
- For small $n$ or when $\hat{p}$ is near 0 or 1, consider Wilson or exact (Clopper–Pearson) intervals.

## Solution

See `solution.ipynb` for the derivation, worked example, and Python implementation.

## Resources

- [Binomial proportion confidence interval (Wikipedia)](https://en.wikipedia.org/wiki/Binomial_proportion_confidence_interval)
- [Wilson score interval (Wikipedia)](https://en.wikipedia.org/wiki/Binomial_proportion_confidence_interval#Wilson_score_interval)
- [Clopper–Pearson interval (Wikipedia)](https://en.wikipedia.org/wiki/Binomial_proportion_confidence_interval#Clopper%E2%80%93Pearson_interval)
- [NIST/SEMATECH e-Handbook: Confidence Intervals](https://www.itl.nist.gov/div898/handbook/prc/section2/prc241.htm)

## LinkedIn Post

[LinkedIn post](https://www.linkedin.com/posts/ajay-sai_ajay-miryala-ajaymiryala-share-7414285065033015296-X5wu?utm_source=share&utm_medium=member_desktop&rcm=ACoAAB9gB1kB6Qhuvd4HLYfBYH93lOEoOdaZeJ0)

## Substack Article

[Substack note](https://substack.com/@ajaymiryala/note/c-195941285?r=bq63v&utm_source=notes-share-action&utm_medium=web)
