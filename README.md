# 🧠 Network Traffic Classification using Random Forest

This project presents a supervised machine learning approach to classify network traffic based on packet-level features. The main objective is to detect and classify types of traffic or anomalies using a Random Forest classifier, while addressing class imbalance through various handling techniques.

---

## 📂 Dataset Overview

The dataset consists of packet-level network traffic with 22 features, including:

- `Average_Packet_Size`
- `Min_Packet_Length`
- `Max_Packet_Length`
- `Fwd_Packet_Length_Mean`
- `Subflow_Fwd_Bytes`
- `ACK_Flag_Count`
- `Init_Win_bytes_forward`
- `Flow_IAT_Mean`
- `Fwd_IAT_Max`, `Fwd_IAT_Mean`
- `Flow_Duration`
- `target` (the class label)

> ⚠️ The dataset exhibited class imbalance, which was addressed during preprocessing.

---

## ⚙️ Preprocessing & Handling Imbalance

- Removed irrelevant/unnecessary columns (e.g., `Unnamed: 0`, IPs).
- Scaled numerical features.
- Handled **class imbalance** using:
  - Class weighting
  - Resampling techniques (e.g., SMOTE or RandomUnderSampler/OverSampler)

---

## 🌲 Model: Random Forest Classifier

### 🔧 Hyperparameter Tuning:
- `n_estimators`: optimized using GridSearchCV / RandomizedSearchCV
- `max_depth`, `min_samples_split`, `min_samples_leaf` tested for best generalization
- `class_weight='balanced'` used to handle imbalance internally

---

## 📈 Evaluation Metrics

- **Accuracy**
- **Precision / Recall / F1-Score**
- **Confusion Matrix**
- **ROC-AUC Curve**

> The model performed well on the minority classes due to the imbalance handling strategy.

---

## 🧪 Sample Results

| Metric       | Score   |
|--------------|---------|
| Accuracy     | 0.89    |
| F1-Score     | 0.89    |
---

## 📌 Key Takeaways

- Handling imbalanced data significantly improved classification performance.
- Random Forest provides robust results on tabular packet-based network features.
- Proper preprocessing and tuning can yield high-performing classifiers for network traffic analysis.
