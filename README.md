# 📈 Online News Popularity Prediction using SVR

This project aims to predict the popularity (number of shares) of online news articles using **Support Vector Regression (SVR)** with both L1 and L2 regularization methods.

---

## 📂 Dataset

We use the [Online News Popularity Dataset](https://archive.ics.uci.edu/ml/datasets/online+news+popularity) from the UCI Machine Learning Repository.  
It contains 61 features extracted from online articles, including NLP-based attributes and metadata.  
**Target variable:** `shares` (number of shares an article received)

---

## 🔍 Project Overview

- Preprocessing steps:
  - Remove non-predictive columns (`url`, `timedelta`)
  - Apply log transformation to the skewed `shares` column
  - Split into training (80%) and testing (20%)
  - Feature scaling using `StandardScaler`
  
- Models used:
  - **SVR (RBF Kernel)** with L2 regularization
  - **LinearSVR** with L1 regularization (sparse feature selection)
  
- Evaluation metrics:
  - Mean Squared Error (MSE)
  - R² Score
  - Visual comparison of predictions vs. actuals
  - Feature importance analysis (via L1 sparsity)

---

## 🧪 Results & Findings

### Model Performance
| Model         | Regularization | R² Score | MSE     |
|---------------|----------------|----------|---------|
| SVR (RBF)     | L2             | ~0.12    | 0.7816  |
| LinearSVR     | L1             | Lower    | Higher  |

- L2-SVR (RBF) had better performance but longer training time.
- L1-LinearSVR gave sparse features (easier to interpret).

### Top Predictive Features
- `n_non_stop_words`
- `n_unique_tokens`
- `kw_avg_avg`

---

## 🛠 How to Run

1. Clone this repo:
   ```bash
   git clone https://github.com/your-username/svr-news-prediction.git
   cd svr-news-prediction
