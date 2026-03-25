# Exoplanet Detection using Kepler Light Curves

## Overview

This project focuses on detecting exoplanets by analyzing light curve data from the Kepler Space Telescope.

The goal is to identify transit signals (dip in brightness) using machine learning models, particularly a **1D Convolutional Neural Network (CNN)**.

## Dataset

* Source: Kepler Telescope Data (via Kaggle / MAST)
* Format: `.fits` files (astronomical time-series data)
* Example star analyzed: `kplr011446443`


## Pipeline

### 1. Data Acquisition

* Used `astroquery` to fetch Kepler light curve data

### 2. Preprocessing

* Converted FITS → Pandas DataFrame
* Handled missing values:
  * Dropped fully NaN columns
  * Interpolation + median filling
* Normalization (mean = 0, std = 1)
* Noise reduction using smoothing

### 3. Feature Engineering

* Segmented time-series data
* Created labels using flux threshold (anomaly detection approach)

### 4. Models Implemented

* Logistic Regression (baseline)
* LSTM
* GRU
* 1D CNN (final model)

## Model Architecture (CNN)

* Conv1D → ReLU → MaxPooling
* Batch Normalization
* Fully Connected Layers
* Sigmoid output for binary classification
