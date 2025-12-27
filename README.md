# Multi-Scale SPEI Forecasting over the Tibetan Plateau  
### A Dynamic Residual-Weighted SARIMA–LSTM Framework with Spatial Attention

This repository provides the official implementation of the drought forecasting framework proposed in our study:

> **Multi-Scale SPEI Forecasting over the Tibetan Plateau Using a Dynamic Residual-Weighted SARIMA–LSTM with Spatial Attention**

The model is designed to improve multi-temporal drought prediction over the Tibetan Plateau by jointly capturing linear seasonality, nonlinear dynamics, and spatial heterogeneity in SPEI time series.

---

## 📌 Overview

Drought processes over the Tibetan Plateau are driven by complex interactions between precipitation variability, temperature-induced evapotranspiration, and strong spatial heterogeneity. Traditional statistical models or single machine-learning models often fail to adequately capture these characteristics across multiple time scales.

To address these challenges, this project proposes a **hybrid SARIMA–LSTM framework** that integrates:

- **SARIMA** for modeling linear and seasonal components  
- **LSTM with spatial attention** for learning nonlinear temporal–spatial dependencies  
- **Dynamic residual-weighted fusion** to adaptively balance linear and nonlinear contributions during drought evolution  

The framework is applied to **multi-scale SPEI prediction (SPEI-1, SPEI-3, SPEI-6, SPEI-12)** across the Tibetan Plateau.

---

## 🧠 Methodology

The proposed framework consists of four key components:

1. **SARIMA module**  
   - Captures linear trends and seasonal periodicity in SPEI time series  
   - Optimized using stationarity tests and parameter selection  

2. **Residual-based LSTM with Spatial Attention**  
   - Models nonlinear temporal dynamics from SARIMA residuals  
   - Incorporates latitude and longitude information  
   - Uses a spatial attention mechanism to emphasize drought-sensitive regions  

3. **Dynamic Residual Weighting Mechanism**  
   - Dynamically adjusts the contribution of SARIMA and LSTM outputs  
   - Based on residual contribution (RC) indicators  
   - Avoids static fusion limitations in conventional hybrid models  

4. **Multi-Scale Forecasting Strategy**  
   - Applied consistently across SPEI-1, SPEI-3, SPEI-6, and SPEI-12  
   - Supports both short-term drought monitoring and long-term drought assessment  

---

## 🗺 Study Area and Data

- **Study region:** Tibetan Plateau  
- **Drought index:** Standardized Precipitation Evapotranspiration Index (SPEI)  
- **Time scales:** 1, 3, 6, and 12 months  
- **Input features:**  
  - SPEI historical values  
  - SARIMA residuals  
  - Spatial coordinates (latitude, longitude)  

All data are preprocessed using normalization, temporal splitting (training/validation/testing), and stationarity checks.

---

## 📊 Main Results

The proposed SARIMA–LSTM framework demonstrates:

- Consistent improvements in prediction accuracy compared to:
  - Single statistical models (SARIMA)
  - Single machine-learning models (SVR, LSTM)
  - Static hybrid models (e.g., SARIMA–SVR)
- Particularly strong performance gains for **medium- and long-term drought prediction (SPEI-6 and SPEI-12)**
- Enhanced robustness under the complex climatic conditions of the Tibetan Plateau

---

## 📂 Repository Structure

```text
├── data/                  # Input SPEI data and spatial information
├── preprocessing/         # Data preprocessing and normalization scripts
├── sarima/                # SARIMA modeling and residual extraction
├── lstm/                  # LSTM and spatial attention implementation
├── fusion/                # Dynamic residual-weighting mechanism
├── evaluation/            # Model evaluation and comparison
├── figures/               # Figures for analysis and visualization
└── main.py                # Main execution script
