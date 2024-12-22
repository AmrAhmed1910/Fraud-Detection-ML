# Online Payment Fraud Detection

This project focuses on detecting fraudulent transactions in online payments using machine learning techniques. The dataset used is sourced from [Kaggle](https://www.kaggle.com/datasets/rupakroy/online-payments-fraud-detection-dataset).

## Project Structure

- **`fraud_detection.ipynb`**: Main Jupyter notebook containing all code for data analysis, preprocessing, model training, evaluation, and prediction.
- **`model.pkl`**: Serialized model file for deployment.
- **Dataset**:
  - Downloaded from Kaggle using KaggleHub.
  - Original file name: `PS_20174392719_1491204439457_log.csv`.

---

## Steps in the Project

### 1. **Dataset Overview**
- The dataset contains features like transaction type, amount, balances before and after transactions, and labels (`isFraud`) indicating fraudulent activity.
- Exploratory data analysis (EDA) includes examining correlations, null values, and transaction type distributions.

### 2. **Data Preprocessing**
- Mapped categorical transaction types to numerical values for compatibility with machine learning algorithms.
- Balanced the dataset using `RandomOverSampler` to address class imbalance.
- Split the data into training and testing sets (70% train, 30% test).

### 3. **Feature Selection**
- Selected features: `type`, `amount`, `oldbalanceOrg`, and `newbalanceOrig`.

### 4. **Modeling**
- Model: Decision Tree Classifier
  - Hyperparameters:
    - `ccp_alpha=0.01`
    - `max_features=3`
    - `min_samples_split=20`
    - `max_depth=5`
    - `random_state=42`
  - `class_weight="balanced"` is used to address class imbalance.

### 5. **Model Evaluation**
- Metrics:
  - Accuracy
  - Precision
  - Recall
  - F1-Score
  - AUC-ROC
- Visualized the confusion matrix to evaluate predictions.

### 6. **Saving and Loading the Model**
- The trained model is saved using Python's `pickle` library.
- Can be reloaded for predictions without retraining.

### 7. **Predictions**
- Provided multiple test samples to evaluate model performance on unseen data.
- Predictions are mapped to `Fraud` or `No Fraud` labels.