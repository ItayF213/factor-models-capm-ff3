# Factor Models: CAPM vs Fama–French Three-Factor Model

## Overview
This project provides an empirical comparison of the Capital Asset Pricing Model (CAPM) and the Fama–French Three-Factor (FF3) model using 25 size–value sorted portfolios. The goal is to evaluate how much additional explanatory power the FF3 model provides relative to CAPM and whether it reduces pricing errors (alphas) across portfolios.

The analysis is implemented in Python and follows a structured, research-style workflow suitable for academic and admissions review.

---

## Data
The project uses publicly available data from Kenneth French’s data library:

- **Fama–French Factors**  
  - Market excess return (Mkt−RF)  
  - Size factor (SMB)  
  - Value factor (HML)  
  - Risk-free rate (RF)

- **Test Assets**  
  - 25 value-weighted portfolios sorted by firm size and book-to-market ratio

All data are monthly and aligned on a common time index. Portfolio returns are converted to excess returns by subtracting the risk-free rate.

---

## Methodology
For each of the 25 portfolios, the following models are estimated using OLS regression:

### CAPM
\[
R_{i,t} - R_{f,t} = \alpha_i + \beta_{i}^{MKT}(MKT_t) + \varepsilon_{i,t}
\]

### Fama–French Three-Factor Model
\[
R_{i,t} - R_{f,t} = \alpha_i + \beta_{i}^{MKT}(MKT_t) + \beta_{i}^{SMB}(SMB_t) + \beta_{i}^{HML}(HML_t) + \varepsilon_{i,t}
\]

For each model and portfolio, the following statistics are computed:
- R² (explanatory power)
- Alpha (pricing error)
- Alpha p-value
- Factor loadings (betas)

---

## Empirical Results

### Model Fit
- **Average R² (CAPM):** ~0.74  
- **Average R² (FF3):** ~0.91  
- **Average increase in R² (FF3 − CAPM):** ~0.18  

The FF3 model consistently explains a substantially larger share of return variation across all portfolios.

### Pricing Errors (Alphas)
- **Significant alphas at 5% level:**
  - CAPM: 11 out of 25 portfolios
  - FF3: 6 out of 25 portfolios

Including size and value factors reduces the number and magnitude of statistically significant alphas, indicating improved pricing performance.

### Cross-Sectional Patterns
- Small and high book-to-market portfolios experience the largest improvement in explanatory power under FF3.
- SMB and HML factor loadings vary systematically across portfolios, consistent with their construction.

---

## Interpretation
The results support well-established empirical asset pricing evidence:

- CAPM alone is insufficient to fully explain returns across size–value portfolios.
- The Fama–French Three-Factor model substantially improves model fit and reduces pricing errors.
- Size and value factors capture systematic risk dimensions beyond the market factor.

Overall, the findings illustrate why multifactor models dominate single-factor approaches in empirical asset pricing.

---

## Repository Structure
- `01_factor_models_capm_ff.ipynb` — Main analysis notebook
- `README.md` — Project overview and results summary

---

## Tools & Libraries
- Python
- pandas
- numpy
- statsmodels
- matplotlib

---
