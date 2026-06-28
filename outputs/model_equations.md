# Task 3: Dummy Variable Creation and Model Equations

## Dummy Variable Strategy and Reference Framework

Linear regression models require numerical input variables. Therefore, categorical variables such as **`region`** and **`store_type`** cannot be included directly in the regression model because they are stored as text values. These variables are converted into **dummy (binary) variables**, where:
**1** indicates that an observation belongs to a particular category.
**0** indicates that it does not.

However, including dummy variables for **all categories** together with the regression intercept would create **perfect multicollinearity**, commonly known as the **Dummy Variable Trap**. In this situation, one dummy variable can be perfectly predicted from the others, preventing the regression model from estimating unique coefficients.

To avoid this problem, one category from each categorical variable is omitted and used as the **reference category**.

# Reference Categories

### Region

The dataset contains four regions:

* East
* North
* South
* West

**Reference Category:** **East**

Dummy variables created:

* `region_North`
* `region_South`
* `region_West`

For stores located in the East region, all three dummy variables are equal to zero.


### Store Type

The dataset contains four store formats:

* Airport
* High Street
* Mall
* Residential

**Reference Category:** **Airport**

Dummy variables created:

* `type_High_Street`
* `type_Mall`
* `type_Residential`

Airport stores are represented when all three dummy variables equal zero.

# Dummy Variable Structure

### Region

| Region           | North | South | West |
| ---------------- | :---: | :---: | :--: |
| East (Reference) |   0   |   0   |   0  |
| North            |   1   |   0   |   0  |
| South            |   0   |   1   |   0  |
| West             |   0   |   0   |   1  |


### Store Type

| Store Type          | High Street | Mall | Residential |
| ------------------- | :---------: | :--: | :---------: |
| Airport (Reference) |      0      |   0  |      0      |
| High Street         |      1      |   0  |      0      |
| Mall                |      0      |   1  |      0      |
| Residential         |      0      |   0  |      1      |


# Interpretation of the Reference Categories

Because **East** and **Airport** are selected as the reference categories, their expected sales performance is incorporated into the regression intercept.

Consequently, the coefficients estimated for the remaining dummy variables represent the expected difference in monthly sales **relative to an otherwise similar store located in the East region and operating as an Airport store, while holding all other variables constant.**

It is important to note that the choice of reference category **does not affect the predictive performance or overall fit of the regression model**. It only changes how the coefficients are interpreted.


# Multiple Regression Equation

Based on the Ordinary Least Squares (OLS) estimation in `analysis/regression_workbook.xlsx`, the estimated regression model is:

[
\begin{aligned}
\widehat{\text{Monthly Sales}}
=&\ 86,319.14 \
&+1.21(\text{Marketing Spend})\
&+27.34(\text{Footfall})\
&-41,243.15(\text{Average Discount})\
&+3,508.40(\text{Staff Count})\
&+3,062.21(\text{Inventory Availability})\
&-3,438.11(\text{Competitor Distance})\
&+15,157.29(\text{Holiday Flag})\
&+12,509.46(\text{Customer Rating})\
&+9,948.71(\text{Region North})\
&+21,089.57(\text{Region South})\
&+25,291.42(\text{Region West})\
&-24,475.84(\text{Store High Street})\
&-11,862.24(\text{Store Mall})\
&-44,695.09(\text{Store Residential})
\end{aligned}
]


# Interpretation of the Categorical Variables

### Regional Effects (Relative to East)

 **Region West (+25,291.42):** After controlling for all other variables, stores located in the **West** are associated with approximately **$25,291** higher expected monthly sales than comparable stores in the **East**.

 **Region South (+21,089.57):** Stores located in the **South** are associated with approximately **$21,090** higher expected monthly sales than East-region stores.

 **Region North (+9,948.71):** Stores located in the **North** are associated with approximately **$9,949** higher expected monthly sales than comparable stores in the East.


### Store Type Effects (Relative to Airport)

 **Residential (-44,695.09):** Residential stores are associated with approximately **$44,695** lower expected monthly sales than Airport stores, after controlling for the remaining predictors.

 **High Street (-24,475.84):** High Street stores are associated with approximately **$24,476** lower expected monthly sales than Airport stores.

 **Mall (-11,862.24):** Mall stores are associated with approximately **$11,862** lower expected monthly sales than Airport stores.


# Business Interpretation

The regression model suggests that store location and store format are important predictors of monthly sales after accounting for marketing spend, customer traffic, staffing, inventory availability, customer ratings, holiday periods, and competitor proximity.

Among the regional categories, **West** and **South** stores are associated with higher expected monthly sales than stores in the **East**. Similarly, **Airport** stores represent the highest-performing reference category, while **Residential**, **High Street**, and **Mall** formats are associated with lower expected monthly sales after controlling for the other operational variables.

These findings indicate that geographic location and store format contribute meaningfully to differences in store performance and should be considered alongside operational investments such as marketing, staffing, and inventory management when making strategic business decisions.



# Summary

Categorical variables are converted into dummy variables to enable their inclusion in the multiple regression model. To avoid the Dummy Variable Trap, **East** was selected as the reference category for **Region**, and **Airport** was selected as the reference category for **Store Type**. The estimated coefficients therefore represent the expected change in monthly sales relative to these baseline categories while holding all other variables constant. This approach provides interpretable estimates of how store characteristics are associated with sales performance without introducing multicollinearity into the regression model.





# Task 8: Model Equations

## Objective

This document summarizes the regression models developed to identify the key drivers of monthly sales performance across retail stores. It includes the simple regression equations, the final multiple regression equation, an explanation of each coefficient, the treatment of dummy variables, and the rationale for selecting the final model.



