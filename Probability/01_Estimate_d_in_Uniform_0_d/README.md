# Estimate d in Uniform(0, d)

**Source:** Google  
**Difficulty:** Hard

## Problem Statement

Given $N$ i.i.d. samples $X_1,\dots,X_N \sim \mathrm{Uniform}(0,d)$, estimate the unknown upper bound parameter $d$.

In particular, the naive estimator $\max_i X_i$ is biased downward (it is always $\le d$), so we want an estimator with a principled bias correction.

## Approach

- Use order statistics: derive the CDF/PDF of the sample maximum $X_{\max}=\max_i X_i$.
- Compute $\mathbb{E}[X_{\max}]$ and solve for $d$ in terms of $\mathbb{E}[X_{\max}]$.
- Replace the expectation with the observed maximum to obtain an unbiased estimator:
  $$\hat d=\frac{N+1}{N}X_{\max}.$$
- (Optional) Compare with other reasonable estimators (e.g., MLE $\hat d_{\text{MLE}}=X_{\max}$ and mean-based $\hat d=2\bar X$) via simulation.
- (Optional) Build a confidence interval for $d$ by inverting the known distribution of $X_{\max}$.

## Solution

See `solution.ipynb` for the Python implementation, simulation, or proof.

## Resources

- [Order statistic (Wikipedia)](https://en.wikipedia.org/wiki/Order_statistic)
- [Continuous uniform distribution (Wikipedia)](https://en.wikipedia.org/wiki/Continuous_uniform_distribution)
- [Maximum likelihood estimation (Wikipedia)](https://en.wikipedia.org/wiki/Maximum_likelihood_estimation)
- Casella & Berger, *Statistical Inference* (order statistics + unbiased estimation) (book reference)

## LinkedIn Post
<!-- Link to LinkedIn post explaining this concept -->
<!-- Example: [LinkedIn Post](https://www.linkedin.com/posts/your-post-url) -->

## Substack Article
<!-- Link to Substack article with detailed explanation -->
<!-- Example: [Substack Article](https://your-substack.com/p/article-title) -->
