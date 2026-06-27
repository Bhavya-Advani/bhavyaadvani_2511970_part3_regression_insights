# Task 3: Dummy Variable Creation and Model Equations

## Dummy Variable Strategy and Reference Framework

Linear regression models require numerical input variables. Therefore, categorical variables such as **`region`** and **`store_type`** cannot be included directly in the regression model because they are stored as text values. These variables were converted into **dummy (binary) variables**, where:

* **1** indicates that an observation belongs to a particular category.
* **0** indicates that it does not.

However, including dummy variables for **all categories** together with the regression intercept would create **perfect multicollinearity**, commonly known as the **Dummy Variable Trap**. In this situation, one dummy variable can be perfectly predicted from the others, preventing the regression model from estimating unique coefficients.

To avoid this problem, one category from each categorical variable was omitted and used as the **reference category**.

---

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

---

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

---

# Dummy Variable Structure

### Region

| Region           | North | South | West |
| ---------------- | :---: | :---: | :--: |
| East (Reference) |   0   |   0   |   0  |
| North            |   1   |   0   |   0  |
| South            |   0   |   1   |   0  |
| West             |   0   |   0   |   1  |

---

### Store Type

| Store Type          | High Street | Mall | Residential |
| ------------------- | :---------: | :--: | :---------: |
| Airport (Reference) |      0      |   0  |      0      |
| High Street         |      1      |   0  |      0      |
| Mall                |      0      |   1  |      0      |
| Residential         |      0      |   0  |      1      |

---

# Interpretation of the Reference Categories

Because **East** and **Airport** were selected as the reference categories, their expected sales performance is incorporated into the regression intercept.

Consequently, the coefficients estimated for the remaining dummy variables represent the expected difference in monthly sales **relative to an otherwise similar store located in the East region and operating as an Airport store, while holding all other variables constant.**

It is important to note that the choice of reference category **does not affect the predictive performance or overall fit of the regression model**. It only changes how the coefficients are interpreted.

---

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

---

# Interpretation of the Categorical Variables

### Regional Effects (Relative to East)

* **Region West (+25,291.42):** After controlling for all other variables, stores located in the **West** are associated with approximately **$25,291** higher expected monthly sales than comparable stores in the **East**.

* **Region South (+21,089.57):** Stores located in the **South** are associated with approximately **$21,090** higher expected monthly sales than East-region stores.

* **Region North (+9,948.71):** Stores located in the **North** are associated with approximately **$9,949** higher expected monthly sales than comparable stores in the East.

---

### Store Type Effects (Relative to Airport)

* **Residential (-44,695.09):** Residential stores are associated with approximately **$44,695** lower expected monthly sales than Airport stores, after controlling for the remaining predictors.

* **High Street (-24,475.84):** High Street stores are associated with approximately **$24,476** lower expected monthly sales than Airport stores.

* **Mall (-11,862.24):** Mall stores are associated with approximately **$11,862** lower expected monthly sales than Airport stores.

---

# Business Interpretation

The regression model suggests that store location and store format are important predictors of monthly sales after accounting for marketing spend, customer traffic, staffing, inventory availability, customer ratings, holiday periods, and competitor proximity.

Among the regional categories, **West** and **South** stores are associated with higher expected monthly sales than stores in the **East**. Similarly, **Airport** stores represent the highest-performing reference category, while **Residential**, **High Street**, and **Mall** formats are associated with lower expected monthly sales after controlling for the other operational variables.

These findings indicate that geographic location and store format contribute meaningfully to differences in store performance and should be considered alongside operational investments such as marketing, staffing, and inventory management when making strategic business decisions.

---

# Summary

Categorical variables were converted into dummy variables to enable their inclusion in the multiple regression model. To avoid the Dummy Variable Trap, **East** was selected as the reference category for **Region**, and **Airport** was selected as the reference category for **Store Type**. The estimated coefficients therefore represent the expected change in monthly sales relative to these baseline categories while holding all other variables constant. This approach provides interpretable estimates of how store characteristics are associated with sales performance without introducing multicollinearity into the regression model.
