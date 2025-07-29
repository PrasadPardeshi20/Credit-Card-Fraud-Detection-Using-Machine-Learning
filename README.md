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

### 🤖 Model: Logistic Regression:

Chosen for its simplicity and explainability.

Used class_weight='balanced' to deal with data imbalance.

Trained on preprocessed data with transformed numerical features.

### 📈 Model Performance:

Metric	Value
Accuracy	96%
Recall (Fraud)	0.99 ✅
Precision (Fraud)	0.03 ⚠️
F1 Score (Fraud)	0.05

0.05

### 🧮 Confusion Matrix:
|                       | Predicted: Not Fraud | Predicted: Fraud |
|-----------------------|----------------------|------------------|
| **Actual: Not Fraud** | 1,821,544            | 84,805           |
| **Actual: Fraud**     | 18                   | 2,419            |

### 🚀 How to Run
1. Clone the repo:
  git clone https://github.com/PrasadPardeshi20/Credit-Card-Fraud-Detection-Using-Machine-Learning.git
cd Fraud-Detection-Project

2. Install dependencies:
   pip install -r requirements.txt

3. Add the dataset to the jupyter folder (name it Fraud.csv)

4. Open the notebook:
   jupyter notebook Fraud_Detection.ipynb

 
### 🔮 Future Improvements
Try ensemble models: Random Forest, XGBoost, LightGBM

Use SMOTE or under-sampling for better class balance

Integrate real-time fraud detection pipeline (e.g., Kafka + Flask)

Perform threshold tuning for better precision-recall trade-off

### 🙏 Acknowledgments
Inspired by various Kaggle datasets on transaction fraud

---

### ⚠️ Note on Dataset

The dataset used in this project is extremely large (~6.3 million rows), which exceeds GitHub's file size limit (100 MB). Therefore:

- The CSV file **is not uploaded** to this repository.
- To run the project locally, you must place the dataset manually in the `data/` folder.
- Make sure the file is named `Fraud.csv`.

> If you need help getting the dataset, feel free to raise an issue or contact the project author.


