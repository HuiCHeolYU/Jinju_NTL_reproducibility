[README.md](https://github.com/user-attachments/files/34665890/README.md)
# Reproducibility materials for the Jinju nighttime light study

**Manuscript:** *Analyzing Declining Nighttime Activity Using Nighttime Light and Land-Use Change: An Urban and Non-Urban Comparative Case Study*

## 1. Current archive

Download [Jinju_NTL_reproducibility_package.zip](./Jinju_NTL_reproducibility_package.zip), the archive accompanying the revised manuscript and Supplementary Tables S1–S4.

- Archive size: **2,719,950 bytes**.
- Archive SHA-256: `0c1da5c9676207d660243ed1613cd77d556608fd11af1b6aa28d9d7687b541f7`.
- Contents: **123 files**. The internal `SHA256SUMS.txt` lists the other 122 files.

The archive contains preprocessing and analysis scripts, retained grid-level derived inputs and statistical outputs, processing documentation, and checks that can be run with the packaged inputs. It does not provide a complete reconstruction from the original satellite and population observations.

## 2. Package structure

```text
Jinju_NTL_reproducibility_package/
├── README.txt
├── code/
├── derived_data/
├── processing_notes/
├── supplementary_outputs/
└── SHA256SUMS.txt
```

- `code/`: input-preparation helpers, historical scripts, revision workflows, and checks using supplied inputs.
- `derived_data/`: retained NTL trend records, grid identifiers, land-cover tables, and regression inputs.
- `processing_notes/`: data-source routes, preprocessing information, script inventories, execution records, and limitations.
- `supplementary_outputs/`: retained diagnostics, sensitivity analyses, overlap summaries, and related revision outputs.

## 3. Checks supported by the supplied inputs

After extracting the ZIP, open the `Jinju_NTL_reproducibility_package` directory. Follow its `README.txt` and install the requirements in the appropriate Python environment:

```bash
python -m pip install -r requirements-supplied-inputs.txt
python code/run_supplied_inputs.py --output-dir reproduced_supplied_inputs
python code/15_verify_supplied_inputs.py --results reproduced_supplied_inputs
python code/verify_package.py
```

These checks cover FDR correction from stored p-values, summaries and spatial overlap of stored seasonal classifications, OLS sensitivity analyses using the supplied regression inputs, descriptive calculations, and file integrity. They start from retained derived inputs and outputs. They do not regenerate the monthly NTL observations, reproduce population allocation, or re-estimate the original spatial-lag model.

Matching checksums establishes file identity and integrity; it does not establish the scientific correctness of every reported result.

## 4. Original data sources and input preparation

- VIIRS Black Marble VNP46A3: [NASA LAADS DAAC](https://ladsweb.modaps.eosdis.nasa.gov/missions-and-measurements/products/VNP46A3/) and [NASA Earthdata Search](https://search.earthdata.nasa.gov/).
- Detailed land-cover maps: [Environmental Spatial Information Service](https://egis.me.go.kr/req/intro.do).
- Population and administrative boundaries: [Statistical Geographic Information Service](https://sgis.kostat.go.kr/), through its data-provision procedures.

See `processing_notes/data_sources_and_code_guide.txt` and `processing_notes/monthly_ntl_source_workflow.txt` for official acquisition routes, required inputs, and script-use boundaries. Input-preparation helpers require explicit source choices and suitable grid geometry. Their inclusion does not establish that those exact scripts and settings generated the retained study results.

## 5. Materials not included and reproduction limits

The archive does not include the final grid-level monthly NTL input CSV, original SGIS inputs, final annual grid-population values and allocation records, or the original spatial weights and complete spatial-lag estimation workflow. Exact source identifiers, the original grid geometry and CRS, and some preprocessing decisions also remain incompletely documented.

Consequently, the archive alone cannot independently reproduce the original monthly trend tests, population assignment, or spatial-lag estimation. Stored results and executable checks of derived inputs should be distinguished from reconstruction from original observations. Further details on these limits are retained in the package notes and the manuscript's data-availability and limitations statements.

## 6. Version notes

This editorial submission update aligns the archive and this description with the corrected manuscript figures and wording. Figure 1(b) has a corrected legend label, and Figure 6 has corrected A/B arrow placement. The reported numerical results and all existing analytical inputs and tabulated outputs are unchanged. No statistical analyses were re-estimated. The archive's dated internal notes preserve the history of earlier local preparation operations, including their upload and execution status at that time.


## 7. Editorial correction scope on 10 November 2026

The manuscript's citywide interpretation now refers to mapped land-cover area associations without inferring residential densification or changes in facility utilization. The reviewer response describes the figure and wording corrections.

Within the archive, Figure 6 and its drawing code are updated only for annotation placement. Existing CSV/JSON analytical records and source raster classifications are preserved. See `processing_notes/editorial_corrections_20261110.json` and `requirements-figure-editorial.txt`. The original statistical environment and its historical records remain separately documented.

The existing limits on monthly-input reconstruction, population allocation and spatial-lag reproduction remain. The P95 boundary convention and the 72 m² map/regression case-area difference were not resolved or numerically changed in this editorial update. No public repository upload was performed by this update.
