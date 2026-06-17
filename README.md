# manish-s-toolkit
# Mahanlytics — User Guide

Mahanlytics is a browser-based statistical analysis toolkit. Everything runs client-side: load a dataset (or use the built-in sample), then explore, visualize, simulate, and test it directly in the sidebar sections.

## 1. Toolkit Features

**Core**
- **Data Explorer** — import a CSV (drag-and-drop or file picker) or load the built-in Boston Housing sample; view row/column counts, missing values, duplicates, and per-column type breakdown; clean the dataset and detect outliers (IQR method).
- **Descriptive Stats** — mean, median, mode, std dev, variance, skewness, kurtosis, quartiles, and range for every numeric column.
- **Visualizations** — build bar, line, scatter, histogram, or box plots from any two columns, plus a correlation heatmap across all numeric fields.

**Distributions**
- **Distributions** — simulate Normal, Poisson, Binomial, Exponential, Uniform, Student's t, or Chi-Square data with adjustable parameters and sample size; view the PDF/histogram and empirical CDF; fit a normal curve to your own data; compare distribution shapes side by side.
- **CLT & Z-Score** — demonstrate the Central Limit Theorem by repeatedly sampling from a chosen source distribution (or your own data) and watching the sampling distribution of the mean converge to normal; compute z-scores and visualize them against the standard normal curve with the empirical rule (68/95/99.7%).

**Testing**
- **Parametric Tests** — One-Sample t, Two-Sample (Welch) t, Paired t, One-Way ANOVA, Chi-Square, and z-Test, each with assumption checks, test statistics, p-values, and a supporting chart.
- **Non-Parametric Tests** — Mann-Whitney U, Wilcoxon Signed-Rank, Kruskal-Wallis, and Friedman, for when normality assumptions don't hold.

**Inference**
- **Normality Tests** — Jarque-Bera test with a Q-Q plot and a normal-fit chart showing empirical-rule coverage bands.
- **Correlation** — Pearson or Spearman correlation between two variables, with a scatter plot and regression line.

**Tools**
- **Confidence Intervals** — compute and compare 90/95/99% CIs for a variable's mean.
- **Test Recommender** — answer a few questions about your data (type, number of groups, independence, normality) and get a recommended test with the rationale, formula, and hypotheses; includes a full test-selection reference table.
- **Report Export** — generate a PDF or HTML report summarizing dataset overview, descriptive statistics, correlations, and automatic interpretations.

## 2. How to Use It

1. **Load data.** Click **Sample Data** to try the Boston Housing dataset, or click **Import CSV** / drag a file onto the Data Explorer panel.
2. **Check data quality.** Review the Column Overview and metrics (missing values, duplicates); click **Clean Dataset** if needed, and check the Outlier Detection panel.
3. **Explore.** Use Descriptive Stats for summary numbers and Visualizations to chart relationships.
4. **Pick an analysis.** Use the sidebar to jump to Distributions, CLT & Z-Score, Parametric/Non-Parametric Tests, Normality Tests, or Correlation. Each panel has a form on the left (choose variables/parameters) and a chart on the right — fill the form, click the action button (e.g. **Run Test**, **Simulate**, **Analyze**), and read the results box for the statistic, p-value, and verdict.
5. **Not sure which test to run?** Go to **Test Recommender**, answer the guided questions, and it will point you to the right test with the reasoning.
6. **Export.** When finished, go to **Report Export**, choose sections to include, and download a PDF or HTML report.

## 3. Example Analysis

**Goal:** Check whether `medv` (median home value) differs meaningfully from a hypothesized value, and explore its relationship with `rm` (rooms per dwelling).

1. Click **Sample Data** to load the Boston Housing dataset.
2. In **Descriptive Stats**, check `medv`'s mean, std dev, and skewness.
3. In **Normality Tests**, select `medv` and run the Jarque-Bera test — if it's non-normal, prefer a non-parametric test later.
4. In **Parametric Tests → One-Sample t**, select `medv`, set H₀: μ = 22, choose two-sided, and click **Run Test**. Read the t-statistic, p-value, and the histogram with the H₀ mean marked.
5. In **Correlation**, set Variable 1 = `rm`, Variable 2 = `medv`, method = Pearson, and click **Analyze** — the scatter plot with regression line shows the strength and direction of the relationship.
6. If `medv` turned out non-normal in step 3, repeat a comparable check using **Non-Parametric Tests → Mann-Whitney U** (e.g. splitting by a categorical variable) instead of the t-test.
7. Go to **Report Export**, keep all sections checked, and export an HTML report capturing the full analysis.
