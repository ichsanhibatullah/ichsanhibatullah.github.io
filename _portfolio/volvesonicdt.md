---
title: "Synthetic Compressional Sonic Log (DT) Generation using Machine Learning in the Volve Field"
excerpt: "I. Hibatullah<br><br>Predicting crucial well logs in the Volve Field using Machine Learning, focusing on highly accurate synthetic DT log generation in Dataiku DSS." #<br><br><img src='/images/volve_dt_ml/image_cbbbdc.png' width='600' height='450'>
collection: portfolio
---

<img src="https://user-images.githubusercontent.com/51282928/140687832-381c13a0-7a2b-495c-8817-eee5064c11b5.png" align="left" width="30" height="30">[Read this full work](https://python.plainenglish.io/synthetic-compressional-sonic-log-dt-generation-using-machine-learning-in-the-volve-field-a8d4cf8c4d7c) in Python Plain English

This project focuses on leveraging Machine Learning to generate synthetic Compressional Sonic Logs (DT) in the challenging yet data-rich Volve Field. The goal was to accurately predict missing DT log data, a crucial parameter for comprehensive subsurface characterization, using readily available well log measurements.

### 📝 Project Overview

Compressional Sonic Logs (DT) are indispensable for both Petrophysicists and Geophysicists, providing critical insights into porosity, lithology, fluid content, and enabling accurate seismic interpretation and modeling. However, these logs are not always available for every well due to various operational or cost constraints. This project aimed to bridge these data gaps using a robust, data-driven approach.

I utilized the publicly available Volve Field dataset, a unique opportunity to apply advanced data science techniques to a real-world oil and gas challenge. My workflow, built end-to-end within **Dataiku DSS** and leveraging its AutoML capabilities, streamlined the process from raw data ingestion to model deployment and visualization.

### ⚙️ Methodology 
The project was structured into three main phases:

1.  **Pre-training:**
    * Imported and stacked individual well datasets, ensuring proper well identification for visualization.
    * Conducted comprehensive Exploratory Data Analysis (EDA), including correlation matrices and bivariate analysis, to understand data relationships and identify potential outliers.
    * Performed data cleaning, defining outliers based on statistical methods (1.5 IQR) combined with geophysical domain expertise.
    * Split the cleaned data into training and blind testing sets, and create dataset of well with no DT for prediction.

2.  **Training:**
    * Developed predictive models using Dataiku's AutoML Prediction feature, with **Root Mean Square Error (RMSE)** as the primary target metric, prioritizing magnitude accuracy.
    * Conducted three case training runs, varying the input features (4, 5, and 6 features: GR, CALI, PEF, RT, NPHI, RHOB) to assess their impact on model performance.
    * Evaluated three algorithms: Random Forest, XGBoost, and LightGBM.

3.  **Post-training:**
    * Deployed the best-performing model (Random Forest) to predict DT logs for wells with absent sonic data.
    * Generated custom visualizations using a Python-based custom plugin to display synthetic DT logs alongside available input logs.

### ✅ Key Results

This experiment demonstrated highly promising results, validating the effectiveness of Machine Learning for synthetic DT log generation:

* **Superior Model Performance:** The **Random Forest** algorithm consistently outperformed XGBoost and LightGBM across all feature sets, proving to be the most accurate and reliable model for this specific application.

    <p align="center">
    <img src="https://miro.medium.com/v2/resize:fit:1100/format:webp/1*R5inL2Xux5n_gTso9ZmVzg.png" alt="Model Performance Table" width="auto" height="auto"/>
    </p>

* **Optimal Feature Subset:** Notably, even with a concise set of four features (Gamma Ray, Resistivity, Neutron Porosity, and Density), the Random Forest model achieved excellent accuracy, with an RMSE of **4.09 US/F** and MAPE of **3.3%** on blind test. This indicates that a basic input can still yield robust predictions, **potentially optimizing data acquisition strategies**.

* **Feature Importance:** Across all models, Neutron Porosity (NPHI) consistently ranked as the most important feature, followed by Density (RHOB), Gamma Ray (GR), and Resistivity (RT). 

    <p align="center">
    <img src="https://miro.medium.com/v2/resize:fit:1100/format:webp/1*APztRZLYhaBvuDXSd1CVnQ.png" alt="Feature Importance" width="450" height="auto"/>
    </p>
<!-- This aligns well with petrophysical understanding of their influence on acoustic properties. -->

* **Visual Validation:** The synthetic DT logs for both blind wells (wells with existing DT logs not used in training) and wells with no DT data showed remarkable agreement with expected geological trends and with actual measured DT logs. The model successfully captured major geological features, confirming the physical plausibility of the predictions. The visual comparison also highlighted minimal differences in prediction quality when comparing models trained with 4, 5, or 6 features, further reinforcing the efficiency of the 4-feature model.

    <div align="center">
    <img src="https://miro.medium.com/v2/resize:fit:2000/format:webp/1*mRAgdc-svLyqum18ciWzxQ.png" alt="DT prediction for well 15/9-F-11 A as blind well" width="700" height="auto"/>
    </div>
    <p align="center">DT prediction for well 15/9-F-11 A as blind well</p>

    <div align="center">
    <img src="https://miro.medium.com/v2/resize:fit:2000/format:webp/1*kNUfpcROV-BARTC6c9LXow.png" alt="DT prediction for well 15/9-F-1 C as well without DT log" width="700" height="auto"/>
    </div>
    <p align="center">DT prediction for well 15/9-F-1 C as well without DT log</p>


This project not only delivered accurate synthetic DT logs for absent data or critical data gaps, but also underscored the **transformative potential of integrating robust ML techniques within geoscience domain knowledge**.