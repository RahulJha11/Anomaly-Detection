Credit Card Fraud Detection

Objective
This project aims to create machine learning models that can identify fraudulent transactions inside the Kaggle Credit Card Fraud Detection dataset. This necessitates dataset preparation, rectifying imbalances, and utilizing both supervised and unsupervised learning techniques to optimize model performance and resilience.


---

Dataset Examination and Readiness

1. Exploratory Data Analysis (EDA)
- **Class Distribution**: - The dataset exhibits significant imbalance, with fraudulent transactions comprising merely **0.17%** of the overall data:
    - Authentic Transactions: **99.83%**
    - Fraudulent Transactions: 0.17%
- **Feature Distributions**: - The majority of features are variables altered by Principal Component Analysis (PCA), namely V1 to V28. The "Amount" feature, which is not PCA-transformed, necessitates normalization.
- **Absence of Missing Values**: - The dataset is devoid of any missing values.

### 2. Data Preprocessing - **Standard Scaling**: - Normalize the "Amount" feature to maintain consistency during model training.
- **Addressing Class Imbalance**:
  - **Synthetic Minority Oversampling Technique (SMOTE)**: Create synthetic samples for the minority fraud class to enhance model efficacy.
  - **Undersampling**: Conduct experiments to diminish the size of the majority class in order to equilibrate the dataset.
  - **Class Weights**: Employ weighted loss functions during training to impose penalties for misclassifications of the minority class.

---

Model Development

Supervised Learning

1. **Baseline Model**: - Train a **Logistic Regression** model to set a performance standard.
   - Assess performance utilizing metrics like accuracy, precision, recall, and F1-score.

2. **Primary Model**: - Employ **XGBoost**, which is exceptionally proficient for imbalanced datasets.
   - Conduct hyperparameter optimization using **GridSearchCV**, concentrating on parameters including learning rate, maximum depth, and the number of estimators.

3. **Performance Comparison**: - Evaluate the Logistic Regression and XGBoost models.
   - Emphasize memory and F1-score to reduce false negatives, as the identification of fraudulent transactions is paramount.

Unsupervised Learning

1. **Autoencoder for Anomaly Detection**: - Train an autoencoder to reconstruct transactions and detect anomalies through reconstruction errors.

2. **Configuration for Infrequent Events**: - Modify hyperparameters (e.g., contamination ratio) to more effectively focus on the minority fraud class.

3. **Anomaly Assessment**: - Contrast identified abnormalities with established fraudulent transactions.
   - Evaluate precision and recall for the anomalies identified as fraudulent.

---

Model Assessment

### Supervised Models - Assess performance utilizing metrics such as: - **Recall**: Emphasize the reduction of false negatives.
  - **Precision** and **F1-score**: Assess the equilibrium between precision and recall.
- Employ **confusion matrices** to evaluate classification inaccuracies.
- Generate **ROC-AUC** and **Precision-Recall curves** to illustrate model efficacy.

### Unsupervised Models
- Contrast the anomalies detected by the autoencoder with genuine fraudulent transactions.
- Compute the precision and recall metrics for the identified abnormalities.

### Comparative Analysis of Methodologies - Evaluate the advantages and disadvantages of supervised and unsupervised techniques in identifying fraudulent activities.
  - Supervised techniques frequently yield superior precision and recall for recognized patterns.
  - Unsupervised techniques can detect unprecedented fraud patterns not observed during training.

---

## Summary
This study exemplifies a thorough methodology for fraud detection by: 1. Mitigating class imbalance by data preprocessing techniques, including SMOTE and class weighting.
2. Constructing resilient supervised models (Logistic Regression and XGBoost) for accurate fraud detection.
3. Investigating unsupervised techniques (Autoencoder) to detect abnormalities that diverge from typical transaction patterns.
4. Analyzing and synthesizing insights from both approaches to improve consistency, robustness, and recall in fraud detection.

The integration of supervised and unsupervised methodologies guarantees a comprehensive solution adept at identifying both established and novel fraudulent activities, providing actionable insights for successful fraud mitigation.

