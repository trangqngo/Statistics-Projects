# Portfolio: Applied Statistical Learning & GLMs

A collection of final projects covering predictive machine learning and advanced generalized linear modeling, completed for **STAT 442** (Statistical Learning & Data Mining) and **STAT 458** (Generalized Linear Models).

---

## 🎵 1. Song Popularity Analysis (Spotify)
**Course:** STAT 442 (Statistical Learning & Data Mining)  
**Authors:** Christopher Chung, Trang Ngo  

### Objective & Dataset
Predict song popularity on Spotify using statistical models trained on a dataset of ~550k tracks spanning 1921–2020. Evaluated both **regression** (raw 0–100 score) and **classification** (above/below median popularity) across 15 song and artist attributes.

### Model Performance
| Model Type | Best Estimator | Top Performance Metrics | Primary Feature Importance Drivers |
| :--- | :--- | :--- | :--- |
| **Regression** | Random Forest | MSE: `102.98` | Release Year (38%), Artist Popularity (28%) |
| **Classification** | Random Forest | Accuracy: `81.91%` \| AUC: `0.906` | Release Year, Artist Popularity, High Danceability |

> **Key Takeaway & Challenges:** Random Forest outperformed linear models, neural networks, and stacked classifiers. However, overall predictive performance remained constrained by high intrinsic variance in track popularity and missing unobserved variables (e.g., lyrics).

---

## 🌧️ 2. Gamma Generalized Linear Models (Australian Rainfall)
**Course:** STAT 458 (Generalized Linear Models)  
**Authors:** Samuel Liu, Trang Ngo  

### Objective & Case Study
Explored the mathematical foundations of Gamma GLMs and applied them to daily Australian weather data to model continuous, right-skewed non-zero rainfall volume based on environmental predictors.

### Key Methodology & Mathematical Findings
* **Theoretical Derivations:** Derived exponential family forms, unit deviance equations, link functions (inverse, identity, log), and dispersion estimators (Pearson vs. MLE).
* **Data Preprocessing:** Subsampled data at 5-day intervals to remove serial autocorrelation and filtered zero-rainfall days. Confirmed the expected quadratic mean-variance relationship $V(\mu) = \mu^2$.
* **Model Selection:** Fitted a Gamma GLM using a log link function, isolating significant predictors via sequential F-tests.

### Empirical Results (% Effect on Rainfall Volume)
| Predictor | Effect per Unit Increase |
| :--- | :--- |
| **Minimum Temp** | **+9.0%** |
| **Morning Humidity (9am)** | **+2.3%** |
| **Morning Wind Speed (9am)** | **+2.2%** |
| **Morning Atmospheric Pressure (9am)** | **-4.8%** |
| **Maximum Temp** | **-8.0%** |

> **Key Takeaway & Limitations:** While Gamma GLMs effectively capture continuous right-skewed data, zero-inflated continuous datasets with repeated discrete measurements cause fitting issues. Truncated or Tobit models are better suited for full precipitation modeling.
