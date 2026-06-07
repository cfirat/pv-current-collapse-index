# PV Current-Collapse Index

This repository contains the Python analysis notebook and processed outputs associated with the manuscript:

**A Current-Collapse Index for Diagnosing Mismatch-Induced Instantaneous Efficiency Degradation in Photovoltaic Modules**

Author: **Coskun Firat**  
Affiliation: Energy Institute, Istanbul Technical University, Istanbul, Türkiye  
ORCID: 0000-0002-2853-8940

## Overview

Partial shading, non-uniform soiling, and mismatch-inducing surface conditions can cause severe instantaneous power loss in photovoltaic (PV) modules. Conventional scalar indicators such as fill factor (FF) may remain relatively high even when the maximum power has collapsed.

This repository implements an I–V-curve-derived diagnostic based on the dimensionless current-collapse index:

R_I = I_sc/I_sc,clean

where (I_sc) is the short-circuit current of a measured trace and (I_sc,clean) is the median clean short-circuit current for the same module.

The analysis evaluates whether (R_I) can distinguish mild optical attenuation from mismatch-dominated current collapse using publicly available experimental I–V data for two crystalline-silicon PV modules measured under clean, soiled, and partially shaded conditions.

## Main findings

The analysis shows that:

- Partial shading reduced mean irradiance-normalized relative efficiency by approximately **73%** in the 30 W HYBRYTEC M5-30/12 module.
- Partial shading reduced mean irradiance-normalized relative efficiency by approximately **84%** in the 90 W Solar Plus Energy SP090P module.
- Across all 17 experimental I–V traces, the current-collapse index \(R_I\) strongly tracked the unclipped relative efficiency proxy:
  - Pearson (r = 0.984)
  - (R^2 = 0.968)
  - fitted slope = 0.922
- Fill factor remained relatively high, approximately **0.71–0.86** in shaded traces, even when most of the maximum power had been lost.
- A threshold near (R_I = 0.5) separated clean and shaded traces in this dataset and identified an anomalous soiled trace as a current-collapse case.

The threshold is dataset-supported and should not be interpreted as a universal physical constant.

## Data source

The raw experimental I–V dataset is openly available from:

Restrepo-Cuestas, B., Guarnizo-Lemus, C., Rojas-Montano, J. J., Montoya-Marin, J. A., & Ibañez-Diaz, A. A. (2024).  
**Experimental data for mismatching faults of photovoltaic modules.**  
Mendeley Data, V2.  
https://doi.org/10.17632/xjs42j8dtf.2

The raw dataset is not redistributed in this repository. Users should download it directly from Mendeley Data and follow the folder structure expected by the notebook.

## Repository contents

```text
notebooks/
    study_iv_current_collapse_v2.ipynb
        Main analysis notebook. Loads the experimental I–V data, extracts trace-level features,
        computes the current-collapse index, generates figures, and exports summary tables.

outputs/
    iv_summary.csv
        Trace-level summary of extracted and reconstructed I–V features.

    condition_summary.csv
        Condition-level statistics by module and surface state.

    table2_correlation.csv
        Correlation and linear-fit statistics between \(R_I\) and \(\eta_{rel,raw}\).

    figures/
        Final manuscript figures in PNG format.

manuscript/
    manuscript_improved.pdf
        Manuscript PDF, if included.
