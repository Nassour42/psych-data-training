# Psychological Data Analysis

Exploratory data analysis of large open-access psychological datasets, built as a self-directed Python learning portfolio. Projects focus on personality psychology and mental health, using real-world data to replicate and extend findings from the peer-reviewed literature.

**Stack:** Python 3 · pandas · numpy · matplotlib · seaborn · scipy · statsmodels · sklearn

---

## Project 1: DASS-42 Mental Health Analysis

**Dataset:** openpsychometrics.org via Kaggle · N = 33,562 (after cleaning) · collected 2017-2019

Analysis of depression, anxiety, and stress scores (DASS-42, Lovibond & Lovibond, 1995) across demographic and personality variables in a large international online sample.

**Cleaning:** 6,213 rows removed (15.6% of 39,775):
- Invalid demographic codes (gender, education, urban, handedness, religion, voted, marital status, English nativity)
- Implausible age (> 90) · completion time < 120 s · implausible family size (0 or > 15) · invalid TIPI responses

**Analyses:**
- Descriptive statistics and demographic visualisations
- One-way ANOVAs + Tukey HSD across gender, region, education, religion, marital status, orientation. Independent samples t-test for voted
- Two-way ANOVAs with interaction terms (gender × region, marital status × religion, etc.)
- Big Five × DASS-42 correlation heatmaps by region (TIPI, Gosling et al., 2003)
- Sensitivity analysis: attentive vs. full sample
- Logistic regression predicting severe depression (AUC = 0.778)

**Key findings:** Emotional stability was the strongest personality predictor of all three DASS subscales (negatively associated with severe depression). Gender and marital status showed significant main effects across all three DASS subscales.

---

## Project 2: IPIP-300 Personality Analysis

**Dataset:** openpsychometrics.org · N = 107,335 (after cleaning) · collected 2001–2011  
**Scoring:** IPIP-NEO-300 via Five-Factor-E (Johnson, 2014) pre-computed; scores are percentile-normed (1-100)

Analysis of Big Five personality structure, age trajectories, sex differences, and latent personality profiles in a large cross-sectional sample. Examined at both domain (5) and facet level (30).

**Cleaning:** 38,053 rows removed from 145,388: age outside 18–70 first (28,185 rows), then countries below n=500 threshold (9,868 rows from remaining sample)

**Analyses:**
- Descriptive statistics and Big Five score distributions
- Age × personality trajectories across decade bins (18-30 → 61-70) at domain + facet level
- Sex differences via t-tests and Cohen's d at domain + facet level
- Pearson correlation matrices (5×5 domain, 30×30 facet)
- K-means clustering (k=4, elbow method) to identify latent personality profiles
- Demographic breakdown by cluster

**Key findings:** Conscientiousness increased and neuroticism decreased with age, replicating the maturity principle (Roberts et al., 2006). Sex differences were small across all domains (all |d| < 0.2). Four personality profiles emerged from k-means clustering, distinguished by their Big Five signatures (e.g. high conscientiousness + low neuroticism vs. high neuroticism + low extraversion).

**Codebook:** [DASS-42](DASS-42%20codebook.txt) · [IPIP-300](https://github.com/NeuroQuestAi/ipip-neo-data) · [IPIP-300 OSF](https://osf.io/tbmh5/)
