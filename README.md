# 05_search_for_methane_on_mars_TES_EMIRS_instrument
This folder contains programs used to analyze the EMIRS spectra + TES spectra to search for methane on Mars and understand if diurnal or seasonal variations exist

# ABSTRACT

The detection of methane on Mars, ranging from a few ppbv to ∼100 ppbv, and contrary reports of non-detection have intrigued the community for more than two decades. Reports of detection with Earth-based observations, from Martian orbit, and on the surface have been challenged on theoretical grounds, on the quality of the signal, and on the interpretation of results.  

The highly sensitive **ExoMars TGO’s ACS and NOMAD instruments** put an upper limit of a few pptv, several orders of magnitude below what was reported earlier. However, the ExoMars observations are made at fixed local times and are not sensitive to the atmosphere near the surface.  

The **Emirates Mars Mission (EMM)** provides near-global coverage of the planet every 9 sols. We use data from the **EMIRS infrared spectrometer** on board EMM during Mars Year 36 and archival data of **MGS/TES** to search for absorption at the C-H bending mode of methane at 1306 cm⁻¹.  

We report:
- An upper limit of **4 ppbv (day)** and **10 ppbv (night)** for methane detection using EMM/EMIRS.  
- An upper limit of **2 ppbv** for methane detection using MGS/TES.  

These results are consistent with the latest **MSL** and **TGO** findings. Future observations with EMM will further refine these constraints.

# Draft Version: September 3, 2025

**Typeset using LaTeX default style in AASTeX7.0.1**

## Title
**A Search for Methane on Mars with EMM/EMIRS and MGS/TES**

### Authors
- Dimitra Atri¹  
- Pallavi Krishna¹  
- Dattaraj B. Dhuri¹  
- Jeongin Lee¹  
- Gopika Krishnan¹  
- Michael D. Smith²  

¹ Center for Astrophysics and Space Science, New York University Abu Dhabi  
² NASA Goddard Space Flight Center  

---

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
