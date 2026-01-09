# Stop Forcing the Mean: A Practical Guide to Confidence Intervals for the Median

**Source:** Google  
**Difficulty:** Medium

## Problem Statement

How would you compute a confidence interval (e.g., 95%) for the **median**—especially when the data are skewed or heavy-tailed and classic mean-based formulas don’t apply cleanly?

## Approach

- Use **bootstrap resampling** to avoid fragile parametric assumptions.
- Re-sample the data **with replacement** to create many bootstrap datasets of size $n$.
- Compute the **median** for each bootstrap dataset to form an empirical sampling distribution.
- Take the desired **percentiles** of the bootstrap medians (e.g., 2.5th and 97.5th) as the CI bounds.
- Report diagnostics (sample size, observed median, CI level, bootstrap iterations) and sanity-check the interval.

## Solution

See `solution.ipynb` for a runnable, step-by-step explanation and Python demonstration.

## Resources

- [Bootstrapping (Wikipedia)](https://en.wikipedia.org/wiki/Bootstrapping_(statistics))
- [Efron (1979): Bootstrap methods (original paper)](https://projecteuclid.org/journals/annals-of-statistics/volume-7/issue-1/Bootstrap-Methods--Another-Look-at-the-Jackknife/10.1214/aos/1176344552.full)
- [Efron & Tibshirani: *An Introduction to the Bootstrap*](https://www.taylorfrancis.com/books/mono/10.1201/9780203052888/introduction-bootstrap-bradley-efron-robert-tibshirani)
- [`numpy.percentile` documentation](https://numpy.org/doc/stable/reference/generated/numpy.percentile.html)
- [`scipy.stats.bootstrap` documentation](https://docs.scipy.org/doc/scipy/reference/generated/scipy.stats.bootstrap.html)

## LinkedIn Post

TBD

## Substack Article

TBD
