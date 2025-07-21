---
title: "Machine Learning-based synthetic shear sonic log (DTS) generation: Volve Field case study"
date: 2025-07-21
excerpt: "I. Hibatullah<br><br>Predicting DTS log in the Volve Field using Machine Learning in Dataiku DSS." #<br><br><img src='/images/volve_dt_ml/image_cbbbdc.png' width='600' height='450'>
collection: portfolio
---

<img src="https://user-images.githubusercontent.com/51282928/140687832-381c13a0-7a2b-495c-8817-eee5064c11b5.png" align="left" width="30" height="30">[Read this full work](https://ichsanhibatullah.medium.com/machine-learning-based-synthetic-shear-sonic-log-dts-generation-volve-field-case-study-b795ef6808d9) on Medium

This project extends my previous work on synthetic Compressional Sonic (DT) log generation, now focusing on predicting the Shear Sonic Log (DTS) in the Volve Field using Machine Learning. Accurately deriving DTS is critical for advanced subsurface characterization, particularly for geomechanics, fluid characterization, and advanced geophysical technique like AVO analysis, especially in wells where such data is absent.

### 📝 Project Overview

The Volve Field's publicly available dataset provides an invaluable platform for innovating, developing, and validating data-driven solutions in geoscience. While DT logs are essential, DTS logs offer complementary, yet distinct, information about a formation's elastic properties (P-wave vs. S-wave velocity). The Vp/Vs ratio derived from these logs is a highly sensitive indicator of fluid content (especially gas), lithology, and stress, making this log indispensable for:

* **Fluid Characterization:** Differentiating between gas, oil, and water.
* **Geomechanics Analysis:** Understanding rock strength, stress regimes, and wellbore stability.
* **Seismic Analysis:** Enabling accurate AVO (Amplitude Versus Offset) analysis and anisotropic seismic modeling.

The challenge lies in the frequent absence of DTS logs due to operational limitations or acquisition costs. This project addresses this issues by creating a predictive model to fill these data gaps.

### ⚙️ Methodology 
The methodology for DTS prediction largely mirrored the successful workflow established for DT logs, implemented end-to-end within **Dataiku DSS**. The project was structured into three main phases:

1.  **Pre-train:** 
    * Data from the Volve Field (24 wells total, focusing on a subset of 9 wells) was imported, cleaned, and prepared, this involved stacking individual well logs.
    * Performed comprehensive Exploratory Data Analysis (EDA) including correlation and bivariate analysis.
    * Performed data cleaning: outlier removal based on statistical methods combined with geophysical plausibility.
    * Partitioned data into training, blind testing, and prediction sets for wells lacking DTS.

2.  **Training:** 
    * Predictive models were built using Dataiku's AutoML Prediction feature. Root Mean Square Error (RMSE) was chosen as the primary metric, ensuring physically meaningful error quantification in microseconds per foot.
    * **Features:** Multiple training runs were conducted with varying input feature sets, ranging from 4 to 7 logs (Gamma Ray, Caliper, Photoelectric Factor, Resistivity, Neutron Porosity, Density, and Compressional Sonic).
    * **Algorithms:** Random Forest, XGBoost, and LightGBM were evaluated for their performance.

3.  **Post-training:**
    * The best-performing model was deployed to generate synthetic DTS logs for wells lacking this data.
    * Custom Python plugin facilitated the visualization of the predicted DTS logs alongside available input logs for prediction QC and interpretation.

### ✅ Key Results

The training and blind testing revealed highly engaging results for synthetic DTS log generation:

* **Superior Model Performance:** The **Random Forest** algorithm consistently outperformed other models (XGBoost and LightGBM), proving to be the most robust and accurate for DTS prediction across all feature combinations.

<p align="center">
  <img src="https://miro.medium.com/v2/resize:fit:640/format:webp/1*6dxlVaftLPBBjNcAxo9elw.png" alt="Model Performance Table" width="auto" height="400"/>
</p>

* **Optimal Feature Subset:** The Random Forest model, when utilizing with only **5-feature set** (GR, RT, NPHI, RHOB, DT), the model achieved exceptional metrics: **7.639 US/F on RMSE** and **3.6% on MAPE**. This demonstrates high accuracy and low prediction error for synthetic DTS logs.

<p align="center">
  <img src="https://miro.medium.com/v2/resize:fit:2000/format:webp/1*vBrT9d0vLLT868EJnONYEg.png" alt="Complete Model Evaluation Table" width="auto" height="auto"/>
</p>

* **Critical Role of DT:** The **Compressional Sonic Log (DT)** emerged as the most important feature (39% contribution) in predicting DTS. This highlights the strong geological and physical coupling between P-wave and S-wave velocities, emphasizing the value of leveraging available DT data for DTS prediction. Other key features included PEF (17%), NPHI (13%), and RHOB (11%).

<p align="center">
  <img src="https://miro.medium.com/v2/resize:fit:1100/format:webp/1*5J9BfJM7hg8NtHojZ4Wu1g.png" alt="Feature Importance" width="450" height="auto"/>
</p>

* **Visual Validation:** Predictions for blind wells and wells lacking DTS logs showed strong alignment with actual logs for blind well and exhibited excellent geological plausibility. The synthetic DTS curves captured key formation changes accurately, visually confirming the model's ability to generalize to unseen data.

<p align="center">
  <img src="https://miro.medium.com/v2/resize:fit:2000/format:webp/1*F1ExOeJasCVZa8XyXXOf0w.png" alt="DTS prediction for well 15/9-F-1 B as blind well" width="700" height="auto"/>
  <br>
  <caption align="center">DTS prediction for well 15/9-F-1 B as blind well</caption>
</p>

<p align="center">
  <img src="https://miro.medium.com/v2/resize:fit:2000/format:webp/1*8hkFDBSXIYl9mpD3Ho1ZbQ.png" alt="DTS prediction for well 15/9-F-1 as well without DTS log" width="700" height="auto"/>
  <br>
  <caption align="center">DTS prediction for well 15/9-F-1 as well without DTS log</caption>
</p>

This project successfully demonstrated the power of Machine Learning, particularly with Random Forest models, in generating accurate and geologically consistent synthetic DTS logs. By utilizing the comprehensive Volve Field dataset and integrating DT as a critical input, a robust solution created for **filling data gaps**, **enhancing subsurface characterization**, and **enabling more informed decisions in hydrocarbon exploration and development**.