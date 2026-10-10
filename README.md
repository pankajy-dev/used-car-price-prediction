# Used Car Price Prediction

A regression project that predicts used car prices from listing features and specifications (mileage, age, fuel type, engine power, equipment, etc.). It is aimed at helping a reseller price vehicles and understand which factors drive price.

## Objectives

- **Price prediction**: model car prices from features such as mileage, fuel type, and performance.
- **Market analysis**: explore trends and preferences in the used car market.
- **Feature importance**: identify the most influential factors on price (e.g. age, mileage, power).

## Repository Contents

| File | Description |
|------|-------------|
| `RR_Car_Price_Prediction.ipynb` | Main notebook: EDA, feature engineering, modelling and evaluation |
| `Car_Price_data.csv` | Dataset (stored with Git LFS, ~11 MB) |
| `Report.pdf` / `Report.odt` | Written report of the analysis and findings |

## Dataset

Key columns include `make_model`, `body_type`, `price` (target), `vat`, `km`, `Type`, `Fuel`, `Gears`, `age`, `Previous_Owners`, `hp_kW`, `Inspection_new`, `Paint_Type`, `Upholstery_type`, `Gearing_Type`, `Displacement_cc`, `Weight_kg`, `Drive_chain`, `cons_comb`, plus list-style equipment columns (`Comfort_Convenience`, `Entertainment_Media`, `Extras`, `Safety_Security`).

## Workflow

1. **Data understanding**: load data, check types, missing values and duplicates.
2. **Exploratory analysis**: distributions of numerical and categorical features, rare category grouping, correlation analysis.
3. **Target transformation**: log transform (`log1p`) of the skewed `price` target.
4. **Outlier handling**: IQR-based detection and 1st/99th percentile capping.
5. **Feature engineering**: brand extracted from `make_model`; equipment lists converted to binary flags (keeping features present in 5%–95% of cars); one-hot encoding of categoricals.
6. **Modelling**: 80/20 train-test split, scaling, baseline Linear Regression, then tuned **Ridge** and **Lasso** regression.
7. **Evaluation**: MAE, MSE/RMSE and R², with multicollinearity checked via VIF.

## Tech Stack

Python, pandas, NumPy, Matplotlib, Seaborn, SciPy, scikit-learn, statsmodels, Jupyter Notebook.

## Getting Started

```bash
git lfs install
git clone https://github.com/pankajy-dev/used-car-price-prediction.git
cd used-car-price-prediction
pip install pandas numpy matplotlib seaborn scipy scikit-learn statsmodels jupyter
jupyter notebook RR_Car_Price_Prediction.ipynb
```

> The CSV is tracked with Git LFS; make sure Git LFS is installed so the actual data is downloaded rather than a pointer file.

## Results

See the notebook and `Report.pdf` for model comparison, findings, limitations and practical implications.
