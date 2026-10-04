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

## Planned Models

- DummyClassifier baseline
- K-Nearest Neighbours
- Decision Tree
- Random Forest

## Evaluation

Primary metric:
- Macro F1 score

Additional evaluation:
- Accuracy
- Per-class precision and recall
- Confusion matrix

## Repository Structure

- `notebooks/` - analysis and modelling notebooks
- `src/` - reusable Python code
- `data/` - dataset information
