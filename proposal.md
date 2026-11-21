# Deliverable 2: Analysis and Pitch

**Topic 7: Software Engineering Trends — Jose, Alif, and Sedan**

We analyze `engineering_trends.csv` (30,903 respondents; 212 variables) to inform CIS career advice. Compensation is `ConvertedCompYearly`, in USD.

## Guided results

**Investigation 1 — Jose.** Respondents with positive compensation and a reported work setting showed:

| Setting | n | Mean (USD) | Median (USD) | Sample variance (USD²) |
|---|---:|---:|---:|---:|
| Remote | 4,606 | 114,563.07 | 93,098.00 | 2.5252 × 10¹⁰ |
| Hybrid | 4,806 | 103,950.39 | 80,705.50 | 1.9809 × 10¹¹ |
| In-person | 1,817 | 93,418.62 | 53,206.00 | 2.5107 × 10¹¹ |

Large spreads make averages unreliable personal forecasts. Across 13,373 complete experience–salary pairs, covariance was 322,971.46 USD·years and Pearson's r was 0.0668. Correlations were 0.1621 for remote and 0.0333 for in-person respondents; both were weak.

**Investigation 2 — Alif.** Among working developers, Rust/Go respondents (n = 2,133) averaged $122,043.29 versus $107,568.77 for Python/Java respondents without Rust/Go (n = 3,307). Overlapping language users entered only Rust/Go. H0 assumed exchangeable salaries across labels; H1 predicted a higher Rust/Go mean. A one-sided, 10,000-shuffle test gave **p = 0.18508**: fail to reject H0 at 0.05. Excluding 55 salaries above the pooled 99th percentile gave sensitivity p ≈ 0.00010. Conclusions depend on extreme-salary handling; neither result establishes that learning a language causes a raise. These guided investigations use different eligible samples.

## Original questions and plan

Use employed/self-employed respondents coding as their primary job. Restrict `Country` to the United States; require positive finite compensation and valid `WorkExp`. Exclude missing answers separately for each question.

1. **Education:** Within 0–5 years of experience, is median compensation higher for master's than bachelor's respondents? Compare these `Education` categories (70 versus 226 eligible respondents). This informs graduate-study discussions; the survey cannot measure tuition costs or a degree's financial return.

2. **Career responsibilities:** Within more than 5 and at most 15 years of experience, is median compensation higher for combined people-manager/individual-contributor roles than senior/staff individual contributors? Compare these `ICorPM` categories (106 versus 431 respondents) to examine two career paths.

For each, report counts, means, medians, interquartile ranges, and box plots. Test the directional median difference with 10,000 label shuffles, seed 42, and a corrected upper-tail p-value. Use 0.025 per primary test for two comparisons. Retain all eligible salaries; report a pooled-top-1% sensitivity check separately. These proposed questions await final analysis and team review. Missing responses, self-reporting, and remaining job differences limit conclusions to associations.

## Reproducibility and contributions

Run `analysis.ipynb` with the CSV beside it and pandas, NumPy, Seaborn, Matplotlib, and ipykernel installed. All 21 code cells ran without saved errors.

**Jose:** cleaning and Investigation 1. **Alif:** Investigation 2, proposed questions, and report draft. **Sedan:** Deliverable 1 cohort definition and bias notes reused here.
