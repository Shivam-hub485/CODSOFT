# Titanic Survival Prediction (CodSoft Internship - Task 1)

This repository contains the implementation of **Task 1: Titanic Survival Prediction** as part of the CodSoft Data Science Internship.

## Project Goal
The objective of this project is to build a machine learning model that predicts whether a passenger on the Titanic survived or not based on historical data. 

## Dataset Description
The Titanic dataset contains individual passenger details:
- `Survived`: 0 = No, 1 = Yes (Target variable)
- `Pclass`: Ticket class (1 = 1st, 2 = 2nd, 3 = 3rd)
- `Sex`: Gender of passenger
- `Age`: Age in years
- `SibSp`: Number of siblings / spouses aboard the Titanic
- `Parch`: Number of parents / children aboard the Titanic
- `Fare`: Passenger fare
- `Embarked`: Port of embarkation (C = Cherbourg; Q = Queenstown; S = Southampton)

---

## Project Structure
```text
CODSOFT/
├── data/
│   └── titanic.csv                       # Titanic dataset (CSV)
├── .gitignore                            # Files ignored by Git (venv, cache)
├── requirements.txt                      # Project dependencies
├── README.md                             # Documentation (This file)
└── titanic_survival_prediction.ipynb     # Jupyter Notebook containing full ML pipeline
```

---

## Key Steps Implemented

### 1. Data Cleaning & Imputation
- Handled missing values: Imputed `Age` with the median and `Embarked` with the mode.
- Dropped features with high cardinality or excessive missing values (`Cabin`, `PassengerId`, `Name`, `Ticket`).
- Encoded categorical features (`Sex`, `Embarked`) using Label Encoding.

### 2. Exploratory Data Analysis (EDA)
- Visualized overall survival rate.
- Analyzed survival rates relative to gender (revealing that females had a survival rate of ~74.20% compared to ~18.89% for males).
- Explored class-based survival rates (showing 1st class passengers had higher survival rates than 3rd class passengers).
- Visualized age distribution against survival status.

### 3. Model Training & Comparison
- Split the dataset into 80% training and 20% testing sets.
- Standardized numerical features using `StandardScaler`.
- Trained and evaluated two classification algorithms:
  - **Logistic Regression** (Linear Baseline)
  - **Random Forest Classifier** (Tree-based ensemble)

### 4. Evaluation Results
- **Logistic Regression Test Accuracy**: ~81.01%
- **Random Forest Test Accuracy**: ~82.12%
- Built confusion matrices and classification reports for both models.
- **Feature Importance**: Analyzed Random Forest feature importances, showing that `Sex` (Gender) and `Fare`/`Pclass` were the most critical features in predicting survival.

---

## How to Run Locally

1. **Clone the repository**:
   ```bash
   git clone <your-repository-url>
   cd CODSOFT
   ```

2. **Create and activate a virtual environment**:
   ```bash
   python -m venv .venv
   # Windows:
   .venv\Scripts\activate
   # macOS/Linux:
   source .venv/bin/activate
   ```

3. **Install dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

4. **Launch Jupyter Notebook**:
   ```bash
   jupyter notebook
   ```
   Open `titanic_survival_prediction.ipynb` in the browser to view the code, plots, and models.
