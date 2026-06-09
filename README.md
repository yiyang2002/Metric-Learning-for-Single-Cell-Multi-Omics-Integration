# Single-Cell Multi-Omics Integration with Metric Learning

This project builds a machine learning workflow for integrating scRNA-seq and scATAC-seq profiles into a shared latent space for single-cell multi-omics analysis.

## Why This Matters

Single-cell multi-omics data can reveal how gene expression and chromatin accessibility relate within the same biological system, but the modalities have different feature spaces, sparsity patterns, and technical noise. This project explores how metric learning can align these modalities so downstream analyses such as visualization, clustering, and cell-type comparison become more coherent.

The repository was originally developed as a CPSC 545 machine learning final project and is presented here as a compact computational biology portfolio artifact.

## Technical Overview

- **Data modalities:** single-cell RNA-seq expression profiles and scATAC-seq-derived gene activity profiles stored as AnnData `.h5ad` objects.
- **Preprocessing:** Scanpy-based filtering, normalization, highly variable gene selection, scaling, and PCA.
- **Integration strategy:** scDML-style metric learning with nearest-neighbor and mutual-nearest-neighbor structure to support cross-modality alignment.
- **Modeling experiments:** optimal transport and triplet-loss-based embedding workflows for learning a shared representation.
- **Evaluation:** UMAP visualization, Leiden clustering, and quantitative embedding metrics including ARI, NMI, and silhouette score.
- **Implementation stack:** Python, Jupyter, Scanpy, AnnData, NumPy, pandas, scikit-learn, TensorFlow/Keras, PyTorch metric learning utilities, and approximate nearest-neighbor libraries.

## Repository Contents

| File | Description |
| --- | --- |
| [`Cpsc545_final_report_v2.pdf`](./Cpsc545_final_report_v2.pdf) | Final project report describing the motivation, method, experiments, and evaluation. |
| [`scDML_v2.ipynb`](./scDML_v2.ipynb) | Main notebook implementing preprocessing, scDML-style integration logic, clustering, visualization, and evaluation. |
| [`OT_triplet_loss.ipynb.zip`](./OT_triplet_loss.ipynb.zip) | Compressed notebook containing the optimal transport and triplet loss experiments, including plots and metric tables. |
| [`rna.h5ad.zip`](./rna.h5ad.zip) | Compressed AnnData object containing the scRNA-seq input data. |
| [`geneact.h5ad.zip`](./geneact.h5ad.zip) | Compressed AnnData object containing scATAC-seq-derived gene activity data. |
| [`adata_merge(insct_10000).h5ad.zip`](./adata_merge(insct_10000).h5ad.zip) | Compressed integrated AnnData artifact produced after training iterations for downstream metric-learning analysis. |

## Skills Demonstrated

- Single-cell RNA-seq and ATAC-seq data handling with AnnData and Scanpy.
- Multi-omics representation learning for cross-modality integration.
- Metric learning using triplet loss and neighbor-graph structure.
- Embedding evaluation with clustering and quantitative comparison metrics.
- Scientific reporting through a written project report, notebooks, visualizations, and reproducible data artifacts.

## Reproducibility Notes

The notebooks and compressed data files are included as project artifacts. To rerun the workflow, unzip the `.h5ad` and notebook archives first, then update any local paths in the notebooks to match your environment. Some notebook cells were developed in Google Colab, so package installation and drive-mount cells may need to be adapted for local execution.

## Project Context

This work was completed for CPSC 545 as a machine learning project focused on computational biology applications. The public repository is organized to highlight the modeling workflow, data integration problem, and technical skills relevant to biotech, bioinformatics, and computational biology roles.
