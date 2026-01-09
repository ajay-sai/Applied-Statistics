# Number of Trials to Detect Biased Coin

**Source:** General  
**Difficulty:** Hard

## Problem Statement

You suspect a coin is biased and want to detect that bias with a hypothesis test.

Assume the null hypothesis is a fair coin $H_0: p = 0.5$. If the true probability of heads were $p = 0.6$, how many flips $n$ would you need so that a **one-sample z-test for a proportion** would (approximately) reject $H_0$ at significance level $\alpha = 0.05$? (You can expect an answer in the high double-digits, often rounded to “about 100”.)

## Approach

- Set up hypotheses $H_0: p = 0.5$ and $H_1: p \neq 0.5$ (two-sided test).
- Use the one-sample proportion z-statistic: $z = \dfrac{\hat p - p_0}{\sqrt{p_0(1-p_0)/n}}$.
- Use the critical value $z_{1-\alpha/2}$ (for $\alpha=0.05$, $\approx 1.96$).
- Approximate the required sample size by setting the expected z-score under $p=0.6$ equal to the critical value.
- Solve for $n$ and round up to the nearest whole flip.
- (Optional) Verify with a quick Monte Carlo simulation and/or an exact binomial test.

## Solution

See `solution.ipynb` for the full derivation and a small simulation check.

## Resources

- [NIST/SEMATECH e-Handbook (Hypothesis Tests)](https://www.itl.nist.gov/div898/handbook/)
- [Wikipedia: Test of proportions](https://en.wikipedia.org/wiki/Test_of_proportions)
- [SciPy: `scipy.stats.binomtest`](https://docs.scipy.org/doc/scipy/reference/generated/scipy.stats.binomtest.html)
- [Statsmodels: `proportions_ztest`](https://www.statsmodels.org/stable/generated/statsmodels.stats.proportion.proportions_ztest.html)

## LinkedIn Post

[LinkedIn Post](https://www.linkedin.com/)  

## Substack Article

[Substack Article](https://substack.com/)
