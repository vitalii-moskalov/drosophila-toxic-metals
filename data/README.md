# Data

This directory contains the literature-derived datasets, curated gene sets,
and orthology-mapping data used in the analysis of cadmium-, lead-, and
mercury-associated molecular mechanisms in *Drosophila melanogaster*.

## Files

### `literature_corpus_507_records.csv`

Curated literature corpus used for gene extraction and subsequent screening.
The dataset contains 507 literature records retained for the analysis.

### `Table_S1_gene_validation_85.csv`

Validation table for the 85 candidate genes identified during literature
screening. The table documents gene-symbol validation and standardization
against FlyBase and records the decisions used to construct the final
analytical gene set.

### `final_gene_set_48.csv`

Frozen analytical dataset containing the 48 validated *Drosophila
melanogaster* genes retained for downstream analyses.

This file is the primary input dataset for functional-profile permutation
analysis and provides the gene set used for functional enrichment, STRING
network analysis, and orthology mapping.

### `DIOPT_ortholog_mapping_48_genes.csv`

Complete DIOPT ortholog-mapping output for the finalized 48-gene dataset.

The file contains all candidate human orthologs reported by DIOPT rather
than only the highest-scoring match. It includes DIOPT scores, weighted
scores, ranks, best-score indicators, and the supporting ortholog-prediction
methods.

All 48 input FlyBase gene identifiers are represented in the export.
Human ortholog candidates were identified for 47 of the 48 genes; no human
ortholog was returned for `upd3` (FBgn0053542).

## Data provenance

Gene nomenclature and FlyBase identifiers were validated against FlyBase.

Orthology mapping was performed using DIOPT (DRSC Integrative Ortholog
Prediction Tool). The complete mapping output is retained to preserve the
provenance of alternative ortholog predictions and their associated scores.

External functional-enrichment and network-analysis outputs are stored
separately in the `results/` directory.

## Reproducibility

The finalized analytical dataset is `final_gene_set_48.csv`. It should be
treated as the frozen input gene set for downstream analyses.

Code and notebooks used for data processing and statistical analyses are
available in the `code/` directory.
