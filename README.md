# UnicornCompany-DA_Spark-sql-ml
Unicorn Companies Valuation Prediction
# 🦄 Unicorn Companies Valuation Prediction
![Alt text](path_or_URL_to_image)

## Project Overview
This project predicts the valuation of unicorn companies (private companies valued over $1B) using historical data on company characteristics, industry trends, investor information, and founding details.  
The goal is to provide insights into which factors most influence high valuations and to forecast potential future unicorns.

---

## Key Features
- **Data cleaning & preprocessing** of 100+ unicorn companies, including handling missing values and multi‑valued investor columns.
- **Feature engineering:**
  - Company age = `Date_Joined - Founded_Year`
  - Total funding raised
  - Number of investors
  - Industry, country, and financial stage encoded for ML models
  - Multi‑valued investor list transformed via `CountVectorizer`
- **Categorical encoding:** `StringIndexer` + `OneHotEncoder`
- **Feature assembly:** `VectorAssembler` to combine all features into a single vector

---

## Machine Learning Pipeline
- **Model:** `RandomForestRegressor` (PySpark ML) to predict company valuation (`Valuation_B`)
- **Pipeline:** Feature indexing → Encoding → Vectorization → Assembly → Model training
- **Train/test split:** 80/20
- **Evaluation metrics:** RMSE, MAE

---

## Performance Metrics
- **Root Mean Squared Error (RMSE):** 9.70  
- **Mean Absolute Error (MAE):** 2.41  
- **R² score:** 0.15  

---

## Key Learnings / Insights
- Unicorn valuations are **highly skewed** → log‑transformation can improve predictive performance.
- **Investor networks, industry, and company age** are significant predictors.
- **Small datasets** and **sparse multi‑valued categorical features** make accurate prediction challenging.
- Spark ML pipelines efficiently handle **complex feature engineering** and **large categorical encodings**.

---

## Future Improvements
- Apply **log‑transform** to target valuation to reduce skew.
- Explore **Gradient Boosted Trees** or **XGBoost** for improved performance.
- Include **macroeconomic / market trend data** for enhanced prediction.
- Optimize **multi‑investor encoding** for better generalization.

---

## Technologies Used
- **Apache Spark / PySpark**
- **Spark ML** (`RandomForestRegressor`, `VectorAssembler`, `CountVectorizer`, `OneHotEncoder`)
- **Python**
