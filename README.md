# Planetary Nebulae Research

Scientific research on planetary nebulae (PNe) using machine learning to predict physical and chemical properties from observational data. (Junior Academy of Sciences)

## Overview

This repository contains Jupyter notebooks exploring the application of machine learning (primarily XGBoost regression) to planetary nebulae data. The work focuses on predicting elemental abundances (especially nitrogen) and other output parameters from emission lines, diagnostic ratios, and structural properties.

## Notebooks

| Notebook | Description |
|----------|-------------|
| `PN_mlj_nitr_80_20.ipynb` | Predicts nitrogen abundance using emission lines and diagnostic ratios (80/20 split). Achieves high performance (R² ≈ 0.94). |
| `PN_mlj_all witout_nitr_80_20.ipynb` | Models trained without nitrogen features. |
| `PN_mlj_nitr_retrain.ipynb` | Retraining experiments for nitrogen-related models. |
| `PN_mlj_regmet.ipynb` | Regression analysis focused on metallicity / related properties. |
| `PN_mlj_xgboost_all.ipynb` | XGBoost regression on a broader set of output parameters (R² ≈ 0.62 on cleaned data). |

## Data

The notebooks work with several CSV datasets that are merged on a common `id` column:

- Emission lines
- Diagnostic ratios
- Inner/outer radii (`rion`, `rout`)
- Output parameters (abundances, physical properties)

**Typical preprocessing:**
- Merging tables on `id`
- Handling extensive missing values (especially in abundance columns)
- Log-transformation of radius-related features
- Train/test splits (commonly 80/20 or 85/15)

## Models & Results

- **Primary model**: XGBoost Regressor
- Features: Emission lines, diagnostic ratios, structural parameters
- Targets: Elemental abundances (e.g. nitrogen), other physical parameters

Example results from nitrogen abundance prediction:
- R² ≈ 0.94
- Low RMSE on normalized scale

## Usage

Open any notebook in Jupyter or Google Colab. The notebooks are largely self-contained but expect the corresponding CSV data files to be present locally (or adjust paths accordingly).

Typical workflow:
1. Load and merge datasets
2. Clean missing values
3. Feature engineering
4. Train/test split
5. Train XGBoost (or other regressors)
6. Evaluate with MSE, RMSE, MAE, R²
7. Visualize predictions vs. actual values

## Libraries

- `pandas`, `numpy`
- `xgboost`
- `scikit-learn`
- Visualization: `matplotlib`, `seaborn`, `plotly`
- (Some notebooks also explore other regressors / neural approaches)
