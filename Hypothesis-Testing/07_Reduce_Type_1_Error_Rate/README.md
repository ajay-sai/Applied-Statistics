# Reduce Type 1 Error Rate

**Source:** Pinterest  
**Difficulty:** Easy

## Problem Statement

How do you reduce the type 1 error rate in a statistical test?

## Approach

- Recall that the **Type I error rate** is the probability of incorrectly rejecting a true null hypothesis.
- In most classical tests, the **significance level** $\alpha$ is *defined* as the Type I error rate (under the null and assuming test assumptions hold).
- Therefore, the direct way to reduce Type I error is to **lower $\alpha$** (e.g., from 0.05 to 0.01).
- Recognize the trade-off: lowering $\alpha$ typically **reduces power** (increases Type II error) unless you also increase sample size or effect size.
- If you run **multiple tests**, control the *family-wise* Type I error using procedures like **Bonferroni/Holm** (or control FDR if that is the goal).
- Avoid “alpha inflation” from repeated peeking/optional stopping by **pre-specifying** the analysis plan or using valid sequential methods.

## Solution

See `solution.ipynb` for the Python implementation, simulation, or proof.

## Resources

- [NIST/SEMATECH e-Handbook: Hypothesis Tests](https://www.itl.nist.gov/div898/handbook/prc/section2/prc22.htm)
- [NIST/SEMATECH e-Handbook: Multiple Testing](https://www.itl.nist.gov/div898/handbook/prc/section4/prc47.htm)
- [Type I and Type II errors (overview)](https://en.wikipedia.org/wiki/Type_I_and_type_II_errors)
- [Bonferroni correction](https://en.wikipedia.org/wiki/Bonferroni_correction)
- [Holm–Bonferroni method](https://en.wikipedia.org/wiki/Holm%E2%80%93Bonferroni_method)

## LinkedIn Post
<!-- Link to LinkedIn post explaining this concept -->
<!-- Example: [LinkedIn Post](https://www.linkedin.com/posts/your-post-url) -->

## Substack Article
<!-- Link to Substack article with detailed explanation -->
<!-- Example: [Substack Article](https://your-substack.com/p/article-title) -->
