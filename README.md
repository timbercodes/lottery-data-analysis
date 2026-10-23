# Lottery Data Analysis: Probability & Fairness Evaluation 🎲📊

## 📌 Project Overview
An exploratory data analysis (EDA) and statistical evaluation of historical national lottery draws (1968–2026; the analysis covers the current game format only, from 2011-03-05, 1,744 draws). This project aims to verify the randomness of the draws, analyze number frequency distributions, and calculate real-world win probabilities using statistical hypothesis testing.

Rather than relying on "lucky numbers," this project applies Python-based data science techniques to evaluate whether the lottery mechanics align with expected mathematical models.

## 🎯 Goals
- **Data Cleaning & Preprocessing:** Format and standardize years of historical draw data for analysis.
- **Frequency Analysis:** Identify "hot" and "cold" numbers and evaluate if their variance falls within normal statistical limits.
- **Probability Modeling:** Calculate the expected value (EV) and mathematical odds of various winning tiers.
- **Hypothesis Testing:** Apply statistical tests (e.g., Chi-Square) to evaluate the fairness and true randomness of the system.

## 🛠️ Tech Stack
- **Language:** Python 3
- **Data Manipulation:** `pandas`, `numpy`
- **Statistical Analysis:** `scipy.stats`
- **Data Visualization:** `matplotlib`, `seaborn` (or `plotly` for interactive charts)
- **Environment:** Jupyter Notebook

## 🚀 Next Steps (Development Roadmap)
- [ ] Initialize repository and set up the virtual environment.
- [ ] Load and clean the 1968-2026 historical dataset (handle missing values, correct data types).
- [ ] Perform basic EDA (histograms, scatter plots of drawn numbers).
- [ ] Run statistical tests on number distributions.
- [ ] Document findings, create visualizations, and write the final conclusion.

## 🔬 Hypotheses & Analysis Plan
*Defined before running any tests, to avoid p-hacking.*

**Scope:** Israeli Lotto draws in the current format (6 numbers out of 37 + 1 strong number out of 7), from 2011-03-05 to 2026-10-20 (1,744 draws). Earlier draws are excluded because the game rules were different.

**Significance level:** α = 0.05. Where many tests are run at once (e.g. one per number), p-values are adjusted for multiple comparisons (Holm / Benjamini-Hochberg).

| # | Question | Null hypothesis (H0) | Method |
|---|----------|----------------------|--------|
| H1 | Are the 6 main numbers uniform? | Each of the 37 numbers is equally likely (6/37 per draw) | Chi-square goodness-of-fit + Monte Carlo simulation |
| H2 | Is the strong number uniform? | Each value 1–7 is equally likely | Chi-square goodness-of-fit |
| H3 | Are consecutive draws independent? | Overlap between two consecutive draws follows the hypergeometric distribution | Chi-square on overlap counts |
| H4 | Do "hot" numbers stay hot? | Number frequencies in one year do not correlate with the next year | Spearman correlation |
| H5 | Is a number "due" after a long absence? | Gaps between appearances follow a geometric distribution (p = 6/37) | Goodness-of-fit test on gaps |
| H6 | (Exploratory) Do draws with only "birthday numbers" (≤31) have more winners? | Mean number of winners is the same | Non-parametric test |

**Interpretation note:** failing to reject H0 does not prove the lottery is fair. It means no evidence of deviation was found at this sample size.

---
*Developed as a portfolio project focusing on applied statistics and Python data manipulation.*
