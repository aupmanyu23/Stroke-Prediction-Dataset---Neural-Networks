# Stroke-Prediction-Dataset---Neural-Networks

**Dataset Used**:  
We used the **Stroke Prediction Dataset** (https://www.kaggle.com/datasets/fedesoriano/stroke-prediction-dataset) from Kaggle, which includes 11 clinical features for predicting the likelihood of a stroke. These features include demographic and health-related attributes such as age, gender, BMI, average glucose level, hypertension, heart disease, and smoking status.

### Exploratory Data Analysis (EDA):  
We started by performing a thorough **Exploratory Data Analysis (EDA)** to understand the dataset:
1. **Missing Values**: The dataset had missing values in the BMI column, which we filled using the mean of the column.
2. **Outlier Detection**: We detected outliers in the `bmi` and `avg_glucose_level` columns using the **Interquartile Range (IQR)** method. A total of 126 outliers were found in `bmi` and 627 in `avg_glucose_level`. These were subsequently removed.
3. **Label Encoding**: We encoded categorical variables such as `gender`, `ever_married`, `work_type`, `Residence_type`, and `smoking_status` using label encoding to convert them into numerical form.
4. **Normalization**: Features such as `age`, `bmi`, and `avg_glucose_level` were normalized to ensure that they had comparable scales.

### Model Training:
**Handling Class Imbalance**:  
Since stroke cases are rare in the dataset (class imbalance), we applied **SMOTE (Synthetic Minority Over-sampling Technique)** to generate synthetic samples of the minority class and balance the dataset.

**Neural Network Model**:  
We designed a feedforward **neural network** with the following architecture:
- Input Layer: Matches the number of features in the dataset.
- Two Hidden Layers: First with 64 neurons and ReLU activation, second with 32 neurons and ReLU activation.
- Output Layer: A single output neuron with a Sigmoid activation function to predict the probability of stroke.

We trained the model for **100 epochs** using **Binary Cross-Entropy Loss (BCELoss)** and the **Adam optimizer**.

### Results:
After training the model, the evaluation on the test set showed the following performance:
- **Accuracy**: 92.13%
- **ROC AUC**: 0.9638 (indicating strong model performance in distinguishing between stroke and non-stroke cases).
- **Confusion Matrix**:
  - **True Negatives (TN)**: 759
  - **False Positives (FP)**: 83
  - **False Negatives (FN)**: 50
  - **True Positives (TP)**: 798


