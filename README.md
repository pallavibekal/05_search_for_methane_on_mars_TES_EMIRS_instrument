# 05_search_for_methane_on_mars_TES_EMIRS_instrument
This folder contains programs used to analyze the EMIRS spectra + TES spectra to search for methane on Mars and understand if diurnal or seasonal variations exist


## ABSTRACT
The detection of methane on Mars, ranging from a few ppbv to ∼100 ppbv, and contrary reports of non-detection have intrigued the community for more than two decades. Reports of detection with Earth-based observations, from Martian orbit, and from the surface have been challenged on theoretical grounds, on the quality of the signal, and on interpretation of results.  

The highly sensitive **ExoMars TGO’s ACS and NOMAD instruments** place an upper limit of a few pptv, several orders of magnitude below earlier reports. However, ExoMars observations are made at fixed local times and are not sensitive to the atmosphere near the surface.  

The **Emirates Mars Mission (EMM)** provides near-global coverage of the planet every 9 sols. We use data from the **EMIRS infrared spectrometer** on board EMM during Mars Year 36 and archival data of **MGS/TES** to search for absorption at the C–H bending mode of methane at 1306 cm⁻¹.  

We report:  
- **4 ppbv (day)** and **10 ppbv (night)** upper limits for methane detection using **EMM/EMIRS**.  
- **2 ppbv** upper limit for methane detection using **MGS/TES**.  

These findings are consistent with the latest **MSL** and **TGO** results. Future observations with EMM will further refine these constraints.  

---

## Keywords
- **Exoplanet Atmospheres (2021)**  
- **Planetary Atmospheres (1244)**  
- **Mars (1007)**  
- **Solar System Terrestrial Planets (797)**  

---

## 1. INTRODUCTION
With growing evidence of abundant liquid water on the surface of ancient Mars, it is reasonable to assume that the planet once had conditions hospitable for life as we know it (C. P. McKay, 1997). The search for extinct or extant life on the planet is of great interest to planetary science and the broader community.  

Remote sensing observations are a powerful tool to search for potential **biosignature gases**, such as methane, which on Earth is largely produced biologically. On Mars, methane could possibly originate from **subsurface microbes** (e.g., methanogens), since surface conditions are too harsh. However, several **non-biotic sources** exist, including:  

- Serpentinization of olivine  
- Geothermal sources  
- Release from regolith  
- Basalt erosion  
- Impact metamorphism of surface organics  
- Decay of organics in solution  
- Water-rock interactions  
- Cometary impacts  
- Interplanetary Dust Particles (IDPs)  
- Release from clathrates  
- Thermogenesis of biotic or abiotic material  

These mechanisms are well studied (see Y. L. Yung et al., 2018, for details).  

### Previous Detections
Over the past 25 years, multiple studies have attempted to measure methane in the Martian atmosphere via **ground-based observatories, orbiters, and in-situ detection**:  

- **Ground-based detections**:  
  - Canada-France-Hawaii telescope: 10 ± 3 ppbv (V. A. Krasnopolsky et al., 2004)  
  - Keck-2 and NASA-IRTF: ~6 ppbv global average with localized peaks at ~33 ppbv and ~45 ppbv (M. J. Mumma et al., 2009)  

- **Orbital detections**:  
  - MEX/PFS: 10 ± 5 ppbv global average (Formisano et al., 2005), revised to 15 ± 5 ppbv (Geminale et al., 2011)  
  - MGS/TES: 5 ± 2 ppbv and 33 ± 9 ppbv (Fonti & Marzo, 2010)  

These results suggested methane appears **sporadically**, both spatially and temporally.  

### Controversies
Many of these detections have been disputed:  
- Possible **false positives** from nearby CO₂ and H₂O lines (Zahnle et al., 2011).  
- Ambiguities due to **instrument sensitivity/resolution**.  
- Later analyses of MGS/TES after stricter cleaning led to **non-detections** (Fonti et al., 2015).  

More recent studies reported **much lower methane values**, including:  
- MSL/TLS-SAM: seasonal variation at a few ppbv (Webster et al., 2015), later revised to <1 ppbv (Webster et al., 2021).  
- ExoMars/TGO (ACS, NOMAD): consistent **non-detections**, with upper limits of ~20 pptv (Korablev et al., 2018; Montmessin et al., 2021).  

These discrepancies raise critical questions:  
- Why does methane appear to vary spatially and temporally?  
- What mechanism could rapidly destroy or sequester methane, despite known chemistry suggesting it should persist for centuries?  

---

## 2. Methodology
### 2.1 Objective and Approach

The Emirates Mars Mission (EMM) provides an extensive dataset of spectra, making it well-suited for statistical clustering techniques. The method introduced by Fonti & Marzo (2010) has proven effective for large datasets, as it improves the signal-to-noise ratio through data averaging.

This approach has been validated and applied across multiple contexts:

Synthetic data → Liuzzi et al. (2014)

