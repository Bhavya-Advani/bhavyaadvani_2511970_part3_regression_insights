
**Analysis Objective:** To identify key operational factors influencing monthly sales to inform strategic resource allocation.

---

## 1. Business Problem Summary

Leadership identified a need to understand why monthly sales fluctuate across the store network. The objective was to move from anecdotal understanding to an evidence-based model that identifies which business levers (marketing, staffing, inventory, traffic) provide the highest return on investment.

## 2. Dataset Description

* **Total Observations:** 320 monthly store performance records.
* **Scope:** Covers 4 regions, 4 store types, and key operational metrics.
* **Cleaning:** Missing values in `competitor_distance_km` and `customer_rating` were imputed using median values to ensure statistical robustness. Outliers were retained as they reflect legitimate, albeit extreme, business performance.

## 3. Dependent and Independent Variables

* **Dependent Variable:** `monthly_sales` (Predictive Target).
* **Numerical Predictors:** `marketing_spend`, `footfall`, `avg_discount_pct`, `staff_count`, `inventory_availability_pct`, `competitor_distance_km`, `customer_rating`.
* **Categorical Predictors:** `region`, `store_type`, `holiday_flag`.

## 4. Regression Approach

We employed **Ordinary Least Squares (OLS) Multiple Regression**. This approach was chosen to isolate the impact of individual variables while holding all other factors constant, thereby controlling for variables like location when measuring the impact of marketing or staffing.

## 5. Dummy Variable Approach

To include categorical strings (Region/Store Type) in the model, they were encoded as binary (0/1) flags.

* **Reference Categories (Baseline):** `Region: East` and `Store Type: Airport`.
* **Methodology:** We omitted the reference categories to avoid the **"Dummy Variable Trap"** (perfect multicollinearity). Coefficients for other categories represent the performance premium or deficit relative to these baselines.

## 6. Model Comparison Summary

| Metric | Simple Model (Footfall Only) | Final Multiple Regression |
| --- | --- | --- |
| **$R^2$ (Explanatory Power)** | 73.6% | **82.7%** |
| **Statistical Significance** | High | **Extremely High** |
| **Strategic Utility** | Limited | **Comprehensive** |

## 7. Final Model Selected

**The Multiple Regression Model** was selected as the definitive model because it explains **82.7%** of the variance in sales. It provides the most "realistic" view of the business by simultaneously accounting for the interaction between physical traffic, inventory health, and regional factors.

---

## 8. Business Recommendations

* **Prioritize Footfall:** Traffic is the #1 sales engine. Marketing should focus on high-intent local acquisition.
* **Improve Inventory:** A 1% increase in inventory availability drives ~$2,961 in sales. **Prioritize supply chain stability over general advertising.**
* **Replicate Success:** Investigate the "Best-in-Class" operational processes in South and West regions to export those efficiencies to the East and North.
* **Format Review:** Residential and High Street formats are underperforming relative to Airport hubs. Investigate if these require a different labor model or inventory mix.

## 9. Assumptions and Limitations

* **Causality vs. Correlation:** Regression shows that staff count is *associated* with sales, but it does not *prove* adding staff will increase sales (staffing might be a result of high sales). **A/B Testing is required before major CapEx.**
* **Unmeasured Factors:** We have a 17.3% "unexplained" variance, likely due to factors like store square footage, competitor pricing strategies, and local economic sentiment.

---

## 10. Evidence Summary (Screenshots)
**`analysis/regression_workbook.xlsx`**: Contains all raw data, dummy transformations, and OLS regression tables.
**`outputs/model_equations.md`**: Contains the full mathematical equations and variable mapping.
**`analysis/residual_analysis.md`**: Contains the audit of the "Top 5" outliers (high and low residuals) to identify best-practice stores vs. operational friction points.
**`screenshots/residuals_preview.png`**: [A visualization showing the distribution of residuals, confirming no systematic bias in the model].

