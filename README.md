# Residual Sugar, Density and Quality in Red Wine

Hypothesis testing in R on the UCI red wine dataset (1,599 wines). The question:
does residual sugar relate to a wine's density, and does it relate to whether
the wine is rated excellent?

## What's in the analysis

| Part | Question | Method | Result |
|---|---|---|---|
| 1 | Is mean density different above vs. below median residual sugar? | Welch two sample t test | t ≈ -14.70, p < 0.001. Higher sugar wines are denser. |
| 2 | Does mean density differ across the four sugar quartiles? | One way ANOVA | Reject H0. Density rises steadily from Q1 to Q4. |
| 3 | Is sugar quartile associated with an "excellent" rating (quality 7 or higher)? | Chi square test of independence, checked with a 2,000 run permutation test | p ≈ 0.14 for both. No significant association. |

Takeaway: residual sugar is strongly tied to density but tells you little about
whether a wine will score well.

## Run it

Requires R. Open `wine_density_analysis.Rmd` in RStudio and click Knit, or:

```r
rmarkdown::render("wine_density_analysis.Rmd")
```

The dataset is downloaded into `data/` on first run.

## Data

Cortez, P., Cerdeira, A., Almeida, F., Matos, T. and Reis, J. (2009). Wine
Quality. UCI Machine Learning Repository. https://doi.org/10.24432/C56S3T
(CC BY 4.0)

## Tools

R, base stats (`t.test`, `aov`, `chisq.test`), R Markdown
