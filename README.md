# drosophila-toxic-metals
Curated gene dataset and reproducible analyses of cadmium-, lead-, and mercury-associated molecular mechanisms in Drosophila melanogaster

### STRING network statistics

- `STRING_network_summary.csv` — network-level topological statistics
  calculated from the STRING v12.5 association network at a minimum
  combined interaction score of 0.400. The file reports statistics
  for the complete set of 46 STRING-mapped genes and for the
  37-node largest connected component containing all 105 retained
  associations.

- `STRING_network_centrality_46_nodes.csv` — node-level network
  statistics for the 46 STRING-mapped genes, including degree,
  interaction strength, clustering coefficient, and weighted
  betweenness centrality. Weighted shortest-path distances were
  defined as the inverse of the STRING combined score. Nine genes
  without associations above the 0.400 threshold are retained as
  isolated nodes.
