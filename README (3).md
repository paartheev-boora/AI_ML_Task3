
# 🏡 House Price Prediction Project

Predicting house prices is a classic data science problem that helps us understand the factors influencing property values. This project demonstrates a complete **end-to-end workflow**—from data preprocessing to model evaluation—using **multiple linear regression**. We also dive deep into feature relationships to interpret how each variable influences price, making this a practical and educational exploration.

---

## 📊 Dataset Overview

We use the `Housing.csv` dataset, containing **545 rows** and **13 features**, including:

- **Numerical features**: `price`, `area`, `bedrooms`, `bathrooms`, `stories`, `parking`.
- **Categorical features**: `mainroad`, `guestroom`, `basement`, `hotwaterheating`, `airconditioning`, `prefarea`, `furnishingstatus`.

These features represent both property attributes and amenities that could influence house prices.

---

## 🛠️ Workflow Summary

### 1️⃣ Data Loading
- **Library**: `pandas`
- Loaded dataset using:
  ```python
  df = pd.read_csv("Housing.csv")
  ```

---

### 2️⃣ Data Preprocessing
- **Categorical Encoding**: Applied **LabelEncoder** to convert text labels (e.g. 'yes', 'no', 'furnished') to numeric codes for regression.
- **Missing Values**: Checked and confirmed **no missing values** in the dataset.

---

### 3️⃣ Train-Test Split
- Used **scikit-learn**’s `train_test_split` to partition data:
  - **80% training**
  - **20% testing**
- Ensured reproducibility using `random_state=42`.

---

### 4️⃣ Model Training
- Employed **multiple linear regression** with `LinearRegression()` from **scikit-learn**.
- Fitted the model using:
  ```python
  model.fit(X_train, y_train)
  ```

---

### 5️⃣ Model Evaluation
- **Mean Absolute Error (MAE)**: ~979,680 – average deviation from true prices.
- **Mean Squared Error (MSE)**: ~1.77 trillion – penalizes larger errors.
- **R-squared (R²)**: ~0.65 – explains ~65% of price variability.

---

## 🔍 Feature-by-Feature Relationship Analysis

We explored **each feature’s relationship with price** by fitting **individual regression lines**:

| Feature               | Intercept        | Coefficient        | Interpretation |
|-----------------------|------------------|--------------------|----------------|
| **area**              | 2,512,254.26     | 425.73             | 🔼 Larger area increases price steadily. |
| **bedrooms**          | 2,123,152.26     | 873,140.74         | 🛏️ More bedrooms boost price by ~873k each. |
| **bathrooms**         | 2,223,852.17     | 1,960,953.61       | 🚿 Strong impact—each bathroom adds ~1.96M! |
| **stories**           | 3,227,798.30     | 829,763.04         | 🏢 More stories = higher price. |
| **mainroad**          | 3,396,518.55     | 1,527,176.08       | 🚗 Main road access adds ~1.5M. |
| **guestroom**         | 4,489,843.41     | 1,211,207.87       | 🛌 Guestroom presence adds value. |
| **basement**          | 4,435,660.50     | 757,038.22         | 🏠 Basement boosts price. |
| **hotwaterheating**   | 4,676,057.83     | 603,851.26         | 🔥 Adds ~600k. |
| **airconditioning**   | 4,156,110.93     | 1,790,907.28       | ❄️ Huge boost—adds ~1.79M! |
| **parking**           | 4,172,510.43     | 778,700.31         | 🚗 More parking spots = higher price. |
| **prefarea**          | 4,415,446.38     | 1,244,228.62       | 🌳 Preferred area increases price significantly. |
| **furnishingstatus**  | 5,467,302.54     | -717,960.97        | ⚠️ Negative relationship—likely due to encoding; needs review. |

---

## 📈 Visualization

We created **scatter plots with regression lines** for each feature:

✅ Data points are semi-transparent for clarity.  
✅ Regression lines are color-coded and labeled.  
✅ Graphs are easy to interpret and reveal trends.

---

## 📌 Key Takeaways

- **Bathrooms, airconditioning, mainroad, and prefarea** are **strong predictors** of house price.
- **Furnishingstatus** showed a negative coefficient—suggesting label encoding might need refinement (e.g. one-hot encoding).
- Model explains **~65%** of the variance—future work could include:
  - Feature engineering (e.g. interactions).
  - Regularization (Ridge/Lasso) to mitigate overfitting.
  - Advanced models like **Random Forests** or **XGBoost**.

---

## 🚀 Getting Started

1. Clone the repository:
   ```bash
   git clone <your-repository-url>
   cd house-price-prediction
   ```
2. Install dependencies:
   ```bash
   pip install pandas numpy scikit-learn matplotlib seaborn
   ```
3. Run the notebook:
   ```bash
   jupyter notebook
   ```
4. Open `HousePricePrediction.ipynb` and execute cells step by step.

---

## 📌 Recommendations

- Use **one-hot encoding** for categorical features to avoid ordinal bias.
- Explore **feature scaling** if using regularized models.
- Visualize **residuals** to check for homoscedasticity and model fit.

---

## 🤝 License

This project is open-source under the MIT License—feel free to use, modify, and share!

---

## 👩‍💻 Author

**Your Name**  
📧 your.email@example.com  
🔗 [LinkedIn/GitHub](https://your-profile-url)

---
