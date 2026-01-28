🌳 Random Forest — Ensemble Learning

Random Forest = Many Decision Trees trained on random subsets.

✔ Why RF works better than a single decision tree?

Less overfitting

Less variance

More stable

Handles missing values

Works well on high-dimensional data

## 🌟 Bagging — Bootstrap Aggregation

RF uses Bagging:

Each tree gets random rows

Each tree gets random columns

All trees vote → Final prediction

Prediction=MajorityVote(trees)


## 🎯 Feature Importance

RF gives the importance of each feature:

Higher value = More effect on prediction.

Used a lot in ML interviews.


# 🟦 KNN — K-Nearest Neighbors Classifier

Non-parametric algorithm
→ NO training phase
→ Prediction happens by finding nearest neighbors.

## 📌 Distance Metrics
1. Euclidean Distance (Default)

d=(x1​−y1​)2+(x2​−y2​)2+...

​
2. Manhattan Distance

d=∣x1​−y1​∣+∣x2​−y2​∣

## 🎯 Scaling Required

KNN uses distance → scale your data.

Use StandardScaler or MinMaxScaler.

## 🔍 Choosing K value

Low K → Overfitting

High K → Underfitting

Best K → odd numbers (5,7,9)

Use Elbow method


