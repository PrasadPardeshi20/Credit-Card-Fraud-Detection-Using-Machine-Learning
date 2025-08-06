### 💳 Credit Card Fraud Detection using Logistic Regression:

Fraudulent transactions are a critical challenge in the financial sector. This project focuses on detecting fraudulent transactions using a logistic regression model trained on a highly imbalanced dataset of over 6.3 million transactions.

### 📁 Dataset Information:

Rows: ~6.3 million

Columns: 10

Due to large size, the dataset is not uploaded to this repo.

### 📊 Features: 

Feature Name	Description
step	Time step of the transaction
type	Type of transaction (e.g., CASH_OUT, TRANSFER)
amount	Transaction amount
oldbalanceOrg	Sender’s original balance
newbalanceOrig	Sender’s balance after transaction
oldbalanceDest	Receiver’s original balance
newbalanceDest	Receiver’s balance after transaction
isFraud	Target variable (1 = Fraud, 0 = Not Fraud)
isFlaggedFraud	System flag (always 0 here, dropped during preprocessing)

### 🧪 Exploratory Data Analysis (EDA):

The dataset is highly imbalanced — most transactions are genuine.

Fraud is concentrated in CASH_OUT and TRANSFER transaction types.

Extreme values found in multiple columns like amount, oldbalanceOrg — handled using log1p transformation.

Heatmap revealed strong correlation between oldbalanceDest and newbalanceDest.

### 🛠️ Data Preprocessing: 

Log Transformation on skewed columns to reduce outlier impact:

amount, oldbalanceOrg, newbalanceOrig, oldbalanceDest, newbalanceDest

One-Hot Encoding for type (categorical, non-ordinal).

Dropped isFlaggedFraud as it held no meaningful variance.

Class imbalance handled using class_weight='balanced' in model training.


