# Customer Satisfaction Survey

**Source:** General  
**Difficulty:** Medium

## Problem Statement

Your company decides to conduct a customer satisfaction survey by emailing its survey link to a random selection of 10,000 customers who made a purchase in the last 6 months and reside in New York City. The survey includes questions about customer service, product quality, and overall satisfaction. Based on the responses, the company plans to implement targeted improvements. What potential biases could impact the validity of the survey results, and how would you recommend addressing these biases?

## Approach

1) Three critical bias types threaten survey validity: sampling bias (NYC-only, recent purchasers), non-response bias (extreme experiences respond more), and seasonal bias (temporal variation in satisfaction)
2) Sampling bias stems from unrepresentative geographic and temporal constraints, missing valuable insights from inactive customers and other regions
3) Non-response bias mitigation requires both incentivization strategies and statistical correction via propensity score weighting
4) Seasonal bias requires longitudinal survey deployment across multiple time periods to capture year-round variation in customer sentiment
5) Broadening sampling criteria to include browsers (non-purchasers) and longer time windows provides more generalizable insights for business decisions

## Solution

See `solution.ipynb` for the Python implementation, simulation, or proof.

## Resources

- [Groves et al., *Survey Methodology* (coverage/nonresponse/measurement)](https://onlinelibrary.wiley.com/doi/book/10.1002/9781118490013)
- [Lohr, *Sampling: Design and Analysis* (sampling frames, stratification)](https://www.routledge.com/Sampling-Design-and-Analysis/Lohr/p/book/9780367574630)
- [Little & Rubin, *Statistical Analysis with Missing Data* (missingness assumptions)](https://onlinelibrary.wiley.com/doi/book/10.1002/9781119013563)
- [Inverse probability weighting (IPW) overview](https://en.wikipedia.org/wiki/Inverse_probability_weighting)
- [Forecasting: Principles and Practice (seasonality/time effects overview)](https://otexts.com/fpp3/)

## LinkedIn Post
<!-- Link to LinkedIn post explaining this concept -->
<!-- Example: [LinkedIn Post](https://www.linkedin.com/posts/your-post-url) -->

## Substack Article
<!-- Link to Substack article with detailed explanation -->
<!-- Example: [Substack Article](https://your-substack.com/p/article-title) -->
