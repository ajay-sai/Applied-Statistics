# Correlation of X+3 and Y

**Source:** Goldman Sachs  
**Difficulty:** Medium

## Problem Statement

The correlation between random variables $X$ and $Y$ is $\rho$.

What is the correlation between $X + 3$ and $Y$?

## Approach

- Use the definition $\mathrm{corr}(A,B)=\dfrac{\mathrm{cov}(A,B)}{\sigma_A\sigma_B}$.
- Show that adding a constant does **not** change covariance: $\mathrm{cov}(X+3, Y)=\mathrm{cov}(X,Y)$.
- Show that adding a constant does **not** change variance/standard deviation: $\sigma_{X+3}=\sigma_X$.
- Conclude $\mathrm{corr}(X+3, Y)=\mathrm{corr}(X,Y)=\rho$.
- (Optional) Verify with a quick simulation.

## Solution

See the notebook: [`solution.ipynb`](solution.ipynb).

## Resources

- [Wikipedia: Correlation and dependence](https://en.wikipedia.org/wiki/Correlation_and_dependence)
- [Wikipedia: Covariance](https://en.wikipedia.org/wiki/Covariance)
- [Khan Academy: Covariance and correlation intuition](https://www.khanacademy.org/math/statistics-probability/describing-relationships-quantitative-data)
- [Stats.SE: Effect of linear transformations on correlation](https://stats.stackexchange.com/questions/3730)

## LinkedIn Post

[LinkedIn Post](TODO)

## Substack Article

[Substack Article](TODO)