Planetary remote sensing spectra → Marzo et al. (2008)

Spectral classification maps of Mars (CRISM/MRO) → Pletl et al. (2023)

Surface classification of Mercury & the Moon → Taisei et al. (2024)

A detailed explanation of this clustering method, particularly as applied to TES spectra, can be found in Marzo et al. (2008).

K-means Clustering

The clustering procedure employs the k-means algorithm, which minimizes the within-cluster sum of squares:

<img width="949" height="314" alt="image" src="https://github.com/user-attachments/assets/ba708f73-95a3-47ac-877d-0a600c0735c8" />


### Limitations of K-means

**Noise sensitivity** → noisy data can cause misclassification or poor centroid selection (Jolion & Rosenfeld, 1989).

**Spectral dilution** → clustering over large regions can weaken or distort narrow methane absorption features (Fonti et al., 2015).

**Choice of k** → the number of clusters must be specified a priori, which is non-trivial (Turner et al., 2018).

**Refinements by Fonti et al. (2015)**

To address these limitations, Fonti et al. (2015) refined the methodology by:

Applying rigorous noise reduction for TES infrared spectra.

Focusing on narrow spectral regions to better isolate methane absorption.

Keeping the same number of clusters as in 2010, ensuring comparability while acknowledging the lack of clear intrinsic clustering.

These refinements led to earlier methane detections being deemed inconclusive, but the methods remain highly relevant for emissivity data. Importantly, the EMIRS spectrometer on EMM shares direct lineage with TES (Smith et al., 2022), making these techniques directly applicable.

**Application in This Study**

Applied refined clustering techniques to EMM/EMIRS data.

Reanalyzed the original Fonti & Marzo (2010) dataset, which was not revisited in 2015.

Validation step → replicated TES analysis at Ls = 180° (Fonti et al., 2015).

Extended study → applied the method to Ls = 0°, 90°, and 270° to test for seasonal variation in TES data.

<img width="1056" height="330" alt="image" src="https://github.com/user-attachments/assets/4d9e3ffb-53a6-4c72-8fb0-2b261d51f666" />

<img width="1060" height="431" alt="image" src="https://github.com/user-attachments/assets/a185a64b-1a66-4c5d-a937-2c3732c6658f" />

<img width="1046" height="580" alt="image" src="https://github.com/user-attachments/assets/eef71488-1012-4da0-a1ea-e84e6639f6e7" />

<img width="1035" height="525" alt="image" src="https://github.com/user-attachments/assets/ca9b9068-45a0-4a2b-b1ee-642b3d747807" />

<img width="1043" height="387" alt="image" src="https://github.com/user-attachments/assets/9bd621cc-359f-476a-9ad4-7f8c9cb679ef" />

<img width="1033" height="456" alt="image" src="https://github.com/user-attachments/assets/db9eda84-ebbb-47a4-b8b7-0a0389370150" />

<img width="1043" height="586" alt="image" src="https://github.com/user-attachments/assets/4b2b5da7-3074-410e-8469-8d09353c021c" /> 

<img width="1035" height="310" alt="image" src="https://github.com/user-attachments/assets/ec1839bf-3cbc-4cfc-9eae-fd2ef9d6d91a" />

<img width="1040" height="490" alt="image" src="https://github.com/user-attachments/assets/93dadb41-3e43-4d78-8ec9-2103a8d665bb" />

 <img width="1046" height="603" alt="image" src="https://github.com/user-attachments/assets/4b337439-641b-4d28-802a-f930b5006516" />

<img width="1055" height="270" alt="image" src="https://github.com/user-attachments/assets/d2ce4548-5a87-415d-be37-eb2e1a1ee351" />

<img width="1033" height="806" alt="image" src="https://github.com/user-attachments/assets/0c45e4ee-eda9-4bae-a997-ba70e2884107" />

<img width="1098" height="491" alt="image" src="https://github.com/user-attachments/assets/c152f9b1-a36e-4b63-8cd4-4855f6dc7d9e" />

<img width="1096" height="579" alt="image" src="https://github.com/user-attachments/assets/df4691b5-cae7-4849-b3e8-8c89195679a9" />

<img width="1075" height="415" alt="image" src="https://github.com/user-attachments/assets/e615de2d-0c78-448f-8d6b-46b618af9245" />

<img width="1075" height="415" alt="image" src="https://github.com/user-attachments/assets/d1930e89-6b5d-4487-81e3-e24f22b2755a" />

<img width="1088" height="622" alt="image" src="https://github.com/user-attachments/assets/13d03882-c66b-464d-a787-19927b65ad5b" />

<img width="1077" height="523" alt="image" src="https://github.com/user-attachments/assets/bd3709eb-116a-4d9a-aeaa-09d565289b48" />

<img width="1072" height="320" alt="image" src="https://github.com/user-attachments/assets/507b0c93-d5d1-460a-9cdc-cb09fbd72bd9" />

