# Boston Housing Price Prediction: OLS Regression Analysis

## Project Overview
This project estimates a linear regression model to predict housing prices in Boston. The goal of the analysis was to identify the most significant drivers of property values while rigorously addressing data redundancy. Using Ordinary Least Squares (OLS) regression, the final model successfully explains approximately 70% of the variance in Boston house prices. This project was completed in a group setting by myself and my teammates at Vistula University.

## Data Preparation & Feature Selection
To ensure a robust model, the initial dataset was evaluated for multicollinearity using a correlation matrix. 

Variables exhibiting high collinearity (correlation coefficients higher than 0.7 or lower than -0.7) were systematically dropped to prevent model instability. 
* **Variables Removed:** `INDUS`, `NOX`, `AGE`, `RAD`, and `TAX`
* **Final Features Selected:** `RM`, `DIS`, `PTRATIO`, `B`, and `LSTAT`

## Model Performance
* **Adjusted R-Squared:** 0.699 (The model explains ~70% of the variance in the dependent variable).
* **Statistical Significance:** All five independent variables are highly statistically significant, with p-values evaluating to 0.000 (well below the stringent 0.01 threshold).

## Key Findings & Business Insights
Prior to modeling, hypotheses were established regarding how each factor would influence house prices. The OLS output confirmed most expectations, but revealed interesting deviations that highlight the complexity of the housing market:

| Feature | Description | Expected Impact | Actual Coefficient | Insight |
| :--- | :--- | :--- | :--- | :--- |
| **RM** | Average rooms per dwelling | Positive | 4.4538 | Confirmed. More rooms strongly correlate with higher prices. |
| **LSTAT** | % lower status population | Negative | -0.6084 | Confirmed. Higher percentages correlate with lower prices. |
| **B** | Proportion of Black population | Positive | 0.0120 | Confirmed. Slight positive correlation observed. |
| **DIS** | Distance to employment centers | Positive | -0.6152 | **Unexpected.** Prices actually *decreased* further from employment centers, contrary to the initial hypothesis. |
| **PTRATIO**| Pupil-teacher ratio | Positive | -0.9423 | **Unexpected.** A higher ratio of students to teachers strongly correlates with *lower* house prices, suggesting buyers value well-resourced schools. |

## Technologies Used
* **Python** 
* **Pandas / NumPy** (Data manipulation and matrix operations)
* **Statsmodels / Scikit-learn** (OLS Regression modeling)
* **Matplotlib / Seaborn** (Correlation matrix visualization)

## How to Run This Project
1. Clone this repository to your local machine.
2. Install the required dependencies using `pip install -r requirements.txt`.
3. Run the Jupyter Notebook or Python script to view the correlation matrix, feature selection process, and final OLS summary.
