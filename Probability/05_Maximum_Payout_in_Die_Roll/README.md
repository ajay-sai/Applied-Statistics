# Maximum Payout in Die Roll

**Source:** Meta  
**Difficulty:** Medium

## Problem Statement

You can roll a fair 6-sided die at most three times. You will be paid $X$, where $X$ is the highest roll you obtain.

You may choose to stop rolling early if you roll a 6 (since no later roll can improve the maximum).

What is the expected payout $\mathbb{E}[X]$?

## Approach

- Let $M$ be the maximum of the rolls observed (up to 3 rolls, stopping early if a 6 appears).
- Note that “stopping on 6” does **not** change the distribution of $M$ (once a 6 appears, the maximum is already 6).
- Use the CDF method for maxima: for $m \in \{1,\dots,6\}$, $\Pr(M \le m) = (m/6)^3$.
- Convert CDF to PMF via differences: $\Pr(M=m) = \Pr(M \le m) - \Pr(M \le m-1)$.
- Equivalent combinatorial check: $\#\{M=m\} = m^3-(m-1)^3$ out of $6^3$ equally likely length-3 sequences.
- Compute the expectation $\mathbb{E}[M] = \sum_{m=1}^6 m\,\Pr(M=m)$ and optionally verify via simulation.

## Solution

See `solution.ipynb` for the Python implementation, simulation, or proof.

## Resources

- [Expected value (Wikipedia)](https://en.wikipedia.org/wiki/Expected_value)
- [Order statistic / maximum (Wikipedia)](https://en.wikipedia.org/wiki/Order_statistic)
- [Discrete random variables and expected value (Khan Academy)](https://www.khanacademy.org/math/statistics-probability/random-variables-stats-library)
- [Cumulative distribution function (Wikipedia)](https://en.wikipedia.org/wiki/Cumulative_distribution_function)

## LinkedIn Post
<!-- Link to LinkedIn post explaining this concept -->
<!-- Example: [LinkedIn Post](https://www.linkedin.com/posts/your-post-url) -->

## Substack Article
<!-- Link to Substack article with detailed explanation -->
<!-- Example: [Substack Article](https://your-substack.com/p/article-title) -->
