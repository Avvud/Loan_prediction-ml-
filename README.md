# Loan Prediction

A machine learning project that predicts loan approval status (`Loan_Status`) using supervised classification models in Python.

This repository currently contains a Jupyter notebook implementation:

- `loan-prediction.ipynb`

## Project Overview

The notebook walks through a full ML pipeline:

1. Load loan dataset
2. Explore and clean the data
3. Encode categorical features
4. Split data into train/test sets
5. Scale features
6. Train multiple classifiers
7. Evaluate model performance with `classification_report` and confusion matrix
8. Try basic hyperparameter tuning (`GridSearchCV`)

## Dataset

The notebook references Kaggle dataset import via `kagglehub`:

- Dataset: `bhavikjikadara/loan-status-prediction`

It then reads:

- `/content/loan_data.csv`

If you run locally, update the CSV path to your local dataset location.

## Tech Stack

- Python
- pandas
- numpy
- matplotlib
- seaborn
- scikit-learn
- kagglehub (optional, for Kaggle dataset download)

## Installation

Create and activate a virtual environment, then install dependencies.

```bash
python -m venv .venv
# Windows
.venv\\Scripts\\activate
# macOS/Linux
source .venv/bin/activate

pip install pandas numpy matplotlib seaborn scikit-learn kagglehub jupyter
```

## How To Run

1. Place `loan_data.csv` where your notebook can access it.
2. Update this line in the notebook if needed:
   - `data = pd.read_csv("/content/loan_data.csv")`
3. Start Jupyter:

```bash
jupyter notebook
```

4. Open `loan-prediction.ipynb` and run cells top to bottom.

## Modeling Implemented

The notebook trains and evaluates these models:

- Logistic Regression
- K-Nearest Neighbors (KNN)
- Gaussian Naive Bayes
- Decision Tree Classifier
- Support Vector Machine (SVM)

Hyperparameter tuning is introduced with `GridSearchCV` for Logistic Regression.

## Evaluation

Current evaluation methods in the notebook include:

- `classification_report` (precision, recall, f1-score)
- `confusion_matrix`

## Current Limitations / Notes

- The repository has a notebook (`.ipynb`) but no standalone `.py` script yet.
- Label encoding is applied to all feature columns, which may not be ideal for all variable types.
- Test data scaling uses `fit_transform` instead of `transform` (data leakage risk).
- Grid search results are not fully consumed (best parameters and retrained model are not shown).

## Suggested Improvements

- Convert notebook to modular Python scripts (`src/` structure).
- Use `ColumnTransformer` with proper categorical/continuous preprocessing.
- Fix scaling workflow:
  - `x_train = scaler.fit_transform(x_train)`
  - `x_test = scaler.transform(x_test)`
- Add metrics summary table for all models.
- Add cross-validation and ROC-AUC where appropriate.
- Add `requirements.txt` and reproducible environment file.

## Repository Structure

```text
loan_prediction/
+-- loan-prediction.ipynb
+-- README.md
```

## License

No license file is currently included. Add a `LICENSE` file if you plan to distribute this project.
