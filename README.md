# FEMA National Risk Index (NRI) – California vs Other U.S. States

#### Author: Marie Tolteca, MEDS Student

#### Date: 02/17/2026

## Project Overview

This project has two parts. First, it explores how **FEMA National Risk Index (NRI) scores for counties in California compare to counties in other U.S. states**, visualizing the distribution of county-level NRI scores with California highlighted, in `HW2.qmd`. Second, it examines how **climate hazard risk exposure differs across racial and ethnic groups in California counties** by combining FEMA NRI scores with U.S. Census demographic data to calculate population-weighted mean risk percentiles for each racial and ethnic group, in `HW3.qmd`.

The final visualization in `HW2.qmd` uses **boxplots with overlaid jittered points** to show both summary statistics and individual county-level variation. In `HW3.qmd` the final visualization uses *lollipop plot* to show that all racial and ethnic groups in California face extremely high climate risk (98.7%-99.3% percentile), with Asian, Hispanic or Latino, and Black populations experiencing slightly higher exposure within this narrow range.

## Repository Structure
```
.
├── data
│  └── National_Risk_Index_Counties_807384124455672111.csv
│  └── ACS-1yr-2023-county-race-ethnicity.csv
├── eds240-nri-acs-viz.Rproj
├── fema_nri_files
│   ├── figure-html
│   │   ├── unnamed-chunk-4-1.png
│   │   └── unnamed-chunk-5-1.png
├── fema_nri.html
├── fema_nri.qmd
├── HW2.qmd
├── HW3.qmd
└── README.md
```

------------------------------------------------------------------------

## Data Source

-   **Source:** FEMA Resilience Analysis and Planning Tool (RAPT)
-   **Dataset:** National Risk Index (NRI) – Counties
-   **URL:** <https://www.fema.gov/emergency-managers/practitioners/resilience-analysis-and-planning-tool>

------------------------------------------------------------------------

## Variables of Interest

-   `state_name` (character): Full U.S. state name
-   `state_name_abbreviation` (character): Two-letter state abbreviation
-   `national_risk_index_score_composite` (numeric): Composite National Risk Index score at the county level
-   `race`: Groups of Race and Ethinicity
-   `county_name`: County Names in the US
-   `national_risk_index_state_percentile_composite`: (numeric) Composite National Risk Index state percentile at the county level

Only **U.S. states and California Counties** are included in the analysis; territories and the District of Columbia were removed.

------------------------------------------------------------------------

## Data Wrangling

Key preprocessing steps include:

-   Removing U.S. territories and non-state regions
-   Filtering to county-level observations only
-   Reordering factor levels to display California first in the visualization
-   Calculating the **median NRI score for California counties** for annotation
-   Separating words (county and state) to only have the county name
-   Creating new columns and Calculating a weighted risk from the percentile
-   Annotating the weighted risk percentiles on each racial and ethnic groups

------------------------------------------------------------------------

## Visualization Design

-   **Primary chart:** Boxplot by state and Lollipop
-   **Overlay:** Jittered points representing individual counties and with segmented lines
-   **Highlighting:** California counties are emphasized using color
-   **Annotation:** A horizontal dashed line marks California’s median NRI percentile and a vertical line for average weight risk

### Visualization Choices

-   Boxplots summarize central tendency and spread
-   Jittered points reveal distribution and density
-   Custom colors improve interpretability
-   Axis labels and theme adjustments enhance readability
-   Lollipop (point and line) to show distribution

------------------------------------------------------------------------

## Key Findings

-   California counties have **among the highest median NRI scores** relative to other states.
-   The median NRI score for California counties is approximately **94.85**.
-   Several states show substantially lower median NRI scores.
-   Asian, Hispanic or Latino, and Black populations have higher average risk than other groups, with values clustered near the upper end of the percentile scale.

------------------------------------------------------------------------

## Libraries
-   `tidyverse`
-   `ggplot2`
-   `forcats`
-   `gghighlight`
-   `tidycensus`
-   `scales`
-   `janitor`



