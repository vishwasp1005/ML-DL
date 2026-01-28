🚀 Day 2 Completed: Data Encoding, Missing Value Strategy, Model Evaluation Metrics, Regression Techniques, and Feature Scaling Implementation Notes.


🔥 1. Encoding Techniques
<details> <summary><strong>🔹 Why Encoding? (Click to expand)</strong></summary>

Machine Learning models understand numbers only — not text.
So categorical features must be converted to numerical form.

</details>
⭐ ① Label Encoding (Ordered Categories)

📌 Use when categories have rank/order
(e.g., Low < Medium < High)

⭐ ② One Hot Encoding (Non-Ordered Categories)

📌 Use when categories have no order

df = pd.get_dummies(df, columns=['Color'], drop_first=True)


📝 drop_first=True → prevents dummy variable trap


## 🔧 2. Handling Missing Values

| Technique | Best For                     | Code Example                                                     |
|-----------|-------------------------------|------------------------------------------------------------------|
| Mean      | Normal numeric                | `df['Age'].fillna(df['Age'].mean(), inplace=True)`              |
| Median    | Skewed numeric / Outliers     | `df['Income'].fillna(df['Income'].median(), inplace=True)`      |
| Mode      | Categorical                   | `df['Gender'].fillna(df['Gender'].mode()[0], inplace=True)`     |



✂️ 3. Train–Test Split


from sklearn.model_selection import train_test_split

X_train, X_test, y_train, y_test = train_test_split(
    X, y, test_size=0.2, random_state=42
)


🎯 Used to evaluate model performance on unseen data


📊 4. Evaluation Metrics
<details> <summary><strong>📉 Regression Metrics (Click to expand)</strong></summary>
MSE – Mean Squared Error
RMSE – Root MSE
rmse = mse ** 0.5
MAE – Mean Absolute Error
R² Score
    
💡 Higher R² = Better model

</details>
🧮 5. Multiple Linear Regression


📘 Formula  y=b0​+b1​x1​+b2​x2​+...+bn​xn​

🌀 6. Polynomial Regression

📌 Used for non-linear relationships.

⚙️ Formula  y=b0​+b1​x+b2​x2+b3​x3+...

⚡ 7. Feature Scaling
⭐ Standardization (Z-Score)

Used in: SVM, Logistic Regression, KNN, Neural Networks

⭐ Normalization (Min-Max)

Scales between 0 and 1

## 🏁 DAY 2 — Summary Table

| Topic                   | Why Use                 | Notes                          |
|------------------------|--------------------------|--------------------------------|
| Label Encoding         | Ordered labels           | Converts text → numbers        |
| One Hot Encoding       | Non-ordered labels       | Avoid dummy trap               |
| Missing Values         | Clean dataset            | Mean / Median / Mode           |
| Train–Test Split       | Unseen evaluation        | test_size = 0.2                |
| MSE / RMSE             | Error measurement        | RMSE easiest                   |
| MAE                    | Outlier safe             | Absolute difference            |
| R² Score               | Goodness of fit          | Closer to 1 = good             |
| Multiple Linear Reg.   | Multiple inputs          | Linear relationship            |
| Polynomial Regression  | Non-linear curve         | degree = 2/3                   |
| Standardization        | Gradient models          | mean = 0                       |
| Normalization          | NN & bounded models      | Scales 0–1                     |
