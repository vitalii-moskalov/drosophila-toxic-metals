# Code

This directory contains Python and R scripts and Jupyter/Google Colab notebooks used for data processing, validation, statistical analysis, and visualization.

# Code

This directory contains the Jupyter/Google Colab notebooks used for
data processing, validation, statistical analysis, and network analysis.

- `01_literature_screening_and_gene_extraction.ipynb` — reproduces the
  literature-screening and gene-extraction workflow used to generate
  and validate the initial candidate-gene dataset.

- `02_statistical_and_network_analysis.ipynb` — reproduces the gene-level
  permutation analysis of Cd-, Pb-, and Hg-associated functional profiles
  and the STRING network topology and centrality analyses.

The statistical analysis uses 100,000 gene-level permutations with a
fixed random seed and Benjamini–Hochberg correction for category-specific
tests. The network analysis uses STRING associations retained at a minimum
combined interaction score of 0.400 and reports network topology, degree,
interaction strength, clustering, and weighted betweenness centrality.

Input datasets are stored in `../data/`, and generated analysis outputs
are stored in `../results/`.
