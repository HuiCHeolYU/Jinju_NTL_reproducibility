# Reproducibility package for Jinju nighttime light decline analysis

This repository provides reproducibility materials for the manuscript:

**Analyzing Declining Urban Activity Using Nighttime Light and Land-Use Change: An Urban–Non-Urban Comparative Case Study**

## 1. Purpose of this package

This package provides the preprocessing criteria, analysis workflow, derived grid-level datasets, and supplementary outputs used to identify declining nighttime activity areas in Jinju City for the periods 2012–2019 and 2019–2024.

The package is intended to support reproducibility of the main results reported in the manuscript, including:

- grid-level nighttime light preprocessing;
- Theil–Sen slope estimation;
- Mann–Kendall trend testing;
- Benjamini–Hochberg false discovery rate correction;
- seasonal Mann–Kendall robustness check;
- land-cover overlay and land-use change calculation;
- regression input table construction;
- regression diagnostics and spatial robustness outputs.

## 2. Raw data sources

The raw VIIRS Black Marble VNP46A3 nighttime light data are publicly available from NASA Earthdata.

The detailed land-cover maps for 2012 and 2024 are publicly available from the Environmental Spatial Information Service of the Ministry of Environment of Korea.

The raw VIIRS and raw land-cover datasets are not redistributed in this repository because they are publicly available from their original providers. This package provides derived data and processing documentation needed to reproduce the main analytical results.

## 3. Folder structure

Jinju_NTL_reproducibility_package/
│
├─ README.txt
├─ code/
├─ derived_data/
├─ supplementary_outputs/
└─ processing_notes/

## Key preprocessing criteria

In addition, five monthly files were excluded during preprocessing because of severe anomalous values across the study area: 201206, 201506, 202007, 202009, and 202208. These months were treated as missing observations and were not imputed. The trend analyses were conducted using the available monthly observations.
