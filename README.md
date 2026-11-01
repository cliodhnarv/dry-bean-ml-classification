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
- Planned for Milestone 3: K-Nearest Neighbours, Decision Tree and Random Forest. These models have not been implemented yet.

## Evaluation

Primary metric:
- Macro F1 score

Additional evaluation:
- Accuracy
- Per-class precision and recall
- Confusion matrix

The current baseline uses accuracy and macro F1 with 5-fold stratified cross-validation on the training data. Per-class precision/recall and a confusion matrix are planned for later evaluation. The held-out test set is reserved for final evaluation.

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

## Current Milestone 2 Progress

The notebook currently includes:

- Dataset loading and initial dataset inspection.
- Data quality audit of missing values, duplicates, target distribution and numerical summaries.
- Duplicate removal into a separate cleaned DataFrame and separation of predictors and target.
- Stratified train/test split and training-data exploration.
- Pass-through preprocessing setup inside a pipeline.
- Five-fold stratified cross-validation.
- Baseline model evaluation with per-fold scores, means and standard deviations for accuracy and macro F1.

Learned model comparisons remain work for Milestone 3.
