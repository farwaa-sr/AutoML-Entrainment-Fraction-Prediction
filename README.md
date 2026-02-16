# AutoML Sklearn - Entrainment-Fraction-Prediction
This project predicts the **entrainment fraction (`e`)** using AutoML sklearn workflows.
# Auto-Sklearn for Entrainment Fraction Prediction

AutoML workflow for predicting **entrainment fraction (`e`)** in vertical two-phase flow using **Auto-sklearn**, with comparisons against **Random Forest** and **Gradient Boosting (GBM)**. Auto Sklearn runs best on Linux.

## Project Highlights
- End-to-end regression pipeline in `Auto_SkLearn.ipynb`
- Full-feature vs reduced-feature experiments
- Model optimization and cross-validation
- Comparative benchmarking across algorithms
- SHAP-based explainability for best model
- Saved production-ready model artifacts

## Best Result
**Auto-sklearn (Full Dataset, Optimized)** achieved:
- **R²:** `0.953786`
- **RMSE:** `0.061043`
- **MAE:** `0.033579`

## Dataset
Input features (full set, 8):
- Pipe Diameter
- vSG
- vSL
- rhoL
- rhoG
- Surface Tension
- viscosityL
- viscosityG

Data files used:
- `entraineddropletfraction_VerticalFlow.csv`
- `entraineddropletfraction_VerticalFlow-1.csv`

## Repository Structure
- `Auto_SkLearn.ipynb` - main notebook (EDA, modeling, optimization, explainability)
- `saved_models/` - exported trained model and metadata
- `X_train.csv`, `X_test.csv`, `y_train.csv`, `y_test.csv` - optional split exports
- `Feurer2019_Chapter_Auto-sklearnEfficientAndRobust.pdf` - background reference

## Model Artifacts
Generated in `saved_models/`:
- `best_autosklearn_full_optimized.pkl`
- `feature_names.pkl`
- `model_metadata.pkl`

## Tech Stack
- Python
- auto-sklearn
- scikit-learn
- pandas, numpy
- matplotlib, seaborn
- shap

## Run Locally
```bash
# 1) Create/activate environment
python -m venv .venv
# Windows
.venv\Scripts\activate
# Linux/macOS
source .venv/bin/activate

# 2) Install dependencies
pip install auto-sklearn scikit-learn pandas numpy matplotlib seaborn shap jupyter

# 3) Launch notebook
jupyter notebook Auto_SkLearn.ipynb
```
## Explainability
SHAP analysis indicates strongest influence from:

1. Pipe Diameter
2. vSG
3. rhoG
