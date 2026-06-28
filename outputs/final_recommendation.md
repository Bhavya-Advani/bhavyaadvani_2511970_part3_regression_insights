# Task 9: Final Management Recommendation

## Executive Summary

Based on the multiple regression analysis of **320 store-month observations**, the **multiple regression model** was selected as the final analytical model because it explains approximately **82.7% of the variation in monthly sales (R² = 0.827)**. Compared with the simple regression models, the final model provides a more comprehensive understanding of how operational and structural factors are associated with store performance.

Overall, the analysis indicates that monthly sales are influenced by a combination of customer traffic, inventory management, marketing investment, regional location, and store format rather than a single business driver.


# 1. Factors Most Strongly Associated with Monthly Sales

The regression analysis identifies three key drivers of monthly sales.

### A. Footfall (Strongest Operational Driver)

* **Coefficient:** 33.86
* **P-value:** < 0.001

Each additional customer visit is associated with approximately **$33.86** higher monthly sales, holding the other variables constant.

This is the strongest operational predictor in the final model, highlighting the importance of attracting customers into stores.


### B. Inventory Availability

* **Coefficient:** 2,961.27
* **P-value:** < 0.001

A one-percentage-point increase in inventory availability is associated with approximately **$2,961** higher monthly sales.

Maintaining high inventory availability appears to be an important operational factor associated with stronger sales performance.

---

### C. Marketing Spend

* **Coefficient:** 1.19
* **P-value:** < 0.001

Marketing expenditure is positively associated with monthly sales after controlling for the other variables.

Although its estimated effect is smaller than footfall, marketing remains an important contributor to store performance.


### D. Regional and Store Characteristics

Compared with the reference categories:

* Stores located in the **South** and **West** regions are associated with significantly higher monthly sales than comparable stores in the East.
* **Airport** stores remain the highest-performing reference format.
* **Residential** and **High Street** stores are associated with lower monthly sales than Airport stores.

# 2. Variables Leadership Should Focus On

Based on the regression evidence, leadership should prioritize investments in the variables most strongly associated with monthly sales.

### Customer Traffic

Since footfall exhibits the strongest positive relationship with monthly sales, strategies that increase store visits should remain a primary business priority.

Potential initiatives include:

* Local promotional campaigns
* Community events
* Loyalty programmes
* Location-based marketing

---

### Inventory Management

Maintaining high inventory availability should remain an operational priority.

Improving stock availability can reduce lost sales opportunities while enhancing the customer shopping experience.

---

### Marketing Investment

Marketing should continue to support customer acquisition and traffic generation. However, marketing should be integrated with broader operational initiatives rather than viewed as the sole driver of sales growth.



### Learn from High-Performing Regions

The consistently stronger performance of stores located in the South and West regions suggests that leadership should investigate whether operational practices, merchandising strategies, or local market conditions can be replicated across other regions.


# 3. Variables That Should Not Be Over-Interpreted

Not every coefficient in the regression model provides strong statistical evidence.

The following variables should be interpreted cautiously:

| Variable                        | Reason                                                                                                                                              |
| ------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Region North**                | Positive coefficient, but not statistically significant (p = 0.238).                                                                                |
| **Mall Store Type**             | Negative coefficient, but not statistically significant (p = 0.270).                                                                                |
| **Average Discount Percentage** | A negative coefficient does not necessarily imply that discounts reduce sales. Lower-performing stores may simply rely more heavily on discounting. |
| **Competitor Distance**         | The observed relationship may reflect broader market characteristics rather than a direct business effect.                                          |

These variables may still provide useful business context, but they should not be the primary basis for strategic decisions without further investigation.


# 4. Recommended Business Actions

Based on the regression findings, the following actions are recommended.

### 1. Increase Customer Footfall

Prioritize initiatives that encourage additional customer visits through targeted local marketing, promotional events, and customer engagement programmes.



### 2. Improve Inventory Availability

Implement operational initiatives aimed at improving stock availability across stores.

A pilot programme could be conducted in stores with relatively low inventory availability to evaluate whether improvements in product availability are associated with stronger sales performance.


### 3. Benchmark High-Performing Regions

Investigate the operational practices of stores located in the South and West regions and assess whether successful strategies can be implemented across other regions.


### 4. Review Lower-Performing Store Formats

Conduct operational reviews of Residential and High Street stores to identify opportunities for improving productivity, customer experience, and store performance.


# 5. Risks and Limitations

Although the regression model performs well overall, leadership should consider several limitations.

* The model explains **82.7%** of the variation in monthly sales, meaning approximately **17.3%** remains unexplained.
* Variables such as weather, store size, local economic conditions, competitor pricing, and customer demographics were not included in the model.
* The regression output indicates a relatively large condition number, suggesting potential multicollinearity or scaling differences among some predictors.
* The analysis is based on historical data and may not fully capture future market conditions.

Accordingly, the regression model should be used as a decision-support tool rather than the sole basis for strategic planning.


# 6. Association Does Not Automatically Mean Causation

Regression analysis identifies **statistical associations** between variables but does not, by itself, establish cause-and-effect relationships.

For example, stores with more staff may generate higher sales. However, this does not necessarily mean that hiring more employees will automatically increase sales. It is equally possible that stores with higher sales are allocated more staff because they already experience greater customer demand.

Similarly, higher marketing expenditure is associated with stronger sales performance, but the regression analysis alone cannot determine whether marketing directly caused the increase in sales.

Establishing causality would require additional evidence, such as randomized experiments, pilot programmes, or controlled A/B testing.

# Final Recommendation

The multiple regression model provides strong evidence that **customer footfall**, **inventory availability**, and **marketing investment** are the operational factors most strongly associated with monthly sales performance.

Leadership should prioritize initiatives that increase customer traffic, maintain high product availability, and improve operational execution while continuing to monitor marketing effectiveness. In addition, the stronger performance observed in the South and West regions should be investigated to identify practices that can be replicated across the broader store network.

Variables that are not statistically significant should be interpreted cautiously, and major strategic decisions should not rely on a single coefficient alone.

Finally, because regression identifies **associations rather than causation**, the recommended initiatives should be validated through pilot programmes or controlled experiments before being implemented across the entire retail network. This approach combines statistical evidence with practical business testing, supporting more reliable and informed decision-making.
