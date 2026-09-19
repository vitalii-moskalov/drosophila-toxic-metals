# Results

This directory contains the archived outputs and derived results from the
functional enrichment, protein-interaction network, and statistical analyses
performed on the finalized 48-gene *Drosophila melanogaster* dataset.

## g:Profiler functional enrichment

### `gProfiler_enrichment_48_genes.csv`

Functional-enrichment results obtained with g:Profiler/g:GOSt using the
finalized set of 48 FlyBase gene identifiers.

The file contains enriched functional terms, adjusted P-values, intersection
sizes, and the FlyBase identifiers contributing to each term.

## STRING outputs

STRING analyses were performed for the finalized gene set using
*Drosophila melanogaster* as the organism and a minimum required interaction
score of 0.400. Of the 48 input genes, 46 were mapped by STRING.

The original STRING outputs retained in this directory are:

- `STRING_interactions_46_nodes.tsv` — interaction edge list used for
  subsequent network-topology calculations.
- `STRING_functional_annotations_46_nodes.tsv` — functional annotations for
  the STRING-mapped genes.
- `STRING_GO_BP_enrichment_46_nodes.tsv` — Gene Ontology Biological Process
  enrichment output.
- `STRING_GO_MF_enrichment_46_nodes.tsv` — Gene Ontology Molecular Function
  enrichment output.
- `STRING_GO_CC_enrichment_46_nodes.tsv` — Gene Ontology Cellular Component
  enrichment output.

## Derived STRING network statistics

### `STRING_network_summary.csv`

Network-level statistics calculated from the archived STRING interaction
edge list at the 0.400 combined-score threshold.

Statistics are reported for the complete 46-node mapped set and for the
largest connected component.

### `STRING_network_centrality_46_nodes.csv`

Node-level network statistics for the 46 STRING-mapped genes.

The table includes degree, interaction strength, clustering coefficient,
and weighted betweenness centrality. For weighted shortest-path calculations,
edge distance was defined as:

`distance = 1 / combined_score`

Isolated mapped nodes are retained in the output.

## Functional-profile permutation analysis

The functional profiles of the Cd-, Pb-, and Hg-associated gene subsets were
compared using gene-level permutation testing while preserving overlapping
metal-associated gene memberships.

### `functional_profile_observed_table.csv`

Observed counts of genes assigned to the six mutually exclusive primary
functional categories across the Cd-, Pb-, and Hg-associated subsets.

### `functional_profile_global_test.csv`

Result of the global permutation test for heterogeneity of the functional
profiles across the three metal-associated subsets.

### `functional_profile_permutation_results.csv`

Category-specific gene-level permutation tests with Benjamini-Hochberg
false-discovery-rate correction.

The proteostasis category remained significant after multiple-testing
correction, whereas the other primary functional categories did not reach
the FDR-adjusted significance threshold.

## Reproducibility

The derived functional-profile and network-statistics files are generated
by:

`code/02_statistical_and_network_analysis.ipynb`

The notebook uses the frozen analytical dataset:

`data/final_gene_set_48.csv`

and the archived STRING interaction edge list:

`results/STRING_interactions_46_nodes.tsv`

as its principal inputs.

External-service outputs from g:Profiler and STRING are archived here to
preserve the analytical provenance of the downstream analyses.
