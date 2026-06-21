# Olympic EDA

Exploratory data analysis of 120 years of Olympic Games data, with hypothesis testing (t-tests, chi-square) to check whether visual patterns in medals, body size, and host-country advantage actually hold up statistically.

## About

This project analyzes the [120 Years of Olympic History](https://www.kaggle.com/datasets/heesoo37/120-years-of-olympic-history-athletes-and-results) dataset (~70,000 athlete-event records, 1896–2016) using pandas, Seaborn, and SciPy.

A basic EDA pass usually stops at "here's a chart." This goes a step further and asks whether the patterns in those charts are actually statistically meaningful, or just noise:

- Do medalists genuinely differ in age, height, or weight from non-medalists?
- Is there a measurable host-country advantage?
- Is medal outcome related to sex, and how strongly?
- How has the average athlete's body changed across a century of competition?

## What's in here

- **Data cleaning** — duplicate removal, missing-value handling via sport-and-sex grouped median imputation (instead of one global average), and IQR-based outlier checks
- **Hypothesis testing** — independent t-tests (medalist vs. non-medalist), chi-square (sex vs. medal outcome), Pearson correlation (height vs. weight), and a 95% confidence interval on mean age
- **Trend analysis** — decade-level changes in age, height, weight, and participation; gender participation share over time
- **Host-country advantage** — medal rate when competing at home vs. away, tested for significance
- **Visualizations** — distribution plots, a fixed (readable) top-15-country medal heatmap, violin/box plots by medal and season, and a sampled height-vs-weight scatter
- **Findings summary** — built dynamically from the actual test results at the end of the run, not a fixed write-up

## Findings

On the full dataset, the analysis found:

- Medalists are significantly taller, heavier, and slightly older than non-medalists (p < 0.0001 for all three), though the effect is much stronger for height/weight than age — likely reflecting which sports produce medals rather than medals changing physical traits
- Athletes hosting the Olympics had a 22.7% medal rate vs. 13.2% otherwise — a large, statistically significant home advantage (p < 0.0001)
- Height and weight are strongly correlated (r = 0.78)
- Sex shows a weak but technically significant association with medal outcome (p = 0.04)
