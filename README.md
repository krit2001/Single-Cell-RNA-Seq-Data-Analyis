# Single-Cell Analysis of Mouse Limb Development (GSE142425)

This repository contains the analysis pipeline for single-cell RNA-seq data from mouse embryonic forelimb development (E11.5–E18.5) [GSE142425]. The workflow focuses on trajectory inference of Col2a1+ lineages using **scVI** for integration and **scVelo** for RNA velocity. Col2a1+ cells are 

## 🧬 Analysis Workflow

The analysis is performed in Python using the `scverse` ecosystem.

1.  **Preprocessing**: Quality control, doublet removal, and normalization using [Scanpy](https://scanpy.readthedocs.io/).
2.  **Integration**: Batch effect correction across developmental timepoints using [scVI](https://scvi-tools.org/).
3.  **Clustering**: Leiden clustering on the scVI latent space.
4.  **RNA Velocity**:
    - Spliced/unspliced quantification (if re-processed from FASTQ).
    - Velocity estimation using the dynamical model in [scVelo](https://scvelo.readthedocs.io/).
    - Trajectory inference for chondrogenic (Col2a1+) differentiation.

## 📂 Repository Structure

- `notebooks/`: Jupyter notebooks numbered by analysis step.
- `models/`: Directory for saving trained scVI models (not tracked by git).
- `data/`: Placeholder for raw and processed `.h5ad` files.

## 🚀 Getting Started

### 1. Environment Setup
Create the conda environment to ensure version compatibility between `scvi-tools` and `scvelo`.
```bash
conda env create -f environment/environment.yml
conda activate scrna_limb
