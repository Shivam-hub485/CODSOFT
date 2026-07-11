# Sales Prediction using Python (CodSoft Internship - Task 4)

This repository contains the implementation of **Task 4: Sales Prediction using Python** as part of the CodSoft Data Science Internship.

## Project Goal
The objective of this project is to build a regression model that forecasts product sales based on advertising expenditures across three different channels: **TV**, **Radio**, and **Newspaper**.

## Dataset Description
The Advertising dataset contains expenditures and sales volumes for 200 advertising campaigns:
- `TV`: Advertising budget spent on TV (in thousands of dollars)
- `radio`: Advertising budget spent on Radio (in thousands of dollars)
- `newspaper`: Advertising budget spent on Newspaper (in thousands of dollars)
- `sales`: Sales volume of the product (in thousands of units) - Target variable

---

## Project Structure
```text
CODSOFT/
├── data/
│   └── advertising.csv                   # Advertising dataset (CSV)
├── .gitignore                            # Files ignored by Git (venv, cache)
├── requirements.txt                      # Project dependencies
├── README.md                             # Documentation (This file)
└── sales_prediction.ipynb                # Jupyter Notebook containing regression ML pipeline
```

---

## Key Steps Implemented

### 1. Data Loading & Cleaning
- Loaded `advertising.csv` and dropped the index column (`Unnamed: 0`).
- Inspected shape, columns, and checked for null values (0 missing values).

### 2. Exploratory Data Analysis (EDA)
- Plotted individual scatter plots of TV, Radio, and Newspaper expenditures vs. Sales, complete with regression lines.
- Generated a correlation heatmap showing:
  - Very strong positive correlation between TV budget and sales (~0.90)
  - Moderate positive correlation between Radio budget and sales (~0.35)
  - Negligible correlation between Newspaper budget and sales (~0.05)

### 3. Data Preprocessing
- Separated features and target, and performed an 80/20 train-test split.
- Standardized the feature matrices using `StandardScaler` fitted on training statistics.

### 4. Model Training & Comparison
- Trained two regression algorithms:
  - **Linear Regression** (Baseline parametric model)
  - **Random Forest Regressor** (Ensemble tree-based non-linear model)
- Evaluated models using R-squared ($R^2$), Mean Absolute Error (MAE), and Root Mean Squared Error (RMSE).

### 5. Evaluation Results
- **Linear Regression Performance**:
  - $R^2$ Score: **90.59%**
  - Mean Absolute Error (MAE): **1.27**
  - Root Mean Squared Error (RMSE): **1.52**
- **Random Forest Regressor Performance**:
  - $R^2$ Score: **98.42%**
  - Mean Absolute Error (MAE): **0.49**
  - Root Mean Squared Error (RMSE): **0.64**
- The Random Forest Regressor outperformed Linear Regression by successfully capturing non-linear patterns. TV spending is the single most critical driver of sales volumes, followed by Radio.

---

## How to Run Locally

1. **Clone the repository**:
   ```bash
   git clone <your-repository-url>
   cd CODSOFT
   ```

2. **Create and activate a virtual environment**:
   ```bash
   py -m venv .venv
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
   Open `sales_prediction.ipynb` in the browser to view the code, plots, and models.
