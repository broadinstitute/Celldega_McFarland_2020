# Celldega McFarland 2020 DegaFiles

DegaFiles for the [MIX-seq drug screen tutorial](https://broadinstitute.github.io/celldega/examples/tutorial_notebooks/MIX-seq_Drug_Screen_Landscape-Clustergram-Enrich/) in the [Celldega](https://github.com/broadinstitute/celldega) documentation. Celldega's Landscape reads these files directly from this repository to color a UMAP of 86,907 cells by the expression of any of 27,800 genes.

## Source data and attribution

These files are derived from the MIX-seq drug screen of McFarland et al. (2020):

> McFarland JM, Paolella BR, Warren A, et al. Multiplexed single-cell transcriptional response profiling to define cancer vulnerabilities and therapeutic mechanism of action. *Nature Communications* 11, 4296 (2020). https://doi.org/10.1038/s41467-020-17440-w

The data were released by the Broad Institute's Cancer Data Science group on figshare ([MIX-seq data](https://doi.org/10.6084/m9.figshare.10298696)) under CC BY 4.0. We used the harmonized version from scPerturb ([`McFarlandTsherniak2020.h5ad`](https://doi.org/10.5281/zenodo.7041849), CC BY 4.0), as distributed by [pertpy](https://pertpy.readthedocs.io/) (`pertpy.data.mcfarland_2020`):

> Peidli S, Green TD, Shen C, et al. scPerturb: harmonized single-cell perturbation data. *Nature Methods* 21, 531–540 (2024). https://doi.org/10.1038/s41592-023-02144-y

If you use these files, please cite McFarland et al. (2020) and scPerturb.

## Changes from the source

The [pre-process notebook](https://huggingface.co/datasets/broadinstitute/Celldega_Supporting_Data/blob/main/McFarland_2020/McFarland_2020_Pre-process.ipynb) made these changes:

- kept normal-quality cells from the 24-hour drug panel: 13 drugs and DMSO controls in 169 cell lines;
- kept genes detected in at least 3 cells;
- wrote the raw counts as DegaFiles: one Parquet file per gene in `cbg/`, plus `cell_metadata.parquet`, `meta_gene.parquet`, and `landscape_parameters.json`.

The UMAP coordinates and cell annotations (cell line, cancer type, drug, mechanism of action, and experiment group) are in the companion AnnData file, [`McFarland_2020_24h_drug_panel.h5ad`](https://huggingface.co/datasets/broadinstitute/Celldega_Supporting_Data/blob/main/McFarland_2020/McFarland_2020_24h_drug_panel.h5ad), on Hugging Face.

## License

These derived files are shared under the same [Creative Commons Attribution 4.0 International (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/) license as the source data; see [LICENSE](LICENSE).
