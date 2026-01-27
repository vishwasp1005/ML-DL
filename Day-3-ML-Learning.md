Day 3 – Decision Tree Classifier  
• Notes: Entropy, Gini, Information Gain  
• Implemented DecisionTreeClassifier with pruning  
• Added confusion matrix + accuracy + tree visualization  


📌 DAY 3 — Decision Tree Classifier
1️⃣ What is a Decision Tree?

A supervised ML algorithm used for:
✔ Classification
✔ Regression

It splits data using questions until samples become pure.

Example:

Is CreditScore < 650?
├── Yes → Default
└── No  → Safe

2️⃣ Key Concepts
🟤 Node Types

Root Node: first split

Decision Node: internal splits

Leaf Node: final class

3️⃣ Purity Measures
🔸 Entropy (ID3 Algorithm)

Measures impurity.


Entropy=−p1​log2​p1​−p2​log2​p2​
	​

◼ 0 = Pure
◼ High = Mixed classes

🔸 Gini Index (CART Algorithm – sklearn default)


Gini=1−(p12​+p22​)
	

✔ Faster
✔ sklearn uses CART + Gini by default


4️⃣ Information Gain

IG=Entropy(parent)−∑nni​​Entropy(childi​)

→ Higher IG = better split.


5️⃣ Overfitting Problem

Decision Trees easily overfit due to deep branches.

✔ High training accuracy
✘ Poor test accuracy

6️⃣ Pruning Techniques
Pre-Pruning

Limit tree before fully growing:

max_depth
min_samples_split
min_samples_leaf

Post-Pruning

Grow full tree then cut branches (cost complexity pruning):

ccp_alpha

🧪 PYTHON IMPLEMENTATION
