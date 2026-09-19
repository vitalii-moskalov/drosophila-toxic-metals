# Code

This directory contains the Jupyter/Google Colab notebooks used for data
processing, validation, statistical analysis, and network analysis.

## Notebooks

### `01_literature_screening_and_gene_extraction.ipynb`

Documents and reproduces the literature-screening, gene-extraction, and
candidate-gene validation workflow used to construct the analytical gene
dataset.

### `02_statistical_and_network_analysis.ipynb`

Reproduces the downstream statistical and network analyses performed on the
finalized 48-gene dataset.

The notebook performs:

- gene-level permutation analysis of the Cd-, Pb-, and Hg-associated
  functional profiles;
- a global test of functional-profile heterogeneity using 100,000
  gene-level permutations with a fixed random seed;
- category-specific permutation tests with Benjamini-Hochberg FDR
  correction;
- STRING network topology and node-centrality analysis using associations
  retained at a minimum combined interaction score of 0.400;
- calculation of degree, interaction strength, clustering coefficient,
  and weighted betweenness centrality.

For weighted shortest-path calculations, edge distance is defined as:

`distance = 1 / combined_score`

Network-level statistics are calculated for both the complete 46-node
STRING-mapped set and its largest connected component.

## Inputs and outputs

Input datasets are stored in `../data/`.

The archived STRING interaction edge list used by the network analysis and
the generated analytical outputs are stored in `../results/`.

The principal inputs to the downstream analysis are:

- `../data/final_gene_set_48.csv`
- `../results/STRING_interactions_46_nodes.tsv`

Generated outputs include:

- `../results/functional_profile_observed_table.csv`
- `../results/functional_profile_global_test.csv`
- `../results/functional_profile_permutation_results.csv`
- `../results/STRING_network_summary.csv`
- `../results/STRING_network_centrality_46_nodes.csv`

## Reproducibility

`02_statistical_and_network_analysis.ipynb` is designed for execution in
Google Colab/Jupyter and uses a fixed random seed for the permutation
analysis so that the reported statistical results can be reproduced.
