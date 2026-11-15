# CT4101 ML Project
## Dry Bean Classification

This project investigates whether measurements of dry beans
can be used to classify beans into one of seven varieties using
machine learning.

The dataset being used is the Dry Bean Dataset from the UCI Machine Learning Repository.

## Prediction Task

Given 16 numerical measurements of a dry bean, predict its
bean variety.

Target variable:
- Class

Classes:
- Seker
- Barbunya
- Bombay
- Cali
- Dermason
- Horoz
- Sira

## Dataset

Source: UCI Machine Learning Repository  
Dataset: Dry Bean Dataset  
Records: approximately 13,611  
Features: 16 numerical input features  
Licence: CC BY 4.0

## Models

- Milestone 2: DummyClassifier baseline (`most_frequent`).
- Milestone 3: K-Nearest Neighbours, Decision Tree and Random Forest.

All three learned models were compared against the baseline. GridSearchCV was used to test different model settings.

Random Forest achieved the highest tuning CV macro F1 score of 0.9375, followed closely by KNN at 0.9374.

## Evaluation

Primary metric:
- Macro F1 score

Additional evaluation:
- Accuracy
- Per-class precision and recall
- Confusion matrix

The models were evaluated using 5-fold stratified cross validation on the training data. The results were compared before and after hyperparameter tuning.

The tuned Random Forest was used for error analysis. SIRA had the lowest recall, with the most frequent errors occurring between SIRA and DERMASON.

The held-out test set is reserved for final evaluation in Milestone 4.

## Repository Structure

```text
dry-bean-ml-classification/
├── README.md
├── ASSISTANCE.md
├── requirements.txt
├── .gitignore
├── data/
│   ├── README.md
│   └── raw/
│       └── Dry_Bean_Dataset.xlsx
└── notebooks/
    └── 01_data_audit_and_baseline.ipynb
```

The local `.venv/` is excluded from version control. Dataset provenance and licence information are in `data/README.md`; assistance is declared in `ASSISTANCE.md`.

## Windows Setup and Running the Notebook

Python version used: **Python 3.13.1**.

From the project root in PowerShell, create and activate the virtual environment, then install dependencies:

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install -r requirements.txt
```

Start JupyterLab from the same activated environment:

```powershell
python -m jupyterlab
```

Open `notebooks/01_data_audit_and_baseline.ipynb` and run it from top to bottom using the project virtual environment as the notebook kernel. In VS Code, select `.venv` as the notebook kernel and use **Run All**. Keep the raw spreadsheet at `data/raw/Dry_Bean_Dataset.xlsx`.

If the spreadsheet is missing, download it from the [UCI Dry Bean Dataset page](https://archive.ics.uci.edu/dataset/602/dry+bean+dataset), extract the archive and place `Dry_Bean_Dataset.xlsx` in `data/raw/`.

## Current Project Progress

Milestone 2 included:

- Dataset loading and initial dataset inspection.
- Data quality audit of missing values, duplicates, target distribution and numerical summaries.
- Duplicate removal into a separate cleaned DataFrame and separation of predictors and target.
- Stratified train/test split and training-data exploration.
- Pass-through preprocessing setup inside a pipeline.
- Five-fold stratified cross-validation.
- Baseline model evaluation with per-fold scores, means and standard deviations for accuracy and macro F1.

Milestone 3 included:

- Comparison of KNN, Decision Tree and Random Forest.
- Hyperparameter tuning using GridSearchCV.
- Initial and tuned model performance comparison.
- Confusion matrices and per-class error analysis.
- Draft discussion and conclusion.

The final test-set evaluation, report and demonstration video will be completed in Milestone 4.