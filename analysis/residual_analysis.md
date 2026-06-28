# Residual Analysis Report

## 1. Top 5 Positive Residuals (Actual > Predicted)
| store_id   | month      |   monthly_sales |   predicted_sales |   residual |
|:-----------|:-----------|----------------:|------------------:|-----------:|
| STR-1073   | 2025-03-01 |          813317 |            697606 |   115711   |
| STR-1028   | 2025-04-01 |          713611 |            603456 |   110155   |
| STR-1026   | 2025-04-01 |          625514 |            524454 |   101060   |
| STR-1050   | 2025-04-01 |          735787 |            639364 |    96422.2 |
| STR-1030   | 2025-02-01 |          820519 |            724483 |    96035.8 |

## 2. Top 5 Negative Residuals (Actual < Predicted)
| store_id   | month      |   monthly_sales |   predicted_sales |   residual |
|:-----------|:-----------|----------------:|------------------:|-----------:|
| STR-1017   | 2025-03-01 |          685379 |            851739 |    -166360 |
| STR-1023   | 2025-02-01 |          627172 |            760562 |    -133390 |
| STR-1012   | 2025-01-01 |          595468 |            722105 |    -126638 |
| STR-1007   | 2025-02-01 |          800452 |            912994 |    -112542 |
| STR-1009   | 2025-01-01 |          641865 |            741946 |    -100081 |

## 3. Business Interpretation
- **Positive Residuals:** These stores generated significantly more sales than the model expected given their traffic, marketing, and format. These are likely 'high-efficiency' outliers due to unmeasured factors like superior local management, unique event-based demand, or a localized 'cult-following' status.
- **Negative Residuals:** These stores generated significantly fewer sales than expected. They might be struggling with hidden operational frictions, local competitor promotions not captured in the distance variable, or sub-optimal staff performance not reflected in the rating system.
- **Model Bias:** If clusters of negative residuals appear predominantly in one store type (e.g., Residential), the model is over-predicting for that format, suggesting a need for a format-specific feature refinement.
