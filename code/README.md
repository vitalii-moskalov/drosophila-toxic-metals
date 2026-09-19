# Code

This directory contains the Jupyter/Google Colab notebooks used to reproduce the computational and statistical analyses of cadmium-, lead-, and mercury-associated genes in *Drosophila melanogaster*.

## Notebooks

### `01_literature_screening_and_gene_extraction.ipynb`

Reproduces the literature-processing and gene-candidate extraction workflow used to construct the analytical dataset.

The notebook:

- loads the archived corpus of 507 bibliographic records;
- performs explicit publication-level deduplication using PMID, DOI, PMCID, and informative normalized titles;
- retains 454 unique publication-level records;
- applies semi-automated literature screening and identifies 144 high-priority records;
- extracts 18,679 publication-level gene-like candidate mentions;
- generates 1,055 unique gene-like candidates for downstream identifier and evidence validation;
- generates a bibliographic duplicate audit;
- verifies the archived 85-gene validation table and the final 48-gene analytical dataset;
- confirms that all 48 final FlyBase identifiers are represented in the 85-gene validation table.

The computational literature-processing and candidate-extraction stages are reproduced directly. The subsequent transition from 1,055 gene-like candidates to 85 preliminarily validated genes and then to the final 48-gene set involved identifier/source validation and expert curation. These stages are therefore audited against the archived validation datasets rather than reconstructed using a retrospective selection rule.

Principal inputs are stored in `../data/`. Reproducible provenance outputs are written to `../results/`, while regenerable intermediate files are written to `../results/literature_screening_intermediate/`.

### `02_statistical_and_network_analysis.ipynb`

Reproduces the additional statistical and network analyses performed on the final validated gene set.

The notebook:

- performs gene-level permutation analysis of Cd-, Pb-, and Hg-associated functional profiles;
- preserves overlapping metal-associated gene subsets during permutation;
- evaluates the global functional-profile statistic using 100,000 permutations;
- performs category-specific permutation tests with Benjamini–Hochberg FDR correction;
- reconstructs the STRING network from associations retained at a minimum combined interaction score of 0.400;
- calculates network topology and node-level centrality statistics, including degree, interaction strength, clustering coefficient, and weighted betweenness centrality;
- reports network-level statistics for the complete STRING-mapped set and the largest connected component.

Principal inputs are stored in `../data/` and `../results/`. Generated statistical and network-analysis outputs are stored in `../results/`.

## Reproducibility

Both notebooks are designed for execution in Jupyter or Google Colab using the repository directory structure.

The repository separates:

1. archived input and validation datasets (`data/`);
2. executable analysis notebooks (`code/`);
3. reproducible analysis outputs (`results/`).

Intermediate files generated during literature processing are retained separately from the principal archived results because they can be regenerated directly by `01_literature_screening_and_gene_extraction.ipynb`.
