---
title: "Earthquake Data Analyzer - Exploring earthquake catalog dataset patterns using Python"
date: 2025-05-31
excerpt: "I. Hibatullah<br><br>An open-source Python project for extracting insights from earthquake datasets through statistical calculations summary." 
#<br><img src='/images/earthquakedataanalysis/amplitude.png' width='600' height=500>
collection: portfolio
---

👨‍💻 [**Earthquake Data Analyzer**](https://github.com/ichsanhibatullah/earthquake-data-analyzer) is a Python-based project I developed as part of my continued exploration into geophysical data processing. This initiative blends my geophysics background with coding skills I began sharpening through Code In Place 5 (CIP) public course from Stanford University, where I learned the basics and theory of programming.

### 🔁 From Theory to Application

Coming from a geophysics background, I’ve always been fascinated by how physical principles manifest in real-world phenomena like earthquakes, gravity, and magnetic anomalies. Indonesia—my home country—sits on the Pacific Ring of Fire and experiences thousands of earthquakes yearly. This rich but complex dataset presents a unique opportunity: if processed correctly, it can reveal temporal-spatial patterns, help monitor seismic risks, and support policy planning.

So, when I set out to build a final project on Code In Place 5 course, I want to reflect on both my academic foundation and basic practical programming skills that I just learned, I chose to develop **Earthquake Data Analyzer**—a clean, interactive, and modular tool that makes earthquake catalog dataset more accessible for geoscientific interpretation and reveal the hidden patterns of this dataset.

This tool is especially useful in Indonesia, where earthquakes are frequent but the data often sits unused in CSV archives. By providing a way to **analyze** patterns—like whether a region is becoming more active, or if deep-focus events are increasing—we can bridge the gap between raw data and real-world insights.

### ⚙️ What Does It Do?

<p align="center">
  <iframe width="500" height="300" src="https://www.youtube.com/embed/_rQDH7ZQ18Y?si=QgBTlfVIvRGyykHD" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
</p>

`Earthquake Data Analyzer` is designed for **seismology beginners and analysts** who want to explore and understand earthquake catalogs without needing deep coding knowledge. It includes the following core features:

#### 🗃️ Dataset Handling
- Built-in preprocessing functions for raw CSV earthquake data.
- Custom filters by magnitude, depth, or region.
- Compatible with IRIS IEB (Interactive Earthquake Browser) export format.

#### 🧠 Statistical Insights
- Monthly and annual earthquake frequency tracking.
- Highlighting high-magnitude outliers and unusual clusters.

### 📌 Technologies Used
- `Pandas` for data processing and analysis

### 💡 Future Plans
- Create an interactive visualization using `Matplotlib` & `Seaborn`.
- Create spatial mapping visualization using `GeoPandas` & `Shapely`.
- Deploy an interactive web-based app using `Streamlit`.
- Add support for real-time earthquake feeds (e.g., USGS or BMKG API).
- Integrate basic machine learning for event clustering or forecasting trends.

### 🧾 Citation
If you use this tool or its components in your research or classroom, please consider citing the repository:

> Ichsan Hibatullah. (2024). *Earthquake Data Analyzer: Visualizing Seismic Patterns with Python.* GitHub. https://github.com/ichsanhibatullah/earthquake-data-analyzer

### 🔗 Links
- 📂 GitHub Repository: [Earthquake Data Analyzer](https://github.com/ichsanhibatullah/earthquake-data-analyzer)  
- ▶️ YouTube Demo: [Watch the demo](https://www.youtube.com/watch?v=_rQDH7ZQ18Y)

Thanks for reading! Earthquakes may be unpredictable, but my tools for understanding them don’t have to be.