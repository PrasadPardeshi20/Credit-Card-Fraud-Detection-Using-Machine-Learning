💳 Fraud Detection System using Machine Learning
This project implements a fraud detection system on a large-scale transactional dataset using Logistic Regression as the baseline model. It includes comprehensive data preprocessing, exploratory data analysis, and performance evaluation — with special attention to class imbalance and outliers.

📁 Dataset Overview
Size: ~6.3 million rows and 10 columns

Each row represents a financial transaction

Target Variable: isFraud (1 = Fraudulent, 0 = Normal)

Transaction types: CASH_OUT, TRANSFER, PAYMENT, DEBIT, etc.

🧹 Data Preprocessing
Removed identifier columns: nameOrig, nameDest

Applied log transformation (np.log1p) to numeric features with high skew:

amount, oldbalanceOrg, newbalanceOrig, oldbalanceDest, newbalanceDest

Used One-Hot Encoding for the type column to avoid false ordinal relationships

Dropped isFlaggedFraud due to no useful correlation with fraud

📊 Exploratory Data Analysis
Target Variable Distribution
The dataset is highly imbalanced — very few fraudulent transactions compared to non-fraud

Class imbalance is a critical issue that required correction before modeling

Transaction Type & Fraud
Most fraudulent transactions occurred in TRANSFER and CASH_OUT types

Correlation Heatmap
oldbalanceDest and newbalanceDest showed high correlation (~0.88)

isFraud had:

Moderate positive correlation with type_TRANSFER

Negative correlation with type_CASH_OUT

isFlaggedFraud had no meaningful correlations — removed

⚖️ Handling Class Imbalance
We used:

python
Copy
Edit
class_weight='balanced'
in Logistic Regression to automatically give more weight to minority (fraud) cases, compensating for the imbalance without oversampling or SMOTE.

🧠 Model: Logistic Regression
Why Logistic Regression?
Lightweight and interpretable

Scales to large datasets

Good starting point for fraud detection pipelines

Improvements Used:
Log transformation of outliers

One-hot encoding of categorical features

Balanced class weights

✅ Model Evaluation
Classification Report
Class	Precision	Recall	F1-score	Support
Not Fraud (0)	1.00	0.96	0.98	1,906,349
Fraud (1)	0.03	0.99	0.05	2,437

Accuracy: 96%

Recall (Fraud): 0.99 ✅

Precision (Fraud): 0.03 ⚠️

Confusion Matrix
yaml
Copy
Edit
                         Predicted: Not Fraud     Predicted: Fraud
Actual: Not Fraud            1,821,544               84,805
Actual: Fraud                      18                2,419
Interpretation
High recall: almost all fraud cases are detected

Low precision: many false positives, but acceptable in high-risk domains like banking

Shows strong fraud sensitivity — a good baseline for deployment

🛠️ How to Run
bash
Copy
Edit
# Clone the repository
git clone https://github.com/your-username/fraud-detection-ml.git
cd fraud-detection-ml

# Install dependencies
pip install -r requirements.txt

# Run the notebook
jupyter notebook Fraud_Detection.ipynb
📦 Dependencies
Python 3.x

pandas

numpy

matplotlib

seaborn

scikit-learn

🚀 Future Improvements
Try tree-based models: Random Forest, XGBoost

Use SMOTE or undersampling to handle class imbalance

Perform hyperparameter tuning and feature selection

Add real-time streaming fraud detection logic

✍️ Author
Prasad Pardeshi
