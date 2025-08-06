# 💳 Credit Card Fraud Detection using Machine Learning

Fraudulent transactions are rare but can cause huge losses. This project focuses on identifying such frauds accurately using machine learning — specifically a Decision Tree Classifier — while dealing with extreme data imbalance **without using oversampling techniques like SMOTE**.

---

## 📁 Project Overview

- **Goal:** Detect fraudulent credit card transactions with high accuracy and recall.
- **Model Used:** Decision Tree Classifier
- **Dataset:** Simulated dataset with realistic transaction features (highly imbalanced)
- **Tech Stack:** Python, pandas, scikit-learn, matplotlib, seaborn

---

## 🧠 Why Decision Tree?

- Easy to interpret and visualize
- Captures non-linear patterns well
- Effective even on imbalanced data
- Fast training and prediction

---

## 📊 Confusion Matrix

|                             | Predicted: Not Fraud | Predicted: Fraud |
|-----------------------------|----------------------|------------------|
| **Actual: Not Fraud**       | 1,906,110            | 239              |
| **Actual: Fraud**           | 323                  | 2,114            |

### 🔍 Metrics Summary:
- **Accuracy:** 99.98%
- **Precision (Fraud):** High — very few false positives
- **Recall (Fraud):** High — most fraudulent cases are detected
- **F1-Score:** Balanced and optimized

---

## ⚖️ Handling Imbalanced Data

> **No SMOTE or Oversampling used.**  
> The model was evaluated directly on the imbalanced dataset to test the natural capability of the Decision Tree.

### Why SMOTE was Avoided?
- High recall and precision were already achieved without SMOTE
- Avoided adding synthetic data which may introduce noise
- Kept model interpretable and performance genuine

---

## 📌 Dataset Features

- **type**: Type of transaction (TRANSFER, CASH_OUT, etc.)
- **amount**: Transaction amount
- **oldbalanceOrg / newbalanceOrig**: Sender's balance before/after transaction
- **oldbalanceDest / newbalanceDest**: Receiver's balance before/after transaction
- **isFraud**: Label - 1 if transaction is fraud
- **isFlaggedFraud**: System-flagged fraud (rare)

---

## 📈 Data Visualization

- Correlation heatmaps
- Class distribution plots
- Feature importance via Decision Tree

> Visual insights help understand fraud patterns and the skewed nature of the dataset.

---

## 📦 How to Run the Project

1. Clone the repository  
   `git clone https://github.com/PrasadPardeshi20/Credit-Card-Fraud-Detection-Using-Machine-Learning.git`

2. Install dependencies  
   `pip install -r requirements.txt` (if available) or manually:  
   `pandas`, `numpy`, `scikit-learn`, `matplotlib`, `seaborn`

3. Run the notebook  
   Open `Fraud_Detection.ipynb` in Jupyter Notebook or Google Colab

---

## 🏁 Final Thoughts

- Achieved **excellent fraud detection** with a simple, interpretable model.
- Proved that even without resampling, a strong model can detect frauds well.
- Ideal for showcasing practical machine learning skills on real-world challenges.

---

## 🤝 Let's Connect!

-🟦LinkedIn:
(https://www.linkedin.com/in/prasad-pardeshi-a161662b6/)
- 📬 Email: prasadpardeshi480@gmail.com
- 🌐 [GitHub](https://github.com/PrasadPardeshi20)

---

> ⭐ If you found this project interesting, give it a star on GitHub!
