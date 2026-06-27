
Task 1: Understand the Dataset
Objective
The objective of this analysis is to identify the factors that influence monthly sales across retail stores. The findings will help management make evidence-based decisions regarding marketing investment, inventory management, staffing, discount strategies, and store operations.
1. Dependent Variable
The dependent (target) variable is the outcome the regression model will predict.
VariableReasonmonthly_salesThis is the primary business outcome that leadership wants to explain and predict. It will serve as the dependent variable in the regression model.


2. Potential Independent Variables
The following variables are potential predictors of monthly sales.
VariableExpected Relationship with Salesmarketing_spendHigher marketing investment is expected to increase customer awareness and sales.footfall. More customer visits are generally associated with higher sales.avg_discount_pctDiscounts may increase sales volume but could also reduce margins.staff_countAdequate staffing may improve customer service and sales performance.inventory_availability_pctBetter product availability should reduce lost sales opportunities.competitor_distance_kmStores farther from competitors may experience higher sales.holiday_flagSales may increase during holiday periods.customer_ratingHigher customer satisfaction may positively influence repeat purchases and sales.regionSales may differ across geographic regions.store_typeDifferent store formats may generate different sales levels.monthSeasonal effects may influence monthly sales performance.

3. Numerical Variables
The following variables contain quantitative values suitable for regression analysis.

marketing_spend
footfall
avg_discount_pct
staff_count
inventory_availability_pct
competitor_distance_km
customer_rating
monthly_sales
monthly_profit

4. Categorical Variables
These variables represent categories and should be encoded before regression.
VariableRecommended TreatmentregionOne-hot (dummy) encodingstore_typeOne-hot (dummy) encodingmonthEncode as dummy variables if seasonality is being modeledholiday_flagBinary variable (0 = No, 1 = Yes); can be used directly if already numeric5. Variables Requiring Cleaning or Transformation
Before fitting the regression model, the following preprocessing steps should be considered.
VariableSuggested Preparationmarketing_spendCheck for missing values and outliers; consider scaling if required.footfallCheck for missing values and extreme observations.avg_discount_pctVerify values fall within a valid percentage range (0–100).inventory_availability_pctConfirm values are within 0–100%.customer_ratingVerify rating scale and identify missing values.monthConvert to categorical variables if modeling seasonality.regionEncode as dummy variables.store_typeEncode as dummy variables.6. Variables That May Not Be

Useful for Regression
VariableReasonstore_idActs as a unique identifier and does not explain sales performance. It should not be included as a predictor.monthly_profitThis variable is strongly related to sales and is likely an outcome rather than a driver. Including it as an independent variable when predicting monthly sales may introduce data leakage and bias the regression results.Summary
The regression analysis will use monthly_sales as the dependent variable and evaluate how operational, marketing, customer, and store characteristics influence sales performance. Numerical predictors will be assessed directly, while categorical variables such as region, store_type, and month will be encoded before modeling. Variables that serve as identifiers (store_id) or represent business outcomes (monthly_profit) will be excluded to prevent biased or misleading regression results.
