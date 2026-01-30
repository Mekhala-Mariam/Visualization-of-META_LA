
# Traffic Dynamics Analysis using METR-LA Dataset

This repository contains a complete **exploratory data analysis (EDA)** and **time-series analysis** pipeline for the **METR-LA traffic dataset**, implemented in **Python** using **Google Colab**.
The analysis focuses on understanding **temporal traffic patterns**, **sensor-wise dynamics**, and **short-term dependencies** using visualization and autocorrelation.


## Project Overview

Traffic data is inherently **dynamic and temporal**. Understanding its behavior is crucial for:

* Traffic congestion analysis
* Short-term traffic forecasting
* Intelligent transportation systems
* Spatio-temporal modeling using Graph Neural Networks

In this project, we analyze traffic speed/flow recorded at **5-minute intervals** from multiple sensors deployed across **Los Angeles**.


## Key Objectives

* Explore traffic time series data from multiple sensors
* Visualize temporal patterns and daily trends
* Analyze traffic dynamics across all sensors
* Study short-term temporal dependencies using **Autocorrelation Function (ACF)**
* Prepare insights useful for downstream prediction models


##  Dataset: METR-LA

* **Location:** Los Angeles, USA
* **Sensors:** 207 traffic sensors
* **Sampling rate:** Every 5 minutes
* **Values:** Traffic speed / flow

The dataset can be obtained from:

* Kaggle
* Zenodo
* HuggingFace (Parquet format)

>  The dataset is **not included** in this repository due to size and licensing restrictions.


##  Technologies Used

* **Python 3**
* **Google Colab**
* **Pandas** – data handling and preprocessing
* **NumPy** – numerical operations
* **Matplotlib** – visualization
* **Statsmodels** – autocorrelation analysis


##  Analysis Workflow

### 1 Data Loading & Preprocessing

* Load traffic data into a Pandas DataFrame
* Convert timestamp to `DatetimeIndex`
* Handle missing values

```python
df.index = pd.to_datetime(df.index)
df.isna().sum().sum()
```


### 2️ Time Series Visualization

Visualize traffic patterns for selected sensors over a few days.

 Reveals:

* Daily traffic cycles
* Rush hour peaks
* Sensor-specific behavior


### 3️ Traffic Dynamics Heatmap

Downsample data to **30-minute intervals** and visualize traffic dynamics across all sensors.

 Reveals:

* Global traffic trends
* Sensor-level variability
* Congestion patterns



### 4️ Autocorrelation Analysis (ACF)

Analyze short-term temporal dependency using:

* Individual ACF subplots
* Combined ACF comparison plot

```python
acf(series, nlags=36)
```

 Reveals:

* Strong short-term correlation (5–60 minutes)
* Temporal dependence useful for forecasting models

## 📈 Output Visualizations

* 📉 Sensor-wise time series plots
* 🌈 Heatmap of traffic dynamics (sensors × time)
* 📊 ACF plots for temporal dependency analysis


##  How to Run (Google Colab)

1. Open Google Colab
2. Upload the notebook from `notebooks/`
3. Load the METR-LA dataset
4. Run cells sequentially

Recommended: Use Colab for memory efficiency and easy visualization.


##  Future Work

* Traffic prediction using **LSTM / GRU**
* Spatio-temporal modeling using **Graph Neural Networks (GNNs)**
* Incorporating sensor adjacency matrices
* Anomaly detection in traffic patterns


##  Author

**Mekhaila Mariam Mary**

This project is for **educational and research purposes only**.
Dataset usage is subject to the original dataset license.

