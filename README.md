# Industrial IoT Sensor Forecasting | Phase 1

Group project for Principles and Design of IoT Systems at The British University in Egypt.

## Objective

Forecast the next minute's reading for **LIT101**, a tank-level sensor in the Secure Water Treatment (SWaT) dataset. The team resampled the sensor streams to one-minute intervals and evaluated statistical and machine learning models against a previous-minute persistence baseline.

## Phase 1 results

| Model | Recorded test RMSE (mm) |
| --- | ---: |
| Vector autoregression (VAR), six additional sensors | 1.163 |
| Tuned CatBoost | 3.214 |
| Tuned XGBoost | 3.381 |
| ARIMA | 4.776 |
| Previous-minute persistence | 15.669 |

These are the results recorded in the main notebook for one-step forecasting on the project's test split. The one-step setup uses recent observed readings and does not measure long-horizon performance. The SARIMA notebook is a separate exploratory experiment.

## Notebooks

1. [Sensor forecasting](01-sensor-forecasting.ipynb) covers exploratory analysis, preprocessing, feature engineering, model fitting and comparison.
2. [CatBoost convergence](02-catboost-convergence.ipynb) explores a longer training budget and early stopping.
3. [SARIMA experiment](03-sarima-experiment.ipynb) explores seasonal modeling and residual diagnostics.

## Run locally

Install the dependencies with `python -m pip install -r requirements.txt` and open the main notebook in Jupyter. It retrieves the SWaT dataset through KaggleHub and generates `swat_post_processed.csv`, which the CatBoost convergence notebook expects. Use the [dataset source](https://www.kaggle.com/datasets/vishala28/swat-dataset-secure-water-treatment-system) to check availability and access terms. Dataset files, trained models, and cached notebook outputs are excluded from this portfolio copy.
