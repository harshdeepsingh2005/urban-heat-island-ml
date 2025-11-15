# 📘 Urban Heat Island Prediction in Delhi — Supervised Machine Learning Project

## 🔍 Overview

This project builds a supervised machine learning model to predict Urban Heat Island (UHI) intensity across Delhi (India) using multi-source geospatial and environmental datasets.
The model uses only supervised regression algorithms and focuses on identifying the key factors that drive heat intensity in urban environments.

## 🎯 Objective

To develop supervised machine learning models that accurately predict Urban Heat Island (UHI) intensity in Delhi using multi-layer geospatial data, and to quantify which environmental and urban features most strongly influence heat patterns.

## 🗂️ Datasets Used (10-Layer Geo Dataset)

This project integrates 10 high-quality datasets for Delhi:

- MODIS LST (Land Surface Temperature)

- Landsat 8/9 LST (optional high-res)

- Sentinel-2 spectral indices (NDVI, NDBI, NDWI)

- Impervious Surface (GISA/GHSL)

- WorldPop Population Density

- ESA WorldCover Land Use / Land Cover

- Tree Canopy Cover (Copernicus / GFC)

- SRTM DEM (Elevation, slope, aspect)

- VIIRS Night Lights

- ERA5 Meteorology (temp, humidity, wind) (optional)

All datasets are clipped to the Delhi boundary and resampled to a 100m grid.

## 🧱 Project Structure

          delhi-uhi-ml/
          │
          ├── data/               # raw datasets
          ├── processed/          # clipped & resampled rasters
          ├── notebooks/          # Jupyter notebooks for EDA & modeling
          ├── src/                # preprocessing, feature extraction, ML pipeline code
          ├── models/             # trained supervised ML models
          └── README.md

## 🧪 Supervised Learning Models

The following regression models were used:

- Linear Regression (baseline)

- Decision Tree Regressor

- RandomForest Regressor

- XGBoost Regressor ⭐ main model

- LightGBM Regressor

- CatBoost Regressor (optional)

## 🏗️ Methodology

1. Data Preprocessing

  - Clip all rasters to Delhi boundary

  - Reproject to common CRS

  - Resample to 100m resolution

  - Create a 100m × 100m grid

  - Extract raster values for each grid cell

  - Merge all features into Final_Dataset.csv

2. Target Creation

  - Urban Heat Island intensity is computed as:

  - UHI = LST_pixel – mean(LST_rural_reference)

3. Feature Engineering

  - NDVI, NDBI, NDWI generation

  - Impervious % extraction

  - Tree canopy %

  - LULC one-hot encoding

  - Slope & aspect from DEM

  - Population & night lights merging

4. Model Training

  - Train using:

    * Train-test split

    * Hyperparameter tuning

    * RMSE, MAE, R² evaluation metrics

5. Interpretation

  - Feature importance (model-based)

  - SHAP value plots (optional)

6. Outputs

  - UHI prediction maps

  - Actual vs Predicted LST/UHI comparison

  - Feature importance visualization

## 📊 Results (Expected)

  - XGBoost performs the best

  - Impervious surface, NDVI, night lights, population density, and NDBI are top predictors

  - Strong spatial patterns of UHI across central and dense regions of Delhi

## 🧩 Technologies Used

  - Python

  - NumPy, Pandas

  - Scikit-learn

  - XGBoost, LightGBM, CatBoost

  - Rasterio, GDAL, Geopandas

  - Matplotlib, Seaborn

## 📌 How to Run

  - Clone the repository

          Install dependencies
          
          pip install -r requirements.txt


  - Run preprocessing

  - Train models via notebooks or scripts in /src

  - Visualize outputs

## 📜 License

Open for academic, research, and educational use.
