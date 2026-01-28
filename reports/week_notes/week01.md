# Week 01 — EDA Foundations & Data Understanding

## Objective
Establish a clear conceptual and statistical understanding of the
workout, sleep, and recovery datasets before any modeling.

The focus is clarity, not prediction.

## Resources Used
- Practical Statistics for Data Scientists — Chapter 1
- Data Science from Scratch — Chapter 1
- IBM EDA
-Pandas documentation: data types


## What I Did
- Defined dataset granularity and units of observation
- Created a canonical data dictionary
- Initialized EDA notebook structure
- Inspected raw datasets without transformation

## Key Takeaways
- Different datasets operate at different time scales (sets vs days)
- Recovery scores are estimates, not ground truth
- Misinterpreting averages is a major risk in rehab contexts

## Risks Identified
- Overreacting to single-day changes
- Treating ordinal variables as continuous
- Ignoring variability

## Next Steps
- Compare mean vs median across key metrics
- Quantify variability as a stability signal

### Day 2 — Mean vs Median

- Identified metrics distorted by outliers
- Median better represents “typical” rehab behavior
- Mean is sensitive to missed days and extreme sessions

### Day 3 — Variability

- Consistency matters more than peaks in rehab
- In normal distributions: 1.5 * IQR rule to detect outliers is not a law, is a rule but provides 99% of data but IQR make no assumptions regarding the distribution
- Histogram with KDE is a good idea, but keep in mind KDE is density (proportion)
- Variance & MSE are the same just if bias is zero when calculating MSE
- MAD (Median Absolute Deviation from Median) is recommended to handle outliers
- Percentiles also used for outliers handling
- Coefficient of Variation (CV) = (std / mean) used to seek stability
