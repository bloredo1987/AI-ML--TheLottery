# AL-ML-- The Lottery

## Basic ML: Apply Basic Constraints, Ranges, Historical Combinations
In this project, I approach lottery prediction as a constrained, data‑driven sampling problem. I treat each ball position (B1–B5 and P1) as an independent variable with its own historical behavior. By analyzing positional ranges, frequency distributions, and statistical patterns, I create a structured framework that keeps predictions realistic, statistically grounded, and free from patterns that have already occurred.

Key Constraints I Use
- Position‑specific ranges:  
I define realistic ranges for each ball position based on historical draws. This prevents sampling outside the domain of valid values and keeps each position aligned with its historical behavior.
Key concept: positional analysis
- Historical pattern analysis:  
I calculate the min, max, and mean for each ball position to understand its distribution and validate the ranges I set.
Key concept: feature constraints
- Weighted sampling by historical frequency:  
Instead of sampling uniformly, I weight each number by how often it has appeared historically. This gives more probability mass to numbers that have historically been more common.
Key concept: weighted sampling
- Exclusion of historical combinations:  
I remove any combination that has already occurred. This ensures that every prediction is new and not a repeat of a past draw.
Key concept: set lookup
- Sequential pattern filtering:  
I exclude combinations where the five main balls form a perfect sequence, since these patterns are statistically rare and not useful for prediction.
Key concept: pattern detection
- Independent positional modeling:  
Each ball position has its own sampler, range, and distribution. This mirrors how analysts treat independent variables in a dataset and avoids assuming all numbers behave the same.

- First Attempt
- Second Attempt
- Third Attempt
- Machine Learning Clustering
