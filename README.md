# Margin of Error and Household Income  
### Lake County, IL — ACS 2022 Decision-Quality Reality Check

Tract-level median household income (MHI) from the American Community Survey (ACS) is widely used for high-stakes decisions across sectors. This brief shows where ACS tract MHI is reliable—and where large or missing margins of error (MOE) make decisions statistically fragile. The focus area is Lake County, Illinois, using ACS 5-year 2022 data.

**Full report (PDF):**  
- `/report/margin-of-error-household-income-lake-county.pdf`

---

## Key Findings
- **ACS MHI is a strong decision signal—until uncertainty gets large.** Most Lake County tracts have typical MOE levels, meaning comparisons and rankings are generally stable.  
- **A small set of tracts show exceptionally high uncertainty.** Top-decile MOE tracts represent “fragile signal” areas where tract income estimates can be far from the true value.  
- **Uncertainty can change threshold-based classifications.** Some tracts shift into a borderline category once confidence intervals are considered, meaning eligibility or ranks can flip.  
- **Statewide benchmarking reveals clear high-need pockets—but also a risk zone.** Lake County is affluent overall, yet several tracts meet bottom-quartile statewide need with high confidence, while nearby tracts are MOE-sensitive.  
- **The capstone output is a practical validation checklist.** Borderline tracts are where secondary validation should be required before using tract MHI as a standalone decision input.

---

## Methods in Brief
Using 2022 ACS 5-year tract median household income estimates (B19013) for Lake County, margins of error at 90% confidence were converted into confidence intervals and coefficients of variation. Tracts were mapped by MOE magnitude, then evaluated against both county-median and statewide bottom-quartile thresholds. Tracts whose confidence intervals fell fully below/above thresholds were labeled high-confidence eligible or ineligible; confidence intervals crossing thresholds were labeled borderline/MOE-sensitive. Outputs were exported to QGIS for final cartography. Intervals shown are 90% ACS confidence intervals (estimate ± MOE; MOE = 1.645 × standard error).

---

## Figures

### Map 1 — Tracts with Highest ACS MHI Uncertainty
Tracts in the top 10% of MOE values are highlighted to show where tract-level income estimates are least precise.  
![Map 1](/figures/map_1_highest_moe.png)

### Map 2 — County Threshold Confidence
Shows how MOE can flip tract classification around a countywide income threshold.  
![Map 2](/figures/map_2_county_threshold.png)

### Map 3 — Statewide Benchmark Confidence
Benchmarks Lake County tracts against the Illinois statewide income distribution while incorporating MOE.  
![Map 3](/figures/map_3_statewide_benchmark.png)

### Chart — Borderline Tracts with Confidence Intervals
Dot plot of MOE-sensitive tracts; each interval crosses the statewide cutoff, indicating decision-sensitive classifications.  
![Dot plot](/figures/chart_borderline_dotplot.png)

### Map 4 — Capstone Borderline Context Map
Highlights tracts where MHI uncertainty is most likely to shift decisions; these areas require secondary validation.  
![Map 4](/figures/map_4_capstone_borderline_context.png)

---

## Attribution / Data & Tools
This brief uses tract-level median household income estimates and associated 90% margins of error from the U.S. Census Bureau’s American Community Survey (ACS) 5-year 2022 release, accessed via the Census API. Census tract and place boundaries were drawn from TIGER/Line shapefiles. Data processing, uncertainty calculations, and classification of high-uncertainty and MOE-sensitive tracts were completed in R using the tidycensus, tidyverse (dplyr, ggplot2, readr), sf, tigris, and scales packages. Cartography, labeling, and final figure layouts were produced in QGIS. Basemap context is provided by OpenStreetMap contributors under the Open Database License (ODbL).
