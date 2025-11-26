# STATS C173 — Geostatistics Final Project(s): Soil Heavy Metals & Recreated Wildfire FRP

Two versions of the final project:
- **Version 1 (original):** Spatial analysis of **soil heavy metals** (cadmium target) with variograms, model fitting, and kriging. 
- **Version 2 (recreated with a different dataset):** Geostatistical analysis of **NASA FIRMS wildfire FRP** in California (MODIS; 2025-01-06 to 2025-01-24), deduplicated to **755 unique points**; EDA, variograms (classical/robust/directional), and interpolation attempts. 

---

## What’s here
- `c173_fp_Sathasivam_Daren.Rmd` / `c173_fp_Sathasivam_Daren.pdf` — **Soil metals** pipeline: histograms/ECDFs, bubble & H-scatterplots, empirical semivariograms (classical + robust), spherical/exponential/gaussian fits (equal/Cressie/npairs weights), **IDW** prediction grid, and **kriging** setups. See strong cross-metal correlations (e.g., Cd–Cu ≈ 0.93) and spherical fits with practical ranges around ~900–1,100 units. 
- `c173_fp2.Rmd` / `c173_fp2.pdf` — **Wildfire FRP** pipeline: CA subset (long/lat bounds), day/night factor, FRP + thermal predictors (brightness, bright_t31), **755×9** after dedupe, bubble & H-scatterplots, classical/robust and **directional** semivariograms, and model fits; includes mapping, EDA, and interpolation attempts.

> Note: The second project is a full **recreation using a different dataset** to stress-test the same geostatistical workflow on a new problem (FRP instead of soil Cd). 

---

## Methods (shared themes)
- **EDA:** histograms, ECDFs, boxplots, scatterplots, descriptive stats.  
- **Spatial visuals:** bubble maps and **H-scatterplots** to inspect local correlation.  
- **Semivariograms:** classical & robust; weighted fits (npairs/Cressie/equal); **spherical**, **exponential**, **gaussian** comparisons; **directional** variograms for anisotropy (FRP). 
- **Interpolation:** **IDW** grids; **ordinary kriging** setups based on fitted models (soil metals end-to-end; FRP includes fit/warning diagnostics on short temporal window). 

---

## Data notes
- **Soil metals** come from the class dataset (x, y, cadmium, copper, lead, zinc). Keep raw links/reads in the Rmd and avoid committing data files. 
- **Wildfire FRP (FIRMS / MODIS):** CA filter, 2025-01-06 to 2025-01-24; deduplicated by coordinates; variables include FRP, brightness, bright_t31, confidence, scan, day/night, date. Raw CSV not included; see Rmd for expected schema/fields.

---