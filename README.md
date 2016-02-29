# Identifying candidate OPC–endothelial cell interactors

By Daniel Himmelstein & Dan Zollinger

Oligodendrocyte precursor cells (OPCs) were [recently found](https://doi.org/10.1126/science.aad3839 "Oligodendrocyte precursors migrate along vasculature in the developing nervous system") to migrate along the vascular endothelium. Here we identify gene pairs that are candidate OPC–endothelial cell interactors. We create a filtered set of gene-gene interactions by:

+ filtering for genes that participate in relevant GO terms
+ filtering for gene-pairs that exceed an interaction confidence score threshold
+ filtering for gene-pairs where one gene is enriched in OPCs and the other is enriched in endothelial cells.

The filtered dataset provides a candidate network of interactions for biologic interrogation.

## Execution

Execute the notebooks in the following order:

1. [`enrichment.ipynb`](enrichment.ipynb) — calculate transcriptional fold changes for OPCs and endothelial cells. Integrate Gene Ontology annotations.
2. [`interaction.ipynb`](interaction.ipynb) — integrate protein interactions with expression and GO data. Filter interactions according to user-defined parameters. Create an interaction network.

## Datasets

The following datasets are created:

+ [`enrichment.tsv`](data/enrichment.tsv) — text file with expression fold changes and GO annotations.
+ [`filtered.xlsx`](data/filtered.xlsx) — spreadsheet with the filtered interactions.
+ [`network.graphml`](data/filtered.xlsx) — network constructed using the filtered interactions. This file can be loaded into [Cytoscape 3](http://www.cytoscape.org/) using the menu option: File ▶ Import ▶ File.

## Resources

Expression data is from the [Brain RNA-Seq database](http://web.stanford.edu/group/barres_lab/brain_rnaseq.html) [Zhang et al (2014) [_J Neurosci_](https://doi.org/10.1523/JNEUROSCI.1860-14.2014 "An RNA-Sequencing Transcriptome and Splicing Database of Glia, Neurons, and Vascular Cells of the Cerebral Cortex")].

Protein-protein interactions are extracted from the [STRING database](http://string-db.org/) version 10 [Szklarczyk et al (2015) [_Nucl Acids Res_](https://doi.org/10.1093/nar/gku1003 "STRING v10: protein–protein interaction networks, integrated over the tree of life")].

Gene Ontology annotations are retrieved from [user-friendly GO Annotations](http://git.dhimmel.com/gene-ontology/) [Himmelstein et al (2015) [_Zenodo_](https://doi.org/10.5281/zenodo.21711 "gene-ontology: Initial zenodo release")].

## Installation

_Instructions for biologists:_

If you don't already have python, install [Anaconda for Python 3.5](https://www.continuum.io/downloads).

Next clone this repository to your computer. You can also [download and extract a zip](https://github.com/dhimmel/opcendo/archive/master.zip).

Launch Jupyter (`jupyter notebook` in terminal or using the Anaconda GUI) and navigate to the `opcendo` directory.

## License

All original content in this repository is released under [CC0 1.0](https://creativecommons.org/publicdomain/zero/1.0/ "Creative Commons · Public Domain Dedication"). STRING data is licensed as [CC BY 3.0](http://creativecommons.org/licenses/by/3.0/). The Gene Ontology data is licensed as [CC BY 4.0](http://creativecommons.org/licenses/by/4.0/). Brain RNA-Seq data is included with permission from its creator Steven Sloan.
