# Task 6: Model Comparison

## Objective

To determine the most suitable model for explaining monthly sales performance, three regression models were compared:

1. Simple Regression Model – Marketing Spend
2. Simple Regression Model – Footfall
3. Multiple Regression Model

The comparison evaluates each model based on explanatory power, statistical significance, business usefulness, and practical limitations.

---

# Model Comparison

| Model                                   | Dependent Variable | Independent Variables                                                                 | R-squared | Significant Variables (p < 0.05)                                                                       | Business Usefulness                                                                                                                                                                | Limitations                                                                                                                                                                                                                                    |
| --------------------------------------- | ------------------ | ------------------------------------------------------------------------------------- | --------: | ------------------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Simple Regression – Marketing Spend** | Monthly Sales      | Marketing Spend                                                                       | **0.167** | Marketing Spend                                                                                        | Demonstrates that marketing expenditure is positively associated with sales and provides a simple measure of marketing effectiveness.                                              | Explains only **16.7%** of the variation in sales and ignores other important operational factors.                                                                                                                                             |
| **Simple Regression – Footfall**        | Monthly Sales      | Footfall                                                                              | **0.736** | Footfall                                                                                               | Shows that customer traffic is the strongest individual predictor of monthly sales and is useful for evaluating traffic-generation initiatives.                                    | Considers only one predictor and does not account for inventory, regional differences, or store characteristics.                                                                                                                               |
| **Multiple Regression**                 | Monthly Sales      | Marketing Spend, Footfall, Inventory Availability, Region Dummies, Store Type Dummies | **0.827** | Marketing Spend, Footfall, Inventory Availability, Region South, Region West, High Street, Residential | Provides the most comprehensive explanation of monthly sales by simultaneously evaluating operational and structural factors. Supports strategic planning and resource allocation. | Does not capture every factor affecting sales. Approximately **17.3%** of variation remains unexplained. Some variables (Region North and Mall) are not statistically significant, and multicollinearity should be assessed before deployment. |

---

# Comparison of Explanatory Power

The explanatory power of the models improves substantially as additional predictors are incorporated.

| Model               |        R² | Interpretation                                                                                |
| ------------------- | --------: | --------------------------------------------------------------------------------------------- |
| Marketing Spend     | **0.167** | Explains only a small proportion of sales variation.                                          |
| Footfall            | **0.736** | Explains most of the variation and is the strongest single-variable model.                    |
| Multiple Regression | **0.827** | Explains the largest proportion of variation by combining operational and structural factors. |

The increase from **73.6%** to **82.7%** demonstrates the value of considering multiple business drivers simultaneously.

---

# Significant Variables

The multiple regression model identifies several statistically significant variables.

| Variable               | Direction | P-value | Business Interpretation                                                               |
| ---------------------- | --------- | ------: | ------------------------------------------------------------------------------------- |
| Footfall               | Positive  |  <0.001 | Strongest operational driver of monthly sales.                                        |
| Marketing Spend        | Positive  |  <0.001 | Marketing investment contributes positively to sales performance.                     |
| Inventory Availability | Positive  |  <0.001 | Better product availability is associated with higher monthly sales.                  |
| Region South           | Positive  |   0.005 | South region stores outperform comparable East region stores.                         |
| Region West            | Positive  |   0.003 | West region stores outperform comparable East region stores.                          |
| High Street            | Negative  |   0.014 | High Street stores are associated with lower sales than Airport stores.               |
| Residential            | Negative  |  <0.001 | Residential stores are associated with substantially lower sales than Airport stores. |

Variables that were **not statistically significant** include:

* Region North (p = 0.238)
* Mall Store Type (p = 0.270)

These variables should be interpreted cautiously and should not be used as the primary basis for business decisions.

---

# Business Usefulness

### Marketing Spend Model

Useful for understanding the individual relationship between marketing expenditure and sales but insufficient for supporting major strategic decisions because it ignores other important business factors.

### Footfall Model

Provides strong evidence that customer traffic is closely associated with sales performance. It is useful for evaluating traffic-generation strategies but cannot distinguish the effects of other operational variables.

### Multiple Regression Model

Provides the most complete understanding of monthly sales performance by simultaneously evaluating marketing investment, customer traffic, inventory management, regional location, and store format. This model is the most appropriate for forecasting, performance analysis, and strategic planning.

---

# Limitations

Although the multiple regression model performs well overall, several limitations remain.

* Approximately **17.3%** of sales variation remains unexplained.
* External factors such as weather, local economic conditions, competitor pricing, customer demographics, and store size were not included.
* The model assumes linear relationships between predictors and monthly sales.
* The regression identifies statistical associations rather than causal relationships.
* Additional diagnostic testing (such as Variance Inflation Factors) should be performed to evaluate potential multicollinearity.

---

# Final Model Selected

The **Multiple Regression Model** was selected as the final analytical model because it provides the highest explanatory power (**R² = 0.827**), incorporates multiple operational and structural variables simultaneously, and delivers the most actionable insights for leadership.

Compared with the simple regression models, it provides a more realistic representation of the factors associated with monthly sales and therefore offers the strongest foundation for business decision-making.
