# Neuroblastoma-outcome-prediction 

## Repository Structure:

### Combined_data_RF
Contains Random Forest models trained on both Microarray and RNA expression data.
In this approach, each clinical endpoint is modelled separately, meaning the training process switches the target endpoint and trains an independent model for each outcome.

### RNA_RF_model
Contains models trained using RNA expression data only.
Unlike the earlier approach, this notebook trains a single Random Forest model that simultaneously predicts all endpoints:

Binary clinical outcomes (e.g., risk, progression, survival)
Categorical outcome: disease stage

This model performs multi-output prediction, removing the need to switch endpoints between training runs.

## Accuracy

### Single Model Performance in RNA_RF_model

Prediction accuracy was computed for each clinical endpoint, including High risk, Progression, Death by disease and INSS stage, using a held-out validation dataset.

|   Endpoint  | Accuracy | ROC-AUC |
|-------------|----------|---------|
| Risk        |   0.86   |  0.96   |
| Progression |   0.84   |  0.87   |
| Death       |   0.86   |  0.92   |
| Stage       |   0.65   |  0.78   |

Performance differed across endpoints, partly reflecting class imbalance and limited sample sizes in certain clinical categories.
