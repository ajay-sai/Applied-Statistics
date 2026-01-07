# Unbiased Estimation of Variance

**Source:** Google  
**Difficulty:** Medium

## Problem Statement
Prove that the sample variance formula is an unbiased estimation of the population variance.

## Approach
Main Topic: Mathematical proof that the sample variance formula (with denominator n-1) is an unbiased estimator of the population variance.

Key Takeaways:
1) An estimator is unbiased when its expected value equals the true population parameter: E[sample statistic] = population parameter
2) The proof leverages expectation operator rules (linearity, extracting constants) and substitutes established variance formulas
3) The critical result shows that dividing by (n-1) instead of n corrects for the bias introduced by using the sample mean rather than the population mean
4) The (n-1) denominator (Bessel's correction) ensures the sample variance is an unbiased estimator, while dividing by n would underestimate the true variance
5) This foundational result underpins why statistical software and formulas use (n-1) for sample variance calculations

## Solution
See `solution.ipynb` for the Python implementation, simulation, or proof.

## Resources
- [Unbiased Estimation of Variance - Wikipedia](https://en.wikipedia.org/wiki/Unbiased_estimation_of_variance)
- [Variance - Wikipedia](https://en.wikipedia.org/wiki/Variance)

## LinkedIn Post
https://www.linkedin.com/posts/ajay-sai_why-sample-variance-divides-by-n-1-a-complete-share-7414434107339751424-4ekj?utm_source=share&utm_medium=member_desktop&rcm=ACoAAB9gB1kB6Qhuvd4HLYfBYH93lOEoOdaZeJ0

## Substack Article
https://open.substack.com/pub/ajaymiryala/p/why-sample-variance-divides-by-n?utm_campaign=post-expanded-share&utm_medium=web