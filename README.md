# Customer Churn Prediction
![Churn](https://github.com/aryanc381/Churn-Prediction-for-Banks-Understanding-Customer-Retention/blob/main/pic.png)
## Overview
Customer churn prediction is crucial for businesses, especially banks, to identify clients likely to leave the organization. This project employs machine learning techniques to predict customer churn using a deep learning model. The dataset, preprocessing steps, and neural network architecture are detailed below.

---

## Project Workflow
The project follows these steps:
1. **Data Acquisition**: Load the dataset containing customer demographics, account details, and churn labels.
2. **Data Preprocessing**:
   - Remove unnecessary columns.
   - Convert categorical data to numerical using one-hot encoding.
3. **Feature Scaling**: Normalize data to improve model performance.
4. **Model Development**:
   - Build a Sequential Neural Network.
   - Train the model on processed data.
5. **Evaluation**: Assess model accuracy and performance on the test set.

---

## Dataset
The dataset contains the following attributes:
- **Demographics**: `CreditScore`, `Geography`, `Gender`, `Age`.
- **Account Details**: `Tenure`, `Balance`, `NumOfProducts`, `HasCrCard`, `IsActiveMember`, `EstimatedSalary`.
- **Target Variable**: `Exited` (1 indicates churn; 0 indicates no churn).

The dataset is sourced from [Churn_Modelling.csv]([/path/to/dataset](https://www.kaggle.com/datasets/rjmanoj/credit-card-customer-churn-prediction?resource=download)).

---

## Libraries Used
The following Python libraries are employed:
- **Pandas**: For data manipulation and analysis.
- **NumPy**: For numerical computations.
- **TensorFlow**: For building and training the deep learning model.
- **scikit-learn**: For data preprocessing and splitting the dataset.

---

## Data Preprocessing

### 1. Loading and Cleaning Data
Unnecessary columns like `RowNumber`, `CustomerId`, and `Surname` are dropped. The cleaned dataset looks like this:
| CreditScore | Geography | Gender | Age | Tenure | Balance  | NumOfProducts | HasCrCard | IsActiveMember | EstimatedSalary | Exited |
|-------------|-----------|--------|-----|--------|----------|---------------|-----------|----------------|-----------------|--------|
| 619         | France    | Female | 42  | 2      | 0.00     | 1             | 1         | 1              | 101348.88       | 1      |
| ...         | ...       | ...    | ... | ...    | ...      | ...           | ...       | ...            | ...             | ...    |

### 2. Encoding Categorical Variables
Using one-hot encoding, categorical variables like `Geography` and `Gender` are transformed into numerical features.

### 3. Splitting Dataset
The dataset is split into training and testing subsets:
- **Features (`X`)**: All columns except `Exited`.
- **Target (`y`)**: `Exited` column.

---

## Model Architecture
The project employs a **Sequential Neural Network** with the following architecture:
1. **Input Layer**: Accepts 11 input features.
2. **Hidden Layers**:
   - First Layer: 11 neurons, `sigmoid` activation.
   - Second Layer: 9 neurons, `relu` activation.
3. **Output Layer**: 1 neuron, `sigmoid` activation (binary classification).

### Model Summary
| Layer     | Output Shape | Parameters |
|-----------|--------------|------------|
| Dense_1   | (None, 11)   | 132        |
| Dense_2   | (None, 9)    | 108        |
| Output    | (None, 1)    | 10         |

**Total Parameters**: 250.

---

## Model Training
The model is compiled with:
- **Optimizer**: `Adam`
- **Loss Function**: `Binary Crossentropy`
- **Metrics**: `Accuracy`

Training involves:
- Batch Size: `42`
- Epochs: `100`
- Validation Split: `20%`

---

## Results
The model achieves high accuracy during training and validation. Detailed training logs show improvements across epochs: `80.35%`

If you have any doubts, please feel free to email me at `venomc381@gmail.com`.
