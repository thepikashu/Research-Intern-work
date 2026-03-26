# Exoplanetary Multi-System Analysis: Investigating the Radius Valley

[![Data Source: NASA Exoplanet Archive](https://img.shields.io/badge/Data-NASA%20Exoplanet%20Archive-orange)](https://exoplanetarchive.ipac.caltech.edu/cgi-bin/TblView/nph-tblView?app=ExoTbls&config=PS)

## Overview
This project explores the **Radius Valley**—a significant gap in the distribution of exoplanetary radii between $1.5$ and $2.0 \ R_{\oplus}$. Conducted during my research internship at the **Tata Institute of Fundamental Research (TIFR)**, this study utilizes data from over **3,000 multiplanetary systems** (Kepler and TESS) to understand how stellar radiation influences atmospheric loss.

## Key Research Goals
* **Bimodal Distribution:** Confirm the gap between Super-Earths and Sub-Neptunes across different star types.
* **Atmospheric Stripping:** Quantify the relationship between planetary radius change ($\Delta R$) and stellar irradiation ($S$).
* **Multi-planet Correlation:** Analyze if the "Radius Valley" signature is more pronounced in systems with multiple transiting planets.

## Technical Workflow

### 1. Data Processing
* **Cleaning:** Automated handling of missing values using linear interpolation and median imputation.
* **Filtering:** Narrowed the dataset to host stars ($3000\text{--}7000\text{ K}$) and planets ($\le 4 \ R_{\oplus}$).
* **Normalization:** Corrected flux values and calculated transit depths.

### 2. Astrophysical Math
The analysis implements core astrophysical laws:
* **Luminosity ($L$):** Computed using $L = 4\pi R_*^2 \sigma T_{eff}^4$.
* **Irradiation ($S$):** Calculated as $S = \frac{L}{4\pi a^2}$.
* **Slope Proxy:** Calculated $\frac{\Delta R}{\Delta \log_{10}(S)}$ for planet pairs within the same system to act as a proxy for atmospheric loss sensitivity.

### 3. Classification by Spectral Type
Analyzed systems separately to find mass-dependent trends:
* **M-type:** $< 4000\text{ K}$
* **K-type:** $4000\text{--}5200\text{ K}$
* **G-type:** $5200\text{--}6200\text{ K}$
* **F-type:** $> 6200\text{ K}$

## Sample Visualizations
All the plots are available [here](plots)  
  
![Radius Distribution Histogram](plots/planet_radii_distribution.png)

## Key Findings
Our analysis of multiplanetary systems across different spectral types (M, K, G, F) confirms the presence of the **Radius Valley**. 
* **Observation:** M-type systems show a distinct atmospheric loss sensitivity compared to G-type stars.
* **Metric:** The calculated $\Delta R / \Delta \log(S)$ suggests that photoevaporation is likely the dominant mechanism for atmospheric stripping in short-period planets orbiting high-temperature hosts.

## Conclusion
The results indicate a clear bimodal distribution across all spectral types. The $\Delta R / \Delta \log S$ metric shows varying sensitivities to stellar irradiation, suggesting that photoevaporation plays a dominant role in shaping the planetary systems of higher-temperature stars.

**Author:** Yashasvee Taiwade  
**Context:** Research Internship Project (TIFR)
