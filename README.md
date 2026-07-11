# Iris Flower Classification (CodSoft Internship - Task 3)

This repository contains the implementation of **Task 3: Iris Flower Classification** as part of the CodSoft Data Science Internship.

## Project Goal
The objective of this project is to build a machine learning model that can learn from sepal and petal measurements of iris flowers and accurately classify them into their respective species (`setosa`, `versicolor`, or `virginica`).

## Dataset Description
The Iris dataset contains sepal and petal measurements for 150 iris flowers:
- `sepal_length`: Sepal length in cm
- `sepal_width`: Sepal width in cm
- `petal_length`: Petal length in cm
- `petal_width`: Petal width in cm
- `species`: Species of the iris flower (`setosa`, `versicolor`, `virginica`)

---

## Project Structure
```text
CODSOFT/
├── data/
│   └── iris.csv                          # Iris dataset (CSV)
├── .gitignore                            # Files ignored by Git (venv, cache)
├── requirements.txt                      # Project dependencies
├── README.md                             # Documentation (This file)
└── iris_flower_classification.ipynb      # Jupyter Notebook containing full ML pipeline
```

---

## Key Steps Implemented

### 1. Data Loading & Inspection
- Verified that the dataset contains 150 observations (50 for each of the three species) and has no missing or null values.

### 2. Exploratory Data Analysis (EDA)
- Plotted class distributions showing balanced species sizes.
- Visualized pairwise relationships using pairplots.
- Generated violin plots for sepal and petal length/width distributions, which highlighted that `setosa` is linearly separable from the other two species.

### 3. Data Preprocessing
- Encoded target species labels using `LabelEncoder`.
- Partitioned features and target into an 80% training set and a 20% testing set, using stratified splitting to ensure class balance.
- Standardized the feature matrices using `StandardScaler`.

### 4. Model Training & Evaluation
- Trained two classifiers:
  - **Logistic Regression** (baseline linear classifier)
  - **K-Nearest Neighbors (KNN)** (distance-based non-linear classifier)
- Evaluated models using classification reports (Accuracy, Precision, Recall, F1-Score) and confusion matrices.
- Both models achieved **100% test accuracy** on the 20% split (30 samples).
- Logistic Regression is recommended for deployment due to its simplicity, speed, and interpretability.

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
   Open `iris_flower_classification.ipynb` in the browser to view the code, plots, and models.