# 1. Simple Regression Models

## Model 1: Footfall

### Regression Equation

[
\widehat{\text{Monthly Sales}} = 446,410.58 + 35.68(\text{Footfall})
]

### Business Interpretation

* The intercept (**446,410.58**) represents the estimated monthly sales when customer footfall is zero.
* The coefficient (**35.68**) indicates that each additional customer visit is associated with an average increase of approximately **$35.68** in monthly sales.
* With an **R² of 0.7363**, footfall alone explains approximately **73.6%** of the variation in monthly sales, making it the strongest standalone predictor among the simple regression models.



## Model 2: Marketing Spend

### Regression Equation

[
\widehat{\text{Monthly Sales}} = 560,777.35 + 2.13(\text{Marketing Spend})
]

### Business Interpretation

The intercept (**560,777.35**) represents the estimated monthly sales when marketing spend equals zero.
The coefficient (**2.13**) indicates that every additional **$1** invested in marketing is associated with approximately **$2.13** higher monthly sales.
The model explains **16.7%** of the variation in monthly sales (**R² = 0.1672**), indicating that marketing contributes positively to sales but is a weaker standalone predictor than footfall.



# 2. Multiple Regression Model

### Final Regression Equation

[
\begin{aligned}
\widehat{\text{Monthly Sales}}
=&\ 142,400 \
&+1.19(\text{Marketing Spend})\
&+33.86(\text{Footfall})\
&+2,961.27(\text{Inventory Availability})\
&+8,358.53(\text{Region North})\
&+20,250(\text{Region South})\
&+18,930(\text{Region West})\
&-23,050(\text{Type High Street})\
&-10,760(\text{Type Mall})\
&-39,630(\text{Type Residential})
\end{aligned}
]

### Model Performance

* **R²:** 0.827
* **Adjusted R²:** 0.822
* **F-statistic:** 164.50
* **Model P-value:** 2.00 × 10⁻¹¹²

The model explains approximately **82.7%** of the variation in monthly sales, indicating strong explanatory power.


# 3. Explanation of the Regression Coefficients

| Variable                   | Coefficient | Business Interpretation                                                                                                                             |
| -------------------------- | ----------: | --------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Intercept**              |     142,400 | Baseline monthly sales for an Airport store in the East region when the numerical predictors equal zero.                                            |
| **Marketing Spend**        |       +1.19 | Each additional **$1** invested in marketing is associated with approximately **$1.19** higher monthly sales, holding the other variables constant. |
| **Footfall**               |      +33.86 | Each additional customer visit is associated with approximately **$33.86** higher monthly sales.                                                    |
| **Inventory Availability** |   +2,961.27 | A one-percentage-point increase in inventory availability is associated with approximately **$2,961** higher monthly sales.                         |
| **Region North**           |   +8,358.53 | Stores in the North are estimated to have higher sales than those in the East, although this difference is not statistically significant.           |
| **Region South**           |     +20,250 | Stores in the South are associated with approximately **$20,250** higher monthly sales than comparable stores in the East.                          |
| **Region West**            |     +18,930 | Stores in the West are associated with approximately **$18,930** higher monthly sales than comparable stores in the East.                           |
| **High Street**            |     −23,050 | High Street stores are associated with lower monthly sales than Airport stores.                                                                     |
| **Mall**                   |     −10,760 | Mall stores are estimated to have lower sales than Airport stores, although this difference is not statistically significant.                       |
| **Residential**            |     −39,630 | Residential stores are associated with substantially lower monthly sales than Airport stores.                                                       |



# 4. Dummy Variables

The categorical variables **Region** and **Store Type** are converted into dummy variables so they could be included in the regression model.

### Region

Dummy variables created:

* Region_North
* Region_South
* Region_West

**Reference Category:** East



### Store Type

Dummy variables created:

* Type_High Street
* Type_Mall
* Type_Residential

**Reference Category:** Airport

One category from each variable was omitted to avoid the **Dummy Variable Trap**, which occurs when all categories are included simultaneously and creates perfect multicollinearity.


# 5. Final Model Selected

The **multiple regression model** was selected as the final predictive model.



# 6. Reason for Selecting the Final Model

The multiple regression model was selected because it provides a more comprehensive explanation of monthly sales than either simple regression model.

Although the simple regression models demonstrated that **Footfall** and **Marketing Spend** are individually associated with monthly sales, they consider only one business factor at a time.

The multiple regression model simultaneously evaluates marketing investment, customer traffic, inventory availability, regional location, and store type. By accounting for these factors together, the model increases the explanatory power from **73.6%** (Footfall model) and **16.7%** (Marketing model) to **82.7%**.

This provides leadership with a more realistic understanding of store performance and supports better operational decision-making.



# Business Summary

The analysis demonstrates that store performance is influenced by multiple operational and structural factors rather than a single business driver.

Among the variables included in the final model:

* **Footfall** is the strongest operational predictor of monthly sales.
* **Inventory Availability** is positively associated with higher sales, emphasizing the importance of maintaining product availability.
* **Marketing Spend** contributes positively to sales but has a smaller effect after accounting for customer traffic and store characteristics.
* Stores located in the **South** and **West** regions tend to outperform comparable stores in the **East**.
* **Airport** stores remain the highest-performing reference category, while **Residential** and **High Street** stores are associated with lower monthly sales.

Overall, the multiple regression model provides the most complete and business-relevant explanation of monthly sales performance and is recommended for forecasting and supporting operational decision-making.

