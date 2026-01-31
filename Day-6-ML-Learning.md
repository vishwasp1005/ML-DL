DAY 6 — MODEL EVALUATION & HYPERPARAMETER TUNING
🟧 1️⃣ CONFUSION MATRIX (Base of Everything)


                  predicted 0     predicted 1 
				  
	actual 0         TN               FN

	actual 1         FP               TP


TP → Correct positive

TN → Correct negative

FP → False alarm

FN → Missed positive

from sklearn.metrics import confusion_matrix
cm = confusion_matrix(y_test, y_pred)
print(cm)

🟪 2️⃣ PRECISION, RECALL & F1 SCORE
🔹 Precision

Out of predicted positives, how many are correct?


Precision=TP+FPTP​
	​


Use when false positives are costly (spam detection).

🔹 Recall

Out of actual positives, how many did we catch?


Recall=TP+FNTP​​


Use when false negatives are costly (disease detection).

🔹 F1 Score

Balance between Precision & Recall


F1=   2×Precision×Recall / Precision+Recall
	​

🔵 3️⃣ ROC CURVE & AUC SCORE

ROC Curve → TPR vs FPR

AUC → Area under ROC curve

AUC Score	Model Quality


0.5	Random

0.7–0.8	Good

0.8–0.9	Very Good

>0.9	Excellent


🟩 4️⃣ CROSS VALIDATION (Very Important)

Instead of single train-test split, we train model multiple times.


✔ More reliable accuracy
✔ Reduces overfitting


🟨 5️⃣ GRIDSEARCH CV (Hyperparameter Tuning)

Automatically finds best parameters.

✔ Improves performance

