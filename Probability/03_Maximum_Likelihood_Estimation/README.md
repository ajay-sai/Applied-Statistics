# Maximum Likelihood Estimation

**Source:** Google  
**Difficulty:** Medium

## Problem Statement

How do you estimate the mean and variance using maximum likelihood estimation (MLE)?

## Approach

- Assume an i.i.d. sample and pick a parametric model (here: Normal with parameters $\mu$ and $\sigma^2$).
- Write the likelihood $L(\theta)=\prod_{i=1}^n f(x_i\mid\theta)$ and work with the log-likelihood $\ell(\theta)=\log L(\theta)$.
- For the Normal model, expand $\ell(\mu,\sigma^2)$.
- Differentiate w.r.t. $\mu$ and $\sigma^2$, set derivatives to zero, and solve.
- Verify the closed-form solution numerically (optional) and via simulation.

## Solution

See `solution.ipynb` for the derivation and Python verification.

## Resources

- [Maximum likelihood estimation (Wikipedia)](https://en.wikipedia.org/wiki/Maximum_likelihood_estimation)
- [Maximum likelihood (Statlect)](https://statlect.com/fundamentals-of-statistics/maximum-likelihood)
- [Maximum Likelihood Estimation (probabilitycourse.com)](https://www.probabilitycourse.com/chapter9/9_1_1_maximum_likelihood_estimation.php)
- [SciPy: `scipy.stats.norm`](https://docs.scipy.org/doc/scipy/reference/generated/scipy.stats.norm.html)
- [SciPy: optimization (`scipy.optimize`)](https://docs.scipy.org/doc/scipy/reference/optimize.html)

## LinkedIn Post

<!-- Link to LinkedIn post explaining this concept -->
<!-- Example: [LinkedIn Post](https://www.linkedin.com/posts/your-post-url) -->

## Substack Article

<!-- Link to Substack article with detailed explanation -->
<!-- Example: [Substack Article](https://your-substack.com/p/article-title) -->
