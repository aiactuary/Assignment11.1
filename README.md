# Assignment11.1
# Used Car Price Prediction with Lasso Regression

## Project Overview
This project uses machine learning to predict used car prices based on features like year, mileage, manufacturer, fuel type, and condition. The goal is to help used car dealers **optimize pricing decisions** and **refine inventory selection** using a data-driven approach.

---

## Model Summary

After comparing Linear Regression, Ridge Regression, and Lasso Regression, we selected **Lasso Regression** as our final model due to its ability to:
- Automatically remove irrelevant features
- Provide similar accuracy to other models
- Enhance interpretability for business use

**Final Model: Lasso Regression**
- **R² Score**: 0.7516
- **Adjusted R²**: 0.7515
- **RMSE**: \5882.90
- **Features Used**: 80 (from hundreds originally)

---

## Data Cleaning
- Filtered vehicles: `price between $1,000 and $50,000`, `year > 2000`
- Dropped high-cardinality or noisy columns: `model`, `paint_color`, `state`
- Removed rows with missing values
- Converted categorical variables using OneHotEncoding
- Scaled numerical variables using StandardScaler

---

## Key Findings
- **Luxury manufacturers** and **vehicle year** are the strongest predictors of price
- **Fuel types**, and **type of the vehicle** significantly impact value
- Reconditioning vehicles to improve condition can boost selling price


## Example: Understanding Price Prediction for a Porsche Diesel Truck

Let’s walk through how the model would predict the price of a used **Porsche**, using the most influential features from the Lasso regression model.

### Base Scenario
WNow, let’s adjust its characteristics to match a **diesel-powered Porsche truck from 2017** and see how each change affects price:

| Change Applied                      | Effect on Price     | Explanation |
|-------------------------------------|----------------------|-------------|
| `manufacturer_porsche`             | **+ $10,070**        | Porsche vehicles command a high brand premium due to performance and prestige. |
| `fuel_diesel`                      | **+ $8,573**         | Diesel engines are valued for fuel efficiency and durability — especially in trucks. |
| `year = 2017` (vs. 2015)           | **+ $14,226**        | Each newer year adds ~$7,113 — a 2-year difference adds significant value. |
| `type_truck`                       | **+ $4,581**         | Trucks are more valuable on average than sedans, especially for work or off-road use. |

---

### 🧮 Estimated Impact Summary
These four characteristics alone add over **$37,000 in estimated value** to the predicted vehicle price compared to a generic used car baseline.

---

### 🧠 Takeaway for Dealers
When considering inventory like a **Porsche diesel truck**:
- **Brand and powertrain matter** — luxury + diesel add major value.
- **Year is a huge lever** — newer is significantly more profitable.
- **Trucks continue to hold value**, especially when paired with diesel engines.

This kind of breakdown helps you understand **why** the model predicts a high price — and how you can use this insight to support pricing or acquisition decisions.

---

## Next Steps
- Integrate model into a pricing tool or internal dashboard
- Expand dataset with regional and seasonal trends
