---
title: "lfpspy - A Python package for low-frequency passive seismic (LFPS) method processing"
date: 2024-08-02
excerpt: "I. Hibatullah¹, Sudarmaji¹, N.N. Hamidah²<br>¹Department of Physics, Faculty of Mathematics and Natural Sciences, Gadjah Mada University, Yogyakarta, Indonesia<br>²Centre for Geological Survey, Geological Agency of Indonesia, Ministry of Energy and Mineral Resources<br><br>Geophysics processing package of Low-Frequency Passive Seismic (LFPS) Method using Python programming language." #<br><img src='/images/lfpspy/Station 38-Spectral Analysis.png' width='600' height=500>
collection: portfolio
---

👨‍💻 [**lfpspy**](https://github.com/ichsanhibatullah/lfpspy) is an open-source Python package I developed in 2024 to process Low-Frequency Passive Seismic (LFPS) ambient-noise data. It was the primary output of my undergraduate thesis project in Geophysics at Gadjah Mada University, born out of both necessity and curiosity.

### 🔁 Background  
This journey began with my desire to apply LFPS methods to map subsurface hydrocarbon potential. However, early in the research, I ran into a major obstacle—there were no open-source tools available to handle LFPS data. Unlike conventional passive seismic processing (e.g., for HVSR or microtremor data), LFPS posed unique challenges in terms of preprocessing, spectral analysis, and window-quality control. I realized I’d either have to abandon the method or build the tools myself—so I chose the latter.

My inspiration came from a paper by Cox et al. (2020), which proposed a [**frequency-domain window-rejection algorithm**](https://academic.oup.com/gji/article/221/3/2170/5805192) for improving H/V spectral ratio estimates by removing noisy or inconsistent windows before averaging, which they implement it on [hvsrpy](https://github.com/jpvantassel/hvsrpy). While their method had been widely used in microtremor and earthquake engineering studies, it hadn’t yet been applied to LFPS data. I saw this as an opportunity to innovate: I designed `lfpspy` to adapt and extend Cox et al.’s method specifically for the lower frequency bands (0.1–1.0 Hz) typical of LFPS surveys.

The project culminated in a full case study on the Majalengka Sub-basin, Indonesia. Using LFPS recordings acquired from a short-period seismic station, I processed the data through `lfpspy`, computed stable V/H curves (VHSR), and identified dominant low-frequency peaks associated with soft sedimentary layers. I then validated these results using polarization attribute and cross-compared them with gravity anomaly maps from previous studies. The results were promising—showing that LFPS, when combined with careful spectral QC and directional analysis, could serve as a cost-effective method for preliminary subsurface assessment.

### ⚙️ Methodology 
The core of `lfpspy` consists of:
- **Spectrum Analysis**: Computes Power Spectral Density on the vertical component (PSD‑Z) and Horizontal‑to‑Vertical Spectral Ratio (H/V) to identify low‑frequency anomalies associated with reservoir rock.  

<p align="center">
  <img src="https://github.com/ichsanhibatullah/ichsanhibatullah.github.io/blob/master/images/lfpspy/Station%2038-Spectral%20Analysis.png?raw=true" alt="Spectral Analysis" width="600" height="auto"/>
</p>

- **Window‑Rejection Algorithm**: Implements Cox et al.’s, which uses statistical thresholds in the frequency domain to reject contaminated windows before averaging, boosting signal‑to‑noise robustness and significantly improving the clarity of low-frequency V/H peaks.

<p align="center">
  <img src="https://github.com/ichsanhibatullah/ichsanhibatullah.github.io/blob/master/images/lfpspy/FDWR%20modified%20from%20Cox.png?raw=true" alt="FDWR Algorithm" width="500" height="auto"/>
  <br>
  <caption align="center">Frequency-domain Window-rejection Algorithm Flowchart (modified from Cox et al.)</caption>
</p>

- **Polarization Analysis**: Performs Principal Component Analysis (PCA) to evaluate particle motion in sliding time windows. This yields dip, azimuth, rectilinearity, and eigenvalue ratios—important for distinguishing noise from signal and validating spectral peaks.

<p align="center">
  <img src="https://github.com/ichsanhibatullah/ichsanhibatullah.github.io/blob/master/images/lfpspy/Station%2038-Polarization%20Analysis.png?raw=true" alt="Polarization Analysis" width="400" height="300"/>
</p>

### 🧾 Citation
- Cox, B. R., Cheng, T., Vantassel, J. P., & Manuel, L. (2020). "A statistical representation and frequency-domain window-rejection algorithm for single-station HVSR measurements. Geophysical Journal International, 221(3), 2170–2183. https://doi.org/10.1093/gji/ggaa119
- Joseph Vantassel. (2020). jpvantassel/hvsrpy: latest (Concept). Zenodo. http://doi.org/10.5281/zenodo.3666956