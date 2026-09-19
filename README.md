## Repository structure

```text
drosophila-toxic-metals/
├── README.md
├── code/
│   ├── README.md
│   ├── 01_literature_screening_and_gene_extraction.ipynb
│   └── 02_statistical_and_network_analysis.ipynb
├── data/
│   ├── README.md
│   ├── literature_corpus_507_records.csv
│   ├── Table_S1_gene_validation_85.csv
│   ├── final_gene_set_48.csv
│   └── DIOPT_ortholog_mapping_48_genes.csv
└── results/
    ├── README.md
    ├── duplicate_groups_audit.csv
    ├── gene_candidates_unique_1055.csv
    ├── gProfiler_enrichment_48_genes.csv
    ├── STRING_interactions_46_nodes.tsv
    ├── STRING_functional_annotations_46_nodes.tsv
    ├── STRING_GO_BP_enrichment_46_nodes.tsv
    ├── STRING_GO_MF_enrichment_46_nodes.tsv
    ├── STRING_GO_CC_enrichment_46_nodes.tsv
    ├── STRING_network_summary.csv
    ├── STRING_network_centrality_46_nodes.csv
    ├── functional_profile_observed_table.csv
    ├── functional_profile_global_test.csv
    └── functional_profile_permutation_results.csv
```

Detailed descriptions of individual files are provided in the README files within each directory.

## Main analytical dataset

`data/final_gene_set_48.csv` contains the frozen set of 48 validated *Drosophila melanogaster* genes used for downstream analyses.

The dataset retains gene-level information required to reconstruct the metal-associated subsets and primary functional categories used in the statistical analyses.

## Functional enrichment

Functional enrichment of the finalized 48-gene set was performed using g:Profiler/g:GOSt. The archived output is available as:

`results/gProfiler_enrichment_48_genes.csv`

## Functional-profile analysis

Differences among the Cd-, Pb-, and Hg-associated functional profiles were evaluated using gene-level permutation testing while preserving overlapping metal-associated gene memberships.

The global and category-specific tests are reproduced by `code/02_statistical_and_network_analysis.ipynb`.

Category-specific P-values were adjusted using the Benjamini–Hochberg false-discovery-rate procedure.

## STRING network analysis

STRING v12.5 was used to analyze functional associations among the finalized genes using *Drosophila melanogaster* as the organism and a minimum required combined interaction score of 0.400.

Of the 48 genes, 46 were mapped by STRING. The retained network contained a 37-node largest connected component with 105 associations; nine mapped genes were retained as isolated nodes at the selected threshold.

Network topology and node-level centrality statistics were calculated from the archived STRING interaction edge list. Weighted shortest-path distances were defined as:

`distance = 1 / combined_score`

The derived network statistics are available as:

- `results/STRING_network_summary.csv`
- `results/STRING_network_centrality_46_nodes.csv`

## Human orthology mapping

Human orthologue prediction for the finalized gene set was performed using DIOPT (DRSC Integrative Ortholog Prediction Tool).

The complete mapping output, including alternative predicted orthologues and supporting prediction methods, is archived as:

`data/DIOPT_ortholog_mapping_48_genes.csv`

Human orthologue candidates were identified for 47 of the 48 genes; no human orthologue was returned for `upd3` (FBgn0053542).

## Reproducibility

Two notebooks provide the principal computational workflows:

1. `code/01_literature_screening_and_gene_extraction.ipynb`  
   Reproduces literature deduplication, screening, candidate extraction, and deterministic gene-like filtering and audits the archived 85- and 48-gene validation stages.

2. `code/02_statistical_and_network_analysis.ipynb`  
   Reproduces functional-profile permutation testing and STRING-derived network statistics.

The repository distinguishes archived source/validation data, executable code, external-service outputs, and derived analytical results. Regenerable intermediate files are not retained as principal repository results.

## External resources

The workflow uses data or outputs from FlyBase, NCBI PubMed/PubMed Central, Europe PMC, g:Profiler/g:GOSt, STRING v12.5, and DIOPT. Database versions, access dates, search procedures, and analytical parameters are described in the associated manuscript and repository files.

## License

Software and code in the `code/` directory are licensed under the MIT License. See `LICENSE-MIT`.

Original curated datasets, derived analysis results, and repository documentation are licensed under the Creative Commons Attribution 4.0 International License (CC BY 4.0), unless otherwise indicated. See `LICENSE-CC-BY-4.0`.

Third-party content remains subject to the applicable terms and licenses of the original sources. See `LICENSE` for details.
