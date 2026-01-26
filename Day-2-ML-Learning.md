📌 DAY 2 CONTENT

✔ Label Encoding
✔ One Hot Encoding
✔ Handling Missing Values
✔ Train–Test Split
✔ Evaluation Metrics (MSE, RMSE, MAE, R²)
✔ Multiple Linear Regression
✔ Polynomial Regression
✔ Feature Scaling (Standardization + Normalization)

-----------------------------------------
📘 1. Encoding Techniques
-----------------------------------------
Why Encoding?

ML models only understand numbers, not text.

① Label Encoding (Ordinal Categories)

Use when categories have rank/priority/order
(e.g., Low < Medium < High)

from sklearn.preprocessing import LabelEncoder
le = LabelEncoder()
df['Education'] = le.fit_transform(df['Education'])

② One Hot Encoding (Nominal Categories)

Use when categories do not have order

df = pd.get_dummies(df, columns=['Color'], drop_first=True)


drop_first=True → avoids dummy variable trap.

-----------------------------------------
📘 2. Handling Missing Values
-----------------------------------------
Mean → Numerical + Normal Distributed
Median → Numerical + Skewed (outliers)
Mode → Categorical
df['Age'].fillna(df['Age'].mean(), inplace=True)
df['Income'].fillna(df['Income'].median(), inplace=True)
df['Gender'].fillna(df['Gender'].mode()[0], inplace=True)

-----------------------------------------
📘 3. Train–Test Split
-----------------------------------------

Purpose: Evaluate model performance on unseen data.

from sklearn.model_selection import train_test_split

X_train, X_test, y_train, y_test = train_test_split(
    X, y, test_size=0.2, random_state=42)

-----------------------------------------
📘 4. Model Evaluation Metrics
-----------------------------------------
Mean Squared Error (MSE)
from sklearn.metrics import mean_squared_error
mse = mean_squared_error(y_test, y_pred)

Root Mean Squared Error (RMSE)
rmse = mse**0.5


(Easiest to interpret)

Mean Absolute Error (MAE)
from sklearn.metrics import mean_absolute_error
mae = mean_absolute_error(y_test, y_pred)

R² Score
from sklearn.metrics import r2_score
r2 = r2_score(y_test, y_pred)


Higher R² → better model.

-----------------------------------------
📘 5. Multiple Linear Regression (MLR)
-----------------------------------------

Used when you have multiple independent features.

𝑦
=
𝑏
0
+
𝑏
1
𝑥
1
+
𝑏
2
𝑥
2
+
.
.
.
+
𝑏
𝑛
𝑥
𝑛
y=b
0
	​

+b
1
	​

x
1
	​

+b
2
	​

x
2
	​

+...+b
n
	​

x
n
	​

Code:
from sklearn.linear_model import LinearRegression

model = LinearRegression()
model.fit(X_train, y_train)
y_pred = model.predict(X_test)

-----------------------------------------
📘 6. Polynomial Regression
-----------------------------------------

Used when data pattern is curved (non-linear).

𝑦
=
𝑏
0
+
𝑏
1
𝑥
+
𝑏
2
𝑥
2
+
𝑏
3
𝑥
3
.
.
.
y=b
0
	​

+b
1
	​

x+b
2
	​

x
2
+b
3
	​

x
3
...
Code:
from sklearn.preprocessing import PolynomialFeatures

poly = PolynomialFeatures(degree=2)
X_poly = poly.fit_transform(X)

model = LinearRegression()
model.fit(X_poly, y)

-----------------------------------------
📘 7. Feature Scaling
-----------------------------------------
Why Scaling?

Some algorithms depend on distance, like:

Logistic Regression (GD)

KNN

SVM

Neural Networks

① Standardization (Z-Score Scaling)

Centers data around mean = 0, std = 1

from sklearn.preprocessing import StandardScaler

scaler = StandardScaler()
X_scaled = scaler.fit_transform(X)

② Normalization (MinMax Scaling)

Scales values between 0 and 1

from sklearn.preprocessing import MinMaxScaler

scaler = MinMaxScaler()
X_scaled = scaler.fit_transform(X)

-----------------------------------------
📌 DAY 2 SUMMARY TABLE
-----------------------------------------
Topic	Why Use	Extra Notes
Label Encoding	Ordered categories	Converts text → integers
One Hot Encoding	Non-ordered categories	Avoid dummy trap
Missing Values	Clean dataset	Mean/Median/Mode
Train–Test Split	Validation	test_size = 0.2
MSE / RMSE	Error	RMSE easiest
MAE	Outlier-safe error	Absolute difference
R² Score	Model performance	0–1 range
MLR	Multi-feature regression	Linear
Polynomial Regression	Non-linear	degree=2,3
Standardization	GD, KNN, SVM	mean=0
MinMax	NN, bounded	0–1
