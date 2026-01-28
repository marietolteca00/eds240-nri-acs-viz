# FEMA National Risk Index (NRI) – California vs Other U.S. States

# Author: Marie Tolteca, MEDS Student

# Date: 01/28/2026

## Project Overview

This project explores how **FEMA National Risk Index (NRI) scores for counties in California compare to counties in other U.S. states**. The analysis focuses on visualizing the distribution of county-level NRI scores by state, with California highlighted for comparison.

The final visualization uses **boxplots with overlaid jittered points** to show both summary statistics and individual county-level variation.

## Repository Structure
```
.
├── data
│   └── National_Risk_Index_Counties_807384124455672111.csv
├── eds240-nri-acs-viz.Rproj
├── fema_nri_files
│   ├── figure-html
│   │   ├── unnamed-chunk-4-1.png
│   │   └── unnamed-chunk-5-1.png
├── fema_nri.html
├── fema_nri.qmd
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

Only **U.S. states** are included in the analysis; territories and the District of Columbia were removed.

------------------------------------------------------------------------

## Data Wrangling

Key preprocessing steps include:

-   Removing U.S. territories and non-state regions
-   Filtering to county-level observations only
-   Reordering factor levels to display California first in the visualization
-   Calculating the **median NRI score for California counties** for annotation

------------------------------------------------------------------------

## Visualization Design

-   **Primary chart:** Boxplot by state
-   **Overlay:** Jittered points representing individual counties
-   **Highlighting:** California counties are emphasized using color
-   **Annotation:** A horizontal dashed line marks California’s median NRI percentile 

### Visualization Choices

-   Boxplots summarize central tendency and spread
-   Jittered points reveal distribution and density
-   Custom colors improve interpretability
-   Axis labels and theme adjustments enhance readability

------------------------------------------------------------------------

## Key Findings

-   California counties have **among the highest median NRI scores** relative to other states.
-   The median NRI score for California counties is approximately **94.85**.
-   Several states show substantially lower median NRI scores.

------------------------------------------------------------------------

## Libraries
-   `tidyverse`
-   `ggplot2`
-   `forcats`
-   `gghighlight`



