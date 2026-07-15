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

## First Attempt (Apply Basic Constraints/Ranges/Historical Data)
This first attempt eads historical lottery results, analyzes number ranges and averages, builds weighted samplers that favor numbers that appeared more often in the past, and then generates new combinations that avoid sequential patterns and avoid any combination that has already occurred historically.

This script is a weighted random lottery predictor.
It tries to generate “future‑looking” combinations by:
- favoring historically common numbers
- avoiding unrealistic patterns
- avoiding exact repeats of past draws
- forced ascending after (after sorting)

It does not guarantee accuracy (lottery numbers are random), but it does produce combinations that are statistically shaped by past data.

## Second Attempt (Clustering/K-Means/Probability Modeling)
This attempt uses clustering and fitted normal distributions to generate numbers that resemble historical patterns, instead of simple random ranges or weighted frequencies.

- cleans the dataset
- clusters historical draws using K‑Means
- fits a normal distribution to each ball position
- samples new numbers from those fitted distributions
- clamps them to realistic ranges
- rejects historical repeats and sequential patterns

## Third Attempt (Machine Learning Clustering)
This version is the most complex, most “statistically engineered,” and most restrictive of all your scripts. It doesn’t just generate combinations — it scores them using probability density, filters them by likelihood, and returns only the statistically strongest candidates.

- Fits normal distributions to each ball
- Generates combinations using those distributions
- Computes a joint likelihood score for each combination
- Filters out combinations with likelihood < 50%
- Removes historical repeats and sequential patterns
- Builds a DataFrame of only “high‑likelihood” combos
- Lets you search for specific combinations

This is the first version that quantifies probability and scores each generated draw. It evaluates how “probable” a combination is under your statistical model, with a likeihood threshold >=50%.

# HeatMap
This shows:
- Rows = numbers (1–69 for white balls, 1–26 for Powerball)
- Columns = ball positions (B1–B5, P1)
- Color intensity = how often that number appeared historically
You’ll instantly see:
- hot zones (frequent numbers)
- cold zones (rare numbers)
- positional biases (e.g., B1 tends to be lower numbers)

![alt text](image.png)

## Results/Findings