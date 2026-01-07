# Estimate Global Mean and Variance

**Source:** General  
**Difficulty:** Easy

## Problem Statement
Suppose you know the mean height and population size of every country. (A) How would you estimate the global mean height? (B) Now, suppose you know the standard deviation of height for every country. How would you estimate the global standard deviation of height?

## Approach
Main Topic: Population-weighted estimation of global statistics (mean and variance/standard deviation) from grouped country-level data.

Key Takeaways:

1) The naive approach of averaging country means and standard deviations ignores population size differences and produces biased estimates
2) Proper global mean estimation requires population-weighted averaging, where each country's contribution is proportional to its population size
3) Global variance estimation is more complex than simply weighting standard deviations—requires accounting for both within-country variance and between-country variance in means 
4) This is a fundamental problem in hierarchical/grouped data analysis, relevant to AB testing, stratified sampling, and distributed computing scenarios
5) Understanding weighted statistics is critical for DS interview questions and real-world aggregation problems (e.g., user metrics across regions, cohort analysis)

Assumptions Made:

1) The original formulas are standard weighted mean and variance calculations
2) The problem assumes we have complete, accurate country-level statistics
3) Standard deviations refer to population or sample standard deviations (consistency assumed)

## Solution
See `solution.ipynb` for the Python implementation, simulation, or proof.

## LinkedIn Post
<!-- Link to LinkedIn post explaining this concept -->
<!-- Example: [LinkedIn Post](https://www.linkedin.com/posts/your-post-url) -->

## Substack Article
<!-- Link to Substack article with detailed explanation -->
<!-- Example: [Substack Article](https://your-substack.com/p/article-title) -->
